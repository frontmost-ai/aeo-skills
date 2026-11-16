# Schedule the runs

The schedule only wakes Autopilot. The run decides the work. A run with no new scan ends in a few seconds.

We read the linked pages on November 15, 2026. Products change. Open the page again before you tell the person how a scheduler behaves.

## When to run

Read `run_config.cadence` and `next_scan` from `list_projects`.

| `cadence` | Run |
|---|---|
| `daily` | Each day, two hours after the time of `next_scan` |
| `mwf` | Monday, Wednesday, and Friday, two hours after the time of `next_scan` |
| `weekly` | Monday, two hours after the time of `next_scan`, and once more on Thursday for pull requests that changed |
| `off` | Do not schedule. See step 3 of Set-up |

If the scan is not done, the run skips the scan steps and still reads the pull requests. The next run reads the scan.

## The prompt for each run

Use this text for every scheduler. Replace the path.

```text
Scheduled Autopilot run. In <absolute path of the repository>, follow the autopilot skill of the frontmost-aeo plugin. Nobody is here to answer questions. Stay inside frontmost-autopilot/charter.md. If nothing changed, print one line and end.
```

## Pick the scheduler

Use the first row that fits what the person has. Ask before you create a scheduled task, a workflow file, or a secret. State where it runs and what it can change.

| The person has | Use | It runs when |
|---|---|---|
| The repository on GitHub | A GitHub Actions workflow with a `schedule` trigger | The computer is off. It can open pull requests |
| The Claude desktop app | A Desktop scheduled task | The app is open and the computer is awake |
| The Codex app | A Codex automation | The app is running and the computer is on |
| A terminal only | The person's own cron or launchd with `claude -p` or `codex exec` | The computer is on |

### GitHub Actions

Write `.github/workflows/frontmost-autopilot.yml` in a pull request. It uses `anthropics/claude-code-action` with a `schedule` trigger, `contents: write` and `pull-requests: write` permissions, the `frontmost-ai/aeo-skills` marketplace, and the `frontmost-aeo@frontmost-ai` plugin. Take the current inputs from the page, not from memory: https://code.claude.com/docs/en/github-actions

The workflow needs two secrets. The person adds both. Never ask for a secret in the chat, and never write one to a file.

- The key or token for Claude, as the page describes.
- Access to Frontmost AI for an agent that runs with nobody there. The agent set-up guide gives the steps: https://frontmost.ai/auth.md. The person stores the key as the secret `FRONTMOST_API_KEY`, and the workflow passes it in the `env` of the action step. If the guide does not show how the key reaches the connector, stop and write the blocker for the person. Do not put the key in a file.

A scheduled workflow runs on the default branch only. GitHub turns off the schedules of a public repository after 60 days with no activity. https://docs.github.com/en/actions/reference/workflows-and-actions/events-that-trigger-workflows#schedule

### Claude desktop app

Create a Desktop scheduled task with the prompt above and the repository as its folder. https://code.claude.com/docs/en/desktop-scheduled-tasks

### Codex app

Create an automation with the prompt above, in the project for this repository. https://learn.chatgpt.com/docs/automations

In Codex, the skills come from `npx skills add frontmost-ai/aeo-skills`, and the connector from https://frontmost.ai/connect.

### A terminal only

Give the person one line for their own cron or launchd. Do not edit their crontab.

```bash
cd <absolute path of the repository> && claude -p "<the prompt above>"
```

## What not to use

`/loop` in Claude Code ends when the session closes, and it expires after seven days. It does not keep Autopilot running. https://code.claude.com/docs/en/scheduled-tasks

## After you schedule

Write in `log.md`: which scheduler, when it runs, and how the person removes it. "pause" stops the work, not the schedule.
