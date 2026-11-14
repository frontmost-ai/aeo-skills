# AEO skills for Claude

A Claude Code plugin with 19 skills for AEO (answer engine optimization): the work of getting a business mentioned in the answers of ChatGPT and other AI apps.

Your agent owns your AI search strategy. Claude is the agent, and each skill is a written procedure that it follows for one job. The jobs include a site audit, a page draft, a check of an agency proposal, and outreach to the list articles ("best X tools") that AI apps cite.

- **Free, with Claude alone:** 13 skills. They need no account. Claude needs web access.
- **With a [Frontmost AI](https://frontmost.ai) account:** the other 6 skills. Frontmost AI is a paid service that records AI answers to your buyers' questions. Plans start at $19 a month.

The skills are text files under the MIT license. They run no code.

## Example

A plumber in Austin gets an agency proposal for $2,400 a month. The prompt is "Check this agency proposal", with the proposal text. `tactic-check` returns one row for each item of the proposal. Four of the eight rows:

| # | Tactic in the proposal | Result | Reason | Do this |
|---|---|---|---|---|
| 2 | Guaranteed ChatGPT mentions within 60 days | Unproven | Nobody outside OpenAI controls ChatGPT answers | Ask how the agency measures a mention, and what you get back if the guarantee fails |
| 4 | 25 five-star Google reviews a month from a "reviewer network" | Against a rule and a United States law | The FTC rule on fake reviews, in effect since October 21, 2024. Google forbids content "not based on a real experience" | Ask each customer for an honest review. Give no reward |
| 7 | Add "Best Plumber Austin" to the Google Business Profile name | Against a rule | Google: "Your name should reflect your business's real-world name" | Keep the real name |
| 8 | Let the search crawler of ChatGPT read the site | Reasonable | OpenAI: sites that opt out "will not be shown in ChatGPT search answers" | Keep this item. It is a one-time job, not a monthly cost |

The business and the proposal are invented. Each rule above is quoted from its official page. The [complete result](examples/tactic-check.md) has all eight rows, with the links.

## Install

In a terminal with [Claude Code](https://claude.com/claude-code):

```bash
claude plugin marketplace add frontmost-ai/aeo-skills
```

```bash
claude plugin install frontmost-aeo@frontmost-ai
```

Start a new session and type `/frontmost-aeo:` to list the skills. To run one, type its name, such as `/frontmost-aeo:ai-readiness`. Claude also picks a skill by itself when your request fits one.

For Cursor, Codex, and other AI apps, see [Other AI apps](#other-ai-apps).

## Prompts to start

Have your website address, your category, and two or three rivals ready.

With Claude alone:

```text
Does ChatGPT recommend my business? Set up a mention check for example.com.

Audit example.com for AI search.

Which pages shape the AI answers for <your category>, and which ones leave us out?

Draft a comparison page: us against <rival>.

An agency sent me this AEO proposal. Check each tactic.

Search for the list articles for <your category>. Find the ones that do not list us, and draft a pitch for each one. Send nothing.
```

With Frontmost AI data:

```text
What changed in our AI answers since last week?

Which questions get our rivals mentioned and not us?

Where do we lose to <rival> in ChatGPT, and why?

Build the tracker of the cited pages that leave us out.

What does ChatGPT say about us? Build the sheet so that I can mark what is wrong.
```

## Skills

### Work with Claude alone

| Skill | What you get |
|---|---|
| `mention-check` | A count of how often an AI app mentions you: 5 buyer questions and 2 questions about your name, 3 tries each. You ask the questions, or Claude asks through a browser tool that you gave it |
| `name-check` | Whether AI apps confuse your business with one that has a similar name, and the wording that keeps them apart |
| `ai-readiness` | Whether AI apps can read your site, and the exact change for each problem |
| `site-audit` | A complete audit for AI search: access, indexing, the facts that buyers ask about, and pages that can be quoted |
| `question-drafting` | The buyer questions to track, in the words that buyers use |
| `source-map` | The pages that shape AI answers for your category, whether each one lists you, and how a business gets onto it |
| `listicle-outreach` | Pitches to the list articles that AI apps cite, a decision sheet for each fee offer, one follow-up, and a check of the live page |
| `directory-listings` | Your listings and business profiles, compared with your real facts, with each correction written inside the platform's rules |
| `community-replies` | The Reddit threads for your buyer questions, with honest draft replies for you to post |
| `page-drafting` | A page for your site, written from your own facts: a question page, a comparison, an alternatives page, or a pricing page |
| `customer-survey` | One sign-up question that shows whether AI apps send you customers, with a ready prompt for a coding agent |
| `tactic-check` | Each tactic in an agency proposal or a tool pitch, checked against the platforms' own rules |
| `ai-search-strategy` | What to fix first, and which repeated jobs to run each week |

With Frontmost AI data, `source-map`, `listicle-outreach`, `community-replies`, and `ai-search-strategy` use recorded AI answers in place of a web search or a count by hand.

### Need Frontmost AI data

A scan is one round of your questions, asked to each AI app.

| Skill | What you get |
|---|---|
| `scan-review` | What changed since the last scan, and which rivals gained |
| `question-gaps` | The questions where AI apps mention rivals and not you, with the reason for each |
| `rival-gaps` | Why AI apps mention one rival more than you, and what you can truthfully match |
| `answer-pages` | A plan for a page on your site, built from real AI answers |
| `answer-accuracy` | A spreadsheet of each AI answer that mentions you, for you to mark what is wrong |
| `placement-tracker` | A spreadsheet of the cited pages that do not list you: the rivals on each page, the outreach status, and the answers that mention you after a listing goes live |

Every skill drafts by default. Claude sends a message, adds a tracked question, or changes your project only after you approve that exact action. Claude never pays or accepts a fee, and it never creates an account or accepts terms for you. Those decisions are yours.

## Connect Frontmost AI

Frontmost AI asks AI apps the questions that your buyers ask, on a schedule. For each answer, it records the businesses that the answer mentions and the pages that it cites.

The plugin adds a connector: the link that lets Claude read that data. To sign in:

1. In Claude Code, run `/mcp`.
2. Choose `plugin:frontmost-aeo:frontmost`.
3. Sign in to Frontmost AI in the browser window that opens.

If Frontmost AI is already a connector in your Claude account, the skills use that connector. You do not need to sign in again.

Every plan includes the connector and starts with a 7-day free trial. See [pricing](https://frontmost.ai/pricing).

## Prompts for a routine

The skills set no schedule. Run these by hand, or put them on the scheduler of your AI app. The weekly prompt and the monthly prompt read Frontmost AI data.

For outreach, Claude needs a way to read and send your mail, such as a Gmail connector. With none, it gives you the text to send.

```text
Each week:
Review the latest scan with ai-search-strategy. Report the jobs done, the jobs open, and the first job for next week.

Each weekday:
Read my outreach mailbox. Handle publisher replies with listicle-outreach. Draft the replies and the follow-ups that are due. Send nothing without my approval.

Each month:
Refresh the placement tracker. Read each page with a date in the Go-Live Date column, and confirm that it still lists us.
```

## What our own work taught us

The skills hold the rules that came from Frontmost AI's own counting and outreach.

From counting answers:

- **One answer is not a count.** The same question returns different businesses on each try.
- **A name can be another business.** An answer about Front's shared inbox is not about Frontmost AI. `name-check` tests for it.
- **A link with no name is not a mention.** A name in a criticism does count. See [how we count](https://frontmost.ai/method).
- **A few pages are behind many answers.** One review site was in 16 of 30 answers to mattress questions. See the [example](https://frontmost.ai/solutions/ecommerce).
- **The pages change by country.** The most cited sites for one software category differ between the United States and Germany. See the [example](https://frontmost.ai/solutions/product-strategy).

From outreach:

- **A question is not a go-ahead.** "What is the next step?" does not approve a send or a payment.
- **A price needs the page's own numbers.** When a publisher quotes a fee, compare it with how often AI apps cite that exact article, not the whole site.
- **A receipt is not a listing.** If you pay for a placement, read the live page. Do the same after a publisher says "it is live".
- **An automatic reply is not a reply.** Count only the publishers where a person answered. Report bounces apart.
- **A mention after a listing is not proof that the listing caused it.** Compare dated answers, and say what the data cannot show.

## Other AI apps

Each skill is a folder with a `SKILL.md` file in the open [Agent Skills](https://agentskills.io) format. An AI app that reads that format can use it. To copy the skills into Cursor, Codex, or another coding agent, use the open [skills](https://github.com/vercel-labs/skills) installer:

```bash
npx skills add frontmost-ai/aeo-skills
```

The Frontmost AI connector also works outside Claude Code. See [frontmost.ai/connect](https://frontmost.ai/connect).

## Contribute

A correction or a new skill is welcome. Read [CONTRIBUTING.md](CONTRIBUTING.md) first. Changes are in the [changelog](CHANGELOG.md).

## Privacy

The skills tell Claude to use the tools that you gave it. This is where your data can go:

- **Web pages.** Claude reads public pages, such as your robots.txt file and a publisher's article.
- **Your mailbox.** For outreach, Claude reads the publisher threads. It sends a message from your mailbox, or through a publisher's form, only after you approve that exact message.
- **Your files.** The spreadsheets and the record of your business facts stay in your own files. A tracker can hold a publisher's name and published contact address.
- **AI apps.** For a mention check, the questions go to the AI app that you choose. They do not contain private data.
- **Your customers' answers.** `customer-survey` plans a question for your own product or form. The answers stay in your own systems.
- **Frontmost AI.** The connector sends your requests to Frontmost AI under its [privacy policy](https://frontmost.ai/privacy). Frontmost AI keeps your project data while your account is open.

## License

[MIT](LICENSE)
