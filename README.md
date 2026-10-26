# Karve skills

Claude skills for [Karve](https://karvejobs.com): find and assess UK jobs from your own Claude, using Karve's structured job data.

A skill is a set of instructions your Claude follows. It does the thinking, and the Karve connector supplies the job data.

> **Status:** early. The first skill, `karve-job-fit`, is available. Feedback is welcome via issues.

## Skills

| Skill | What it does |
|---|---|
| `karve-job-fit` | Reads your CV, searches Karve, and gives an honest, ranked shortlist with matched skills and real gaps |

More may follow, depending on what people find useful.

`karve-job-fit` acts as a strict technical recruiter. It asks for your target level, location and deal-breakers, searches Karve, reads the full listings, scores each role out of 10 against evidence in your CV, and presents a ranked shortlist as a card page with links to apply. It is also open about the free tier, which hides the newest listings.

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

1. Download `karve-job-fit.zip` from the [latest release](../../releases/latest).
2. In claude.ai or Claude Desktop, go to **Settings > Capabilities**, make sure **code execution** is on, then choose **Upload skill** and select the zip. (On some versions the menu is labelled **Customize > Skills**.)
3. Switch the skill on, and check the Karve connector is on in your chat.

## Using it

Start a chat and paste or upload your CV, then ask something like:

> Find me jobs that match my CV.

Claude will ask for your target level, where you want to work, and any deal-breakers (permanent only, no people management, minimum pay and so on). It then searches and gives you a summary table plus a shortlist page. Each card shows the fit score, the five criteria behind it, why it fits, where it falls short, and a **View job and apply** button that opens the listing on Karve.

To get a better shortlist:

- Give it the full CV, not a summary. Scores only credit what the CV evidences.
- Say what level you are aiming for, even if it differs from your current one.
- Expect honest scores. A 7 means a decent match with real gaps, and few roles will score 9 or more.

## Privacy

The skill only reads from Karve and writes the shortlist page in your chat. It is instructed to treat listings and CVs as data, never as instructions, and never to send your CV anywhere. Your CV is shared with Claude in your chat, as with any other message. Shortlist pages may be shared, so they leave out personal details.

## Troubleshooting

- **Claude can't find any Karve tools:** the connector isn't added, or it's switched off for this chat.
- **Claude doesn't ask questions or build the page:** check the skill is switched on, and that code execution is enabled.
- **The skill won't install or run:** code execution must be enabled in your Claude settings.
- **Fewer recent jobs than expected:** the free tier hides the newest listings. Claude reports how many are hidden when Karve provides the count.
- **A job shows as closed:** its application link no longer works, so don't apply through it.

## Scope

This repository holds the skills only. The Karve job data and the connector are a separate service, and the MIT licence here covers the skills, not the data or the service.

## Licence

[MIT](LICENSE)
