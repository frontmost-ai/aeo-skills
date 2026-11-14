---
name: answer-pages
description: "Plan a page on the business's own site from real AI answers: a page for one buyer question, a fair comparison page, a better version of a page that AI apps already cite, or page ideas from the web searches that ChatGPT ran. Use before you write content for AI search. Needs a Frontmost AI project."
---

# Answer pages

Use this guidance to plan a page on the business's own website from the answers that AI apps gave. It covers four jobs: a page for one question, a comparison page, improvements to pages that AI apps already cite, and page ideas from ChatGPT's searches.

## Before you start

This skill reads a Frontmost AI project through the Frontmost AI tools that this plugin connects.

- If a tool returns `setup_required`, give the person the `url` from the result. Stop until they say that set-up is done.
- If a tool returns `plan_required`, say that this data needs a paid Frontmost AI plan, and stop.
- If the Frontmost AI tools are not available, use the `page-drafting` skill. It needs no account. To plan pages from real AI answers, the person connects Frontmost AI: https://frontmost.ai/connect
- Never invent the data, and never fill a gap with a guess.

## Read the answers first

1. Call the tool for the job: `get_questions` for a page for one question, `get_rivals` for a comparison page, `get_sources` for pages that AI apps already cite, and `get_queries` for page ideas from ChatGPT's searches.
2. Open the real answers. Use `question_id`, `rival_id`, or the row's `answers_filter` in `get_answers`. Do not build a filter.
3. Write down three things: the points that the answers repeat, the facts that they use to compare businesses (price, features, limits, who the product fits), and the format of the pages that they cite (comparison, list, guide, review).

## Plan the page

- **Title**: the buyer's question in plain words.
- **First paragraph**: a direct answer in 2 or 3 sentences that a reader can quote without the rest of the page.
- **Body**: one section for each point that the answers repeat. Put the specific fact first in each section.
- **Facts**: use only facts that the person confirms. When you need a price, a limit, or a feature and you do not have it, ask. Never invent one.

## Job rules

- **One question**: unless the person names one, pick the question with the most answers that name a rival and not the business.
- **Comparison**: take each point from a real answer and show the quote. Include the points where the rival is stronger. A page that hides them is not fair, and readers will see it.
- **Cited pages**: for each of the business's own pages that AI apps cite, say what the answers took from it and what the answers needed and did not find there.
- **Searches**: group ChatGPT's searches by what the buyer wants. Give one page idea for each group. Ask which groups the site already covers before you call a group a gap. When a page on the site already covers the group, add the subject to that page.

## Never suggest

- `llms.txt` files or "AI schema". Google states that its AI features need no new files and no special markup.
- Keyword stuffing, hidden text, or copied text from a rival.
- Any promise that AI apps will cite or mention the page. No method is proven to earn a citation. A page is a bet that the data supports.

## Output

An outline: the title, the first paragraph as a draft, the section headings with one line on what each section must state, and the list of facts that you still need from the person.
