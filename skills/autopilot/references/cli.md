# Autopilot with the Frontmost AI CLI

Use the CLI when the Frontmost AI connector is not available, for example in a scheduled run in a terminal. The CLI reads the same data as the connector and returns the same fields.

## Check the CLI

1. Run `frontmost whoami --json`.
2. If the command is not found, give the person these two commands, and stop:

   ```bash
   curl -fsSL https://frontmost.ai/install | bash
   frontmost login
   ```

3. If it says "Not signed in" or returns `unauthorized`, give the person `frontmost login`, and stop. A scheduled run can use an API key in the `FRONTMOST_API_KEY` environment variable instead.
4. If it returns `plan_required`, say that Autopilot needs a paid Frontmost AI plan, and stop.

Add `--json` to every command, and read the fields that the steps name. Add `--project <project-id>` when the workspace has more than one project. A scan command with no scan ID reads the newest delivered scan.

## Tool to command

| Connector tool | CLI command |
|---|---|
| `list_projects` | `frontmost projects --json`. Each project has `run_config` and `next_scan`. `frontmost scans --json` lists the delivered scans, newest first |
| `get_scan` | `frontmost scans get [scan-id] --json` |
| `get_readiness` | `frontmost scans readiness [scan-id] --json` |
| `get_questions` | `frontmost scans questions [scan-id] --questions unbranded --json` |
| `get_sources` | `frontmost scans sources [scan-id] --json` |
| `get_queries` | `frontmost scans queries [scan-id] --questions unbranded --json` |
| `get_answers` | `frontmost scans answers [scan-id] --json`. For an `answers_filter`, give each of its fields as a flag: `page_url` is `--page-url`, `reach_result_id` is `--reach-result-id`. Use `--cursor` with `next_cursor` for the next page. With `answer_id`, use `frontmost answers get <answer-id> --json` |
| `get_brief` | `frontmost brief --json` |
| `update_project` | `frontmost projects update [project-id] --cadence <daily\|mwf\|weekly\|off>` |
| `update_recommendations` | `frontmost recommendations done <id>` |

The same approval rules apply. A command that changes the project needs the person's yes in a chat, as the tool does.

If a command fails, write its error code and message in `log.md`. Do not fill the gap with a guess.
