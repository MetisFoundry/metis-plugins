# Metis Check

**Check the citations in an AI answer at the registries that issue them.** DOI, PubMed, arXiv, ORCID, ROR, ISBN, LEI, ISIN, CUSIP, SEC CIK, EIN, NPI, UK company numbers, domains and more. Each identifier comes back in exactly one of four states: settled true, settled false, not decidable (a person decides) or unreachable (a delay, not evidence). Every check ends in a signed report with its own id, a PDF and a recheck button anyone can press.

By [Metis Foundry](https://metisfoundry.com). One account covers ChatGPT, Codex, Claude, Claude Code, Cursor and VS Code. Every account starts with 5 checks a month; [plans](https://check-api.metisfoundry.com/check/plans).

[![A Metis Check report](https://check-api.metisfoundry.com/check/report/MC-ND82-CGEH-PFFH/card.png)](https://check-api.metisfoundry.com/check/report/MC-ND82-CGEH-PFFH)

*A real report: three identifiers settled true, one settled false. [Open it and press Recheck](https://check-api.metisfoundry.com/check/report/MC-ND82-CGEH-PFFH).*

## Install

| Client | How |
|---|---|
| **Claude** (web, desktop, mobile) | Settings → Connectors → add a connector by URL: `https://mcp.metisfoundry.com/mcp`. Once Metis Check is listed in the connectors directory, choose it there. |
| **Claude Code** | `/plugin marketplace add MetisFoundry/metis-plugins` then `/plugin install metis-check@metis`, or `claude mcp add --transport http metis-check https://mcp.metisfoundry.com/mcp` |
| **Codex CLI** | `codex plugin marketplace add MetisFoundry/metis-plugins` then `codex plugin add metis-check@metis` |
| **ChatGPT** | The Metis Check plugin is submitted to the OpenAI directory. Until it is listed: Settings → Connectors → add by address `https://check-api.metisfoundry.com/mcp/check` |
| **Cursor** | [Add to Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=metis-check&config=eyJ1cmwiOiAiaHR0cHM6Ly9jaGVjay1hcGkubWV0aXNmb3VuZHJ5LmNvbS9tY3AvY2hlY2sifQ==) |
| **VS Code** | [Add to VS Code](vscode:mcp/install?%7B%22name%22%3A%20%22metis-check%22%2C%20%22type%22%3A%20%22http%22%2C%20%22url%22%3A%20%22https%3A%2F%2Fcheck-api.metisfoundry.com%2Fmcp%2Fcheck%22%7D) ([web redirect](https://vscode.dev/redirect/mcp/install?name=metis-check&config=%7B%22type%22%3A%20%22http%22%2C%20%22url%22%3A%20%22https%3A%2F%2Fcheck-api.metisfoundry.com%2Fmcp%2Fcheck%22%7D)), or `code --add-mcp '{"name": "metis-check", "type": "http", "url": "https://check-api.metisfoundry.com/mcp/check"}'` |
| **Any MCP client** | Remote server `https://check-api.metisfoundry.com/mcp/check` (OAuth sign-in; a free account is created on first connection). Registry name `com.metisfoundry/metis-check`. |

Sign in or create a free Metis account when the client asks.

## Try it in one click

* [Try it in Claude](https://claude.ai/new?q=Use%20Metis%20Check%20to%20check%20these%20references%3A%2010.1038%2Fs41586-020-2649-2%2C%20PMID%2032939066%2C%20arXiv%3A2005.14165%20and%2010.1000%2Fnot-a-real-doi-9999.%20Give%20me%20the%20report%20link.)
* [Try it in ChatGPT](https://chatgpt.com/?q=Use%20Metis%20Check%20to%20check%20these%20references%3A%2010.1038%2Fs41586-020-2649-2%2C%20PMID%2032939066%2C%20arXiv%3A2005.14165%20and%2010.1000%2Fnot-a-real-doi-9999.%20Give%20me%20the%20report%20link.)

The prompt asks Metis Check to check four references, one of them invented. The invented one comes back settled false, with the registry that said so.

## What you get

* **Four states, nothing hidden**: settled true, settled false, not decidable, unreachable, and a not-checked list with the reason for each.
* **A report that rechecks without Metis**: every line carries the registry query and the SHA-256 of the registry's answer; signed JSON and a PDF.
* **Shareable**: anyone with the link can open the report and press Recheck; the registries are asked again, live.
* **Private**: passages are never stored, only the identifiers, their positions and a hash. Metis never asks for conversation history.
* **Honest scope**: Metis Check establishes that an identifier is registered and what the registry says. It does not decide whether a paper supports a claim.

## Plans

Free: 5 checks a month. Pro: $29 a month (or $276 a year), 2,000 checks, case law included. Team: $249 a month (or $2,388 a year), 15,000 checks, 5 seats. Checks that cannot be settled cost nothing. Details: https://check-api.metisfoundry.com/check/plans

## Repository layout

* `.agents/plugins/marketplace.json` — Codex marketplace (`metis`); plugin in `plugins/metis-check`
* `.claude-plugin/marketplace.json` — Claude Code marketplace (`metis`); plugin manifest in `plugins/metis-check/.claude-plugin`
* `server.json` — official MCP Registry manifest
* `PUBLISH.md` — how the listings are published

## Support and license

hello@metisfoundry.com. The files in this repository are MIT licensed (`LICENSE`); the Metis Check service is proprietary (`NOTICE.md`).
