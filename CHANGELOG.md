# Changelog

## 0.4.1 (November 16, 2026)

- `rival-gaps`: the Head to head step is removed. Frontmost AI retired that view, so the result never has it.

## 0.4.0 (November 16, 2026)

`autopilot` and `scan-review` run on the Frontmost AI CLI when the connector is not available.

- `autopilot`: a new file, `references/cli.md`, names the CLI command for each tool that Autopilot calls, and how to install and sign in. Set-up and each run use it when the connector is not available, for example in a scheduled run in a terminal.
- `scan-review`: reads the scan and its answers with the CLI when the connector is not available.
- Needs Frontmost AI CLI 0.7.0 or later.

## 0.3.0 (November 15, 2026)

One new skill, `autopilot`. It needs a Frontmost AI project.

- `autopilot`: runs the AI search strategy without a prompt each time. Set-up writes a charter with the business facts and the limits, and schedules a run after each scan. Each run opens a job only where the data shows its evidence. The limits set the pace, and no calendar does. Assist is the default. Full-send starts only when the person asks.
- `ai-search-strategy`: the head-to-head system is removed.
- `rival-gaps`: Head to head is read only when the result has it.
- README and CONTRIBUTING: `autopilot` is the one skill that sets a schedule, and Full-send is the one exception to drafts by default.

## 0.2.3 (November 14, 2026)

- README: Connect Frontmost AI links the API, the command line, and the new SDKs for TypeScript, Python, and Rust.

## 0.2.2 (November 13, 2026)

Corrections from a cold read of the repository.

- README: the Install section states that the plugin adds the Frontmost AI connector. Row 2 of the example agrees with the complete result. The line under the first skill table names the skills that read a Frontmost AI project.
- `examples/mention-check.md`: shows the count that follows the set-up. The rivals and the numbers in the count are invented.
- `listicle-outreach` and `question-drafting`: the descriptions state that the skill works with no Frontmost AI project.
- Changelog: 0.2.1 has its date, and one line about 0.2.0 is corrected.

## 0.2.1 (November 13, 2026)

Fixes from five test runs. Each run was one complete skill, from the request to the result.

- `source-map`: a page that nobody opened has the result Not opened. When most pages have a count of 1, open the editorial lists and the directories first.
- `name-check`: uses saved answers from a Frontmost AI project when the project has them.
- `directory-listings`: a rule page that does not load is marked "not checked today".

## 0.2.0 (November 13, 2026)

Eight new skills. They need no Frontmost AI account.

- `mention-check`: a count by hand of how often an AI app mentions a business.
- `name-check`: whether AI apps confuse a business with one that has a similar name.
- `site-audit`: a complete site audit for AI search.
- `page-drafting`: a page for the business's own site, written from confirmed facts.
- `source-map`: the pages that shape AI answers for a category.
- `customer-survey`: one question that shows whether AI apps send customers.
- `directory-listings`: listings and business profiles, corrected inside each platform's rules.
- `tactic-check`: an agency proposal or a tool pitch, checked against the platforms' own rules.

Changed:

- `community-replies` and `ai-search-strategy` work with no account, from a web search or a count by hand.
- The six skills that need Frontmost AI data say so in their descriptions. The text of each one names the skill to use with no account.

## 0.1.0 to 0.1.6 (November 13, 2026)

- First release: 11 skills and the Frontmost AI connector.
- Listing fields, the icon, the privacy section of the README, and `SECURITY.md`.
