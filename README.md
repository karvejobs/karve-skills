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
- The Karve connector added to your Claude (see below)
- A CV you're happy to share with your Claude

## Adding the Karve connector

The connector gives your Claude access to Karve's job data. Its address is:

```
https://karvejobs.com/mcp
```

No sign-in is needed at the moment.

**Claude.ai and Claude Desktop**

1. Go to **Customize > Connectors**.
2. Add a custom connector.
3. Paste the address above and save.
4. Make sure the connector is switched on in the chat where you want to use it.

**Claude Code**

```
claude mcp add --transport http karve https://karvejobs.com/mcp
```

**Check it works**

Ask Claude: *What Karve search filters are available?* You should get lists of skills and locations back. The connector may appear under the name "Job Matcher Service". If nothing comes back, the connector isn't connected yet, so fix that before installing a skill.

## Installing a skill

Once a skill is released:

1. Download its zip from the [Releases](../../releases) page.
2. In Claude, go to **Customize > Skills > Upload a skill** and choose the zip.
3. Ask Claude to find jobs that match your CV.

## Troubleshooting

- **Claude can't find any Karve tools:** the connector isn't added, or it's switched off for this chat.
- **The skill won't install or run:** code execution must be enabled in your Claude settings.
- **Fewer recent jobs than expected:** the free tier hides the newest listings. Claude reports how many are hidden when Karve provides the count.
- **A job shows as closed:** its application link no longer works, so don't apply through it.

## Scope

This repository holds the skills only. The Karve job data and the connector are a separate service, and the MIT licence here covers the skills, not the data or the service.

## Licence

[MIT](LICENSE)
