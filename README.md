# Karve skills

Claude skills for [Karve](https://karvejobs.com): find and assess UK jobs from your own Claude, using Karve's structured job data.

A skill is a set of instructions your Claude follows. It does the thinking, and the Karve connector supplies the job data.

> **Status:** early. No skills are published yet. The first one, a CV-to-jobs matcher, is in development.

## Planned skills

| Skill | What it does |
|---|---|
| `karve-job-fit` | Reads your CV, searches Karve, and gives an honest, ranked shortlist with matched skills and real gaps |

More may follow, depending on what people find useful.

## Requirements

- Claude (claude.ai, Claude Desktop or Claude Code) with **code execution** enabled
- The Karve connector added to your Claude
- A CV you're happy to share with your Claude

## Installing a skill

Once a skill is released:

1. Download its zip from the [Releases](../../releases) page.
2. In Claude, go to **Customize > Skills > Upload a skill** and choose the zip.
3. Ask Claude to find jobs that match your CV.

## Scope

This repository holds the skills only. The Karve job data and the connector are a separate service, and the MIT licence here covers the skills, not the data or the service.

## Licence

[MIT](LICENSE)
