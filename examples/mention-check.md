# Example: `mention-check`

The first part is the set-up from one run on November 13, 2026, with the rival names changed. The second part shows the count that follows. The business and the rivals are invented.

## The request

```text
My business is Acme Invoices, invoicing software for freelancers in the US.
Rivals: Example Books, Sample Ledger. I use ChatGPT. Set up the check. I will ask the questions myself.
```

## The set-up

The check is ready for you to run. Read the seven questions first, then ask them in ChatGPT.

| # | Question | Group | In the score? |
|---|---|---|---|
| 1 | What is the best invoicing software for freelancers? | Best choice | Yes |
| 2 | What are good alternatives to Example Books for freelancers? | In place of a rival | Yes |
| 3 | How much does invoicing software for a freelancer cost? | Price | Yes |
| 4 | How do I stop chasing clients for late payments as a freelancer? Is there a tool for it? | A problem | Yes |
| 5 | Which invoicing tools for freelancers take card payments and send recurring invoices? | Fit | Yes |
| 6 | What is Acme Invoices and who is it for? | Name | No |
| 7 | Is Acme Invoices a good choice for freelancers? | Name | No |

**Question 5 is a guess.** I do not know which features Acme Invoices has. Replace "card payments and recurring invoices" with a feature that Acme Invoices has.

**Sample Ledger has no question.** Question 2 uses Example Books only. If you want Sample Ledger too, tell me and I will add an eighth question.

### How to ask (3 tries for each of 7 questions = 21 answers)

1. Ask all the questions on the same day, from a place in the US.
2. Open a new temporary chat for each try.
3. Turn search on. Keep an answer only if it shows its sources.
4. Paste the question. Copy the complete answer and its sources into the matching answer file.
5. Fill in one row of the sheet for each answer.

### Files

- `mention-check-2026-11-13.csv`: 21 rows, with the question, the group, and the try filled in.
- `answers/`: 21 empty answer files, from `q1-try1.txt` to `q7-try3.txt`.

### After you ask

Send me the sheet, or the answer files. I count the score out of 15 (questions 1 to 5, 3 tries each). I give the count for each rival, and I list the pages that two or more answers link. Then I name the first job.

I do not answer the questions myself. My own answer is not a data point.

## The count

**Every number in this part is invented, to show the format.** It is not a measurement of ChatGPT. The pages are invented too.

**Acme Invoices is mentioned in 2 of 15 discovery answers.** The discovery answers are the answers to questions 1 to 5, which do not contain your name. ChatGPT with search, November 13, 2026, asked from Austin, Texas, not signed in.

| # | Group | Acme Invoices | Example Books | Sample Ledger |
|---|---|---|---|---|
| 1 | Best choice | 1 of 3 | 3 of 3 | 3 of 3 |
| 2 | In place of a rival | 1 of 3 | 3 of 3 | 2 of 3 |
| 3 | Price | 0 of 3 | 2 of 3 | 3 of 3 |
| 4 | A problem | 0 of 3 | 2 of 3 | 1 of 3 |
| 5 | Fit | 0 of 3 | 3 of 3 | 2 of 3 |
| | **Total** | **2 of 15** | **13 of 15** | **11 of 15** |

**Name questions.** All 6 answers describe Acme Invoices, and none describes a different business.

**Pages that two or more answers link:**

| Page | Answers | Acme Invoices on the page |
|---|---|---|
| `reviews.example/best-invoicing-software-for-freelancers` | 6 | Not present |
| `freelance.example/invoicing-tools-compared` | 4 | Not present |
| `acmeinvoices.example/pricing` | 2 | Present |

**What ChatGPT says about Acme Invoices.** Mark each quote right or wrong:

- "Plans start at $12 a month" (2 answers)
- "Built for small agencies" (1 answer)

**The first job.** If a quote is wrong, correct that fact on your own page first, with `site-audit`. If both are right, get onto the two list pages that leave you out, with `source-map`. Both rivals are in more than half of the discovery answers, and those two pages do not list you.

**Limits.** This count is 15 answers from one day and one place. Answers differ by person, place, and day. A difference of 1 or 2 answers in the next check is normal variation. The count shows what a new buyer can see. It does not show sales.
