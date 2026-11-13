# AEO skills for Claude

A Claude Code plugin with 11 skills for AEO (answer engine optimization): the work of getting a business mentioned in the answers of ChatGPT and other AI apps.

Your agent owns your AI search strategy. Each skill is a written procedure for one job in that work. The jobs include a check that AI apps can read your site, outreach to the list articles ("best X tools") that AI apps cite, and a weekly review.

- **With Claude alone:** `ai-readiness`, `question-drafting`, and `listicle-outreach` work. `ai-search-strategy` works in part.
- **With a [Frontmost AI](https://frontmost.ai) account:** all 11 work. Frontmost AI asks AI apps your buyers' questions and records the answers. The skills read that data.

Frontmost AI wrote these skills from its own AI search work.

## Install

In a terminal with [Claude Code](https://claude.com/claude-code):

```bash
claude plugin marketplace add frontmost-ai/aeo-skills
```

```bash
claude plugin install aeo@frontmost-ai
```

Start a new session and type `/aeo:` to list the skills. To run one, type its name, such as `/aeo:ai-readiness`. Claude also picks a skill by itself when your request fits one.

The plugin installs in Claude Code. For other AI apps, see [Other AI apps](#other-ai-apps).

## Prompts to start

Have your website address, your category, and two or three rivals ready.

With Claude alone:

```text
Can ChatGPT read my site? Check example.com.

Which questions should I track for a <your category> business?

Search for the list articles for <your category>. Find the ones that do not list us, and draft a pitch for each one. Send nothing.
```

With Frontmost AI data:

```text
What should I do about AI search this week?

Which pages does ChatGPT cite for my category, and which ones leave us out?

Where do we lose to <rival> in ChatGPT, and why?

A publisher replied to my pitch with a price. Here is the email. Is it worth it?

What does ChatGPT say about us? Build the sheet so that I can mark what is wrong.
```

## Skills

| Skill | What you get | With Claude alone |
|---|---|---|
| `ai-readiness` | Whether AI apps can read your site, and the exact change for each problem | Yes. Claude reads your robots.txt and home page |
| `question-drafting` | The buyer questions to track, in the words that buyers use | Yes |
| `listicle-outreach` | Pitches to the list articles that AI apps cite, a decision sheet for each fee offer, one follow-up, and a check of the live page | Yes, with your own page list or a web search. No counts of how often AI apps cite each page |
| `ai-search-strategy` | What to fix first, and which repeated jobs to run each week | In part: the readiness check and the questions |
| `placement-tracker` | A spreadsheet of the cited pages that do not list you: the rivals on each page, the outreach status, and the answers that mention you after a listing goes live | No |
| `scan-review` | What changed since the last scan, and which rivals gained | No |
| `question-gaps` | The questions where AI apps mention rivals and not you, with the reason for each | No |
| `rival-gaps` | Why AI apps mention one rival more than you, and what you can truthfully match | No |
| `answer-pages` | A plan for a page on your site, built from real AI answers | No |
| `community-replies` | The Reddit threads that AI apps cite, with honest draft replies for you to post | No |
| `answer-accuracy` | A spreadsheet of each AI answer that mentions you, for you to mark what is wrong | No |

A scan is one round of your questions, asked to each AI app.

`ai-readiness` and `listicle-outreach` need web access. `placement-tracker` and `answer-accuracy` write a spreadsheet file.

Every skill drafts by default. Claude sends a message, adds a tracked question, or changes your project only after you approve that exact action. Claude never pays or accepts a fee. That decision is yours.

## Connect Frontmost AI

Frontmost AI asks AI apps the questions that your buyers ask, on a schedule. For each answer, it records the businesses that the answer mentions and the pages that it cites.

The plugin adds a connector: the link that lets Claude read that data. To sign in:

1. In Claude Code, run `/mcp`.
2. Choose `plugin:aeo:frontmost`.
3. Sign in to Frontmost AI in the browser window that opens.

If Frontmost AI is already a connector in your Claude account, the skills use that connector. You do not need to sign in again.

Plans start at $19 a month for 25 questions in ChatGPT. Every plan includes the connector and starts with a 7-day free trial. See [pricing](https://frontmost.ai/pricing).

## Prompts for a routine

The skills set no schedule. Run these by hand, or put them on the scheduler of your AI app.

For outreach, Claude needs a way to read and send your mail, such as a Gmail connector. With none, it gives you the text to send.

```text
Each week:
Review the latest scan with ai-search-strategy. Report the jobs done, the jobs open, and the first job for next week.

Each weekday:
Read my outreach mailbox. Handle publisher replies with listicle-outreach. Draft the replies and the follow-ups that are due. Send nothing without my approval.

Each month:
Refresh the placement tracker. Read each page with a date in the Go-Live Date column, and confirm that it still lists us.
```

## What outreach taught us

`listicle-outreach` is the procedure that we use for our own outreach. These are rules that we added along the way.

- **A question is not a go-ahead.** "What is the next step?" does not approve a send or a payment.
- **A price needs the page's own numbers.** When a publisher quotes a fee, compare it with how often AI apps cite that exact article, not the whole site.
- **A receipt is not a listing.** If you pay for a placement, read the live page. Do the same after a publisher says "it is live".
- **An automatic reply is not a reply.** Count only the publishers where a person answered. Report bounces apart.
- **A mention after a listing is not proof that the listing caused it.** Compare dated answers, and say what the data cannot show.

## Other AI apps

Each skill is a folder with a `SKILL.md` file in the open [Agent Skills](https://agentskills.io) format. An AI app that reads that format can use it. The Frontmost AI connector also works outside Claude Code. See [frontmost.ai/connect](https://frontmost.ai/connect).

## Privacy

The plugin holds text files only. It runs no code of its own. The skills tell Claude to read web pages with the tools that you gave it. For outreach, they also tell it to read your mailbox. The Frontmost AI connector sends your requests to Frontmost AI under its [privacy policy](https://frontmost.ai/privacy).

## License

[MIT](LICENSE)
