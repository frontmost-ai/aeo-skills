# Example: `mention-check`

This is the set-up from one run on November 13, 2026. The business is invented.

## The request

```text
My business is Acme Invoices, invoicing software for freelancers in the US.
Rivals: FreshBooks, Wave. I use ChatGPT. Set up the check. I will ask the questions myself.
```

## The result

The check is ready for you to run. Read the seven questions first, then ask them in ChatGPT.

| # | Question | Group | In the score? |
|---|---|---|---|
| 1 | What is the best invoicing software for freelancers? | Best choice | Yes |
| 2 | What are good alternatives to FreshBooks for freelancers? | In place of a rival | Yes |
| 3 | How much does invoicing software for a freelancer cost? | Price | Yes |
| 4 | How do I stop chasing clients for late payments as a freelancer? Is there a tool for it? | A problem | Yes |
| 5 | Which invoicing tools for freelancers take card payments and send recurring invoices? | Fit | Yes |
| 6 | What is Acme Invoices and who is it for? | Name | No |
| 7 | Is Acme Invoices a good choice for freelancers? | Name | No |

**Question 5 is a guess.** I do not know which features Acme Invoices has. Replace "card payments and recurring invoices" with a feature that Acme Invoices has.

**Wave has no question.** Question 2 uses FreshBooks only. If you want Wave too, tell me and I will add an eighth question.

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
