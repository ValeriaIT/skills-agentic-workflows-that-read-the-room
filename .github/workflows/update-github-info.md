---
name: update-github-info
description: Draft updates for Mona's GitHub Info site using official GitHub sources and Mona's notes.
model: sonnet-6x
on:
  workflow_dispatch:
  schedule:
    - cron: '17 9 * * *'
safe-outputs:
  create-pull-request:
    title-prefix: "[mona] "
    draft: true
    fallback-as-issue: false
tools:
  edit:
  web-fetch:
network:
  allowed:
    - github.blog
    - github.com
    - awesome-copilot.github.com
---

# Update Mona's GitHub Info website

Read `notes/mona-notes.md` before making changes.

Use the public GitHub sources below and read external guidance with web-fetch:
- GitHub Blog: https://github.blog/latest/
- GitHub Changelog: https://github.blog/changelog/
- Awesome Copilot workflows: https://awesome-copilot.github.com/workflows/

Read repository guidance or reference files with GitHub repository API tools instead of terminal, CLI, or sandboxed commands when you need project-specific context.

Web fetch https://awesome-copilot.github.com/workflows/ as an additional source for curated workflows and practical GitHub Copilot patterns.

Update `site/content/github-info.md` with concise, practical updates for developers. Include the source context when content comes from the GitHub Blog, GitHub Changelog, or Awesome Copilot workflows, and keep the tone aligned with Mona's editorial notes.

Open a pull request for Mona to review. Use `safe-outputs` with `create-pull-request` so the agent proposes changes without writing directly to `main`. The pull request should clearly mention Mona and the GitHub Info content update.
