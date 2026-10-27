# Publishing Metis Check to the public markets

Run each block from a terminal on this Mac. Nothing here needs a secret typed.

## 1. Codex community marketplace (GitHub, public)

```bash
cd ~/dev/metis-plugins-public && gh repo create MetisFoundry/metis-plugins --public --description "Metis Foundry plugins for Codex and ChatGPT: Metis Check settles citations at the source" --homepage "https://metisfoundry.com" --source . --push
```

Anyone can then run `codex plugin marketplace add MetisFoundry/metis-plugins` and `codex plugin add metis-check@metis`.

## 2. Official MCP Registry (registry.modelcontextprotocol.io)

The namespace `com.metisfoundry` is proven by a DNS TXT record on metisfoundry.com. The signing key is in `~/dev/metis-plugin-state/mcp-registry-key.pem` (made on this Mac, never leaves it).

a. Add this TXT record at the apex of metisfoundry.com in Cloudflare DNS (name `@`, content exactly as printed by the next command):

```bash
mcp-publisher login dns --domain metisfoundry.com --private-key "$(openssl pkey -in ~/dev/metis-plugin-state/mcp-registry-key.pem -outform DER 2>/dev/null | tail -c 32 | xxd -p -c 64)" 2>&1 | head -20
```

The command prints the record value (`v=MCPv1; k=ed25519; p=...`) when the record is missing; once the record resolves, it logs in.

b. Publish:

```bash
cd ~/dev/metis-plugins-public && mcp-publisher publish
```

## 3. OpenAI plugin directory (ChatGPT + Codex) — Paul's OpenAI account

platform.openai.com → organization verification → domain verification for `check-api.metisfoundry.com` (paste the token into the setup page or `secrets.env` as `METIS_OPENAI_APPS_CHALLENGE`) → submit from `notes/plugin-submission-kit-2026-10-26.md`.

## 4. Claude Connectors Directory — Paul's Claude account

claude.ai/directory/manage → edit the in-review Metis submission to the name Metis Check per `notes/claude-directory-listing-kit-2026-10-26.md`.
