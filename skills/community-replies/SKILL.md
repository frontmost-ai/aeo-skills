---
name: community-replies
description: "Find the Reddit and forum threads that shape AI answers where a helpful reply fits, and draft replies that state the writer's real role. Use for Reddit work for AI visibility. Works from a web search, or from the threads that a Frontmost AI project records. Drafts only. The person posts."
---

# Community replies

Use this guidance to plan replies in the Reddit threads that AI apps cite. A reply helps only when it is useful to the people in the thread. A reply that reads as an ad gets removed and can get the account banned.

## 1. Find the threads

Use the best source that you have. Say which one you used.

| Source | How | Limit |
|---|---|---|
| A Frontmost AI project | Call `get_sources` for the project and the scan in the request. Read the subreddits, with `threads_status` and `threads_needing_check`. Open a subreddit with `domain` "reddit.com" and its `subreddit` name | Needs an account |
| A `source-map` or a `mention-check` count | Take the Community rows, or the Reddit addresses in the Linked Pages column | A small sample |
| A web search | Search each buyer question with `site:reddit.com`. Take the threads in the first ten results | These threads stand in for AI citations. You have no citation counts |

If a Frontmost AI tool returns `setup_required`, give the person the `url` from the result. If it returns `plan_required`, say that this data needs a paid Frontmost AI plan. In both cases, continue with a web search.

## 2. Keep the threads that fit

Keep a thread only when all of these are true:

- AI apps cite it in this scan's period, or it is in the search results for a buyer question.
- The thread does not mention the business. A thread that needs a check is not confirmed: read it first.
- The question in the thread is one that the product really answers.
- The thread still takes replies. An archived or locked thread cannot. Say so, and leave it out.

## 3. Read the rules, then draft

Ask who will post, and their role in the business.

Read the subreddit's rules before you draft. If the rules forbid self-promotion, do not draft a reply for that subreddit. Say why. If the rules limit it, quote the limit and ask the person.

Draft one reply for each thread that remains.

## The reply

- First line: the writer's real role, for example "I work at Acme" or "I am the founder of Acme".
- Answer the question first. The answer must help a reader who never tries the product.
- Mention the product once, where it fits the question. Say who it does not fit.
- No link unless the thread asks for one. No sales words.
- Write it for one real person to post from their own account.

## Never suggest

- Fake accounts, more than one account, or coordinated posts.
- A reply that hides the writer's role.
- Requests for upvotes, or replies from employees who pretend to be customers.
- The same reply in more than one thread.
- A post in a thread where the product does not fit the question.
- Any promise that AI apps will mention the business after the reply.

## Rules

- Frontmost AI tools do not open public pages. Read each page with your own web tool. If you cannot open a page, ask the person for its text, and say that you did not read it.
- Draft only. The person posts. Do not post for them.
- Never invent a count, and never fill a gap with a guess.
- Report each number with its counts and its source: AI answers, or web-search results. With a Frontmost AI project, link the `url` of the Sources tab.
- Plan a small number of replies. Three good replies are better than ten that look the same.

## Output

For each thread, up to 5: the thread, why it fits (the count with its source, and the question it asks), the subreddit rule that applies, and the draft reply. Then the threads that you left out, with the reason for each.
