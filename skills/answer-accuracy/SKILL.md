---
name: answer-accuracy
description: 'Build a spreadsheet of each AI answer that names the business, with the exact words, tone, other businesses named, and cited pages, so that a person can mark what is wrong. Use for "what does ChatGPT say about me" or a wrong description.'
---

# Answer accuracy

Use this guidance to list each saved answer that names the business, so that a person can read what AI apps say and mark what is wrong. A chart cannot show a wrong fact. A person must read the words.

## Before you start

This skill reads a Frontmost AI project through the Frontmost AI tools that this plugin connects.

- If a tool returns `setup_required`, give the person the `url` from the result. Stop until they say that set-up is done.
- If a tool returns `plan_required`, say that this data needs a paid Frontmost AI plan, and stop.
- If the Frontmost AI tools are not available, ask the person to connect Frontmost AI: https://frontmost.ai/connect
- Never invent the data, and never fill a gap with a guess.

## Build the sheet

1. Call `get_scan` for the project and the scan in the request. Read `metric_breakdown`.
2. Call `get_answers` with the `project_id`, the `scan_id`, `named: true`, and `limit: 20`. Call again with each `next_cursor` until it is null.
3. Do step 2 again with `questions: "unbranded"`. An answer `id` in this second list is from an unbranded question.
4. Make one row for each answer. The row key is the answer `id`. Put it in the last column and never change it.
5. Fill the Frontmost AI columns:

| Column | Value |
|---|---|
| Scan Date | the date of the scan |
| AI App | `app` |
| Question | `question.text` |
| Branded | "Unbranded" or "Branded", from step 3 |
| What It Says | `excerpt`, copied word for word |
| Sentiment | `sentiment` |
| Position | `position` |
| Others Named | the names in `mentions` where `you` is false |
| Cited Pages | the `url` values in `citations`. Mark the ones where `own_site` is true |
| Check This | see below |
| Link | `url` |

6. Add the columns that the person fills in: Accurate or Wrong, What Is Wrong, Page That Should Correct It. Leave them empty.
7. Above the table, write three lines from `metric_breakdown`: all questions, branded, and unbranded. Each line gives `visibility.named` of `visibility.answers`.

## The Check This column

- Write a short note only when the excerpt states a fact that the person can check: a price, a customer type, a product type, a location, a feature, or a different business with a similar name.
- Quote the words that hold the fact. Do not say that the fact is wrong. You do not know the business as the person does.
- If the person gave you their site or their facts in this conversation, you can say which fact differs and quote both.
- Leave the cell empty for an answer with no checkable fact.

## Refresh the sheet

1. Do steps 1 to 3 again for the latest scan.
2. Match each answer to a sheet row by the answer `id`. An answer `id` belongs to one scan, so most rows of a new scan are new.
3. Add the new rows above the old rows. Never delete an old row or its typed cells.
4. Rewrite the three count lines.

## Rules

- Copy the excerpt. Never rewrite it, and never join two answers.
- To read a full answer, call `get_answers` with `answer_id`.
- Report each rate with its counts. Keep branded and unbranded apart.
- Never tell the person to ask an AI app to change an answer, to post fake reviews, or to expect a correction by a date. The usual correction is a clear statement of the fact on the person's own page and on the pages that the answer cites.
- Ask before you change anything in Frontmost AI. This sheet reads only.

## Output

A spreadsheet file with one table, the three count lines above it, and the scan date. Then list the answers with a Check This note, in the order of the sheet. If the AI app cannot make a file, return the table as CSV.
