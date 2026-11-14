---
name: placement-tracker
description: 'Build and refresh a spreadsheet of the cited pages that do not list the business: outreach status, quote, cost per citing answer, and the answers that name the business after a listing goes live. Use to track listicle outreach. Needs a Frontmost AI project.'
---

# Placement tracker

Use this guidance to build a working sheet of the cited pages that do not list the business. The person works one row from first contact to a listing, then sees if AI apps name the business after it.

## Before you start

This skill reads a Frontmost AI project through the Frontmost AI tools that this plugin connects.

- If a tool returns `setup_required`, give the person the `url` from the result. Stop until they say that set-up is done.
- If a tool returns `plan_required`, say that this data needs a paid Frontmost AI plan, and stop.
- If the Frontmost AI tools are not available, use the `source-map` skill. It needs no account, and it works from a web search. To read the pages that AI answers cite, with counts, the person connects Frontmost AI: https://frontmost.ai/connect
- Never invent the data, and never fill a gap with a guess.

## Build the sheet

1. Call `get_sources` for the project and the scan in the request. Then call it with `page_urls` for the pages in `pages_to_get_on` and `questions: "unbranded"`, 50 pages in each call.
2. Make one row for each page in `pages_to_get_on`. The row key is the page `url`. Never change it.
3. Fill the Frontmost AI columns from the data:

| Column | Value |
|---|---|
| Page | `url` |
| Type | `type` |
| Answers Citing It | `answers` from the first call |
| Unbranded Answers Citing It | `answers` for the same `url` in the second call |
| Rivals Listed | the names in `rivals` where `listed` is true |
| Lists You | `you`: Present, Not present, or Check needed. A refresh can also write No current read |
| Listing Checked On | `checked_on` |

4. Add the working columns: Contact, Status, Quote, Paid, Go-Live Date, Note. Leave them empty. The person fills them in, or the `listicle-outreach` skill does. Status uses the states of that skill. This skill never changes a working column on a refresh.
5. Add two calculated columns:
   - Cost per Citing Answer = Paid ÷ Answers Citing It. Leave it empty when Paid is empty.
   - Answers Naming You Since Go-Live. For a row with a Go-Live Date, copy the row's `answers_filter` into `get_answers`, set `since` to that date, and add `named: true`. Write `total`.
6. Above the table, write the counted period from `counted.window`: the `rule`, then `from` and `to` as dates, then the number of scans in `counted.scans`.
7. Sort by Answers Citing It, largest first.

## Refresh the sheet

Do this when the person asks to refresh or update the sheet.

1. Read the Page column. Call `get_sources` with `page_urls` for those pages, 50 in each call. Do it for both question scopes.
2. Match each returned row to a sheet row by `url`. Rewrite only the Frontmost AI columns and the two calculated columns.
3. Keep every other cell as the person typed it. Keep the row order.
4. A page in `not_found` keeps its row. Write "No current read" in Lists You.
5. Call `get_sources` with no `page_urls`, for all questions. Add a row for each page in `pages_to_get_on` that the sheet does not have.
6. Rewrite the counted period above the table.

## Rules

- A page with `you` equal to Check needed is not confirmed. Never tell the person to pitch it before a check.
- Report each count with its total, such as "16 of 160 answers".
- Keep the two question scopes in two columns. Never add them.
- "Answers Naming You Since Go-Live" shows what happened after the date. It does not prove that the listing caused it. Say so once below the table.
- Say the date in `checked_on` when it is more than 7 days old.
- Never suggest paid links, fake reviews, fake accounts, or a promised result. A quote for a sponsored listing is the person's decision. Never ask a publisher to hide that a listing is paid.
- Ask before you change anything in Frontmost AI. This sheet reads only.

## Output

A spreadsheet file with one table, the counted period above it, and a link to the `url` of the Sources tab. If the AI app cannot make a file, return the same table as CSV.
