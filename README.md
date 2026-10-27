# Metis plugins

Plugins from [Metis Foundry](https://metisfoundry.com) for Codex, ChatGPT, Claude and Claude Code: a citation checker that verifies DOIs, PubMed and arXiv ids, LEIs, company numbers and U.S. case citations at the registries that issue them, and files a signed report anyone can recheck.

## Metis Check

Check the citations in an answer at the registries that issue them: DOI, PubMed, arXiv, ORCID, ROR, ISBN, LEI, ISIN, CUSIP, SEC CIK, EIN, NPI and more. Each identifier comes back in exactly one of four states, settled true, settled false, not decidable or unreachable, and every check ends in a signed report with its own id, a public page, a PDF and a recheck button.

### Codex

```bash
codex plugin marketplace add MetisFoundry/metis-plugins
codex plugin add metis-check@metis
```

Sign in or create a free Metis account when Codex asks (5 checks a month).

### ChatGPT

Metis Check is submitted to the OpenAI plugin directory. Until it is listed, add it as a connector by address in Settings → Connectors: `https://check-api.metisfoundry.com/mcp/check`.

### Claude

In Claude, open Settings → Connectors and choose Metis Check, or add it by address: `https://mcp.metisfoundry.com/mcp`.

### Claude Code

```bash
/plugin marketplace add MetisFoundry/metis-plugins
/plugin install metis-check@metis
```

Or add the server directly:

```bash
claude mcp add --transport http metis-check https://mcp.metisfoundry.com/mcp
```

### Any MCP client

Remote MCP server (OAuth sign-in, free account): `https://check-api.metisfoundry.com/mcp/check`. Registry name `com.metisfoundry/metis-check`.

### Plans

Every account starts with 5 checks a month. Plans and prices: https://check-api.metisfoundry.com/check/plans. One account covers Codex, ChatGPT and Claude.

### Support

hello@metisfoundry.com · Privacy: https://mcp.metisfoundry.com/privacy · Terms: https://mcp.metisfoundry.com/terms

Copyright (c) 2026 Metis Foundry. All rights reserved. The plugin files in this repository may be installed and used with Codex, ChatGPT and Claude; the Metis Check service is operated by Metis Foundry under its terms.

### License

The files in this repository are MIT licensed (`LICENSE`); the Metis Check service is proprietary (`NOTICE.md`).
