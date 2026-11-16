# Contribute

Open an issue for a correction, or a pull request for a change.

## What a skill is

A skill is one folder in `skills/` with a `SKILL.md` file. It is a written procedure for one job. An AI agent follows it for a real business.

## Rules for skill text

1. **One job.** If a skill does two jobs, make two skills.
2. **Each step can be done.** Name what the agent reads, the rule that decides, and what it writes. "Analyze the site" is not a step.
3. **No promise.** Nobody outside an AI company controls its answers. Say what the evidence supports.
4. **A platform rule has its source.** Link the platform's own page, and give the date when you read it. A blog post is not a source for a rule.
5. **No real business data.** Use invented examples. Do not add a real person's name, address, or price offer.
6. **Drafts by default.** A skill sends, posts, pays, or changes an account only after the person approves that exact action. `autopilot` in Full-send merges its own site changes, and only after the person turns that mode on.
7. **Plain words.** Short sentences. Define a term the first time.

## Before you open a pull request

Check the plugin:

```bash
claude plugin validate --strict .
```

Run your skill on an invented business, and read the result:

```bash
claude --plugin-dir . -p "/frontmost-aeo:<skill> <your request>"
```

In the pull request, say what you ran and what the skill returned.

## License

Your contribution is under the [MIT license](LICENSE).
