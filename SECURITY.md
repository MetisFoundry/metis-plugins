# Security

This repository holds only the manifests, configuration and skill text that install the Metis Check plugin. It contains no service code and no secrets; secret scanning with push protection is on.

The Metis Check service (https://check-api.metisfoundry.com, https://mcp.metisfoundry.com) is operated by Metis Foundry (I Am Violet Inc.).

## Reporting a vulnerability

Email **hello@metisfoundry.com** with "Security" in the subject. Include what you found, how to reproduce it and, if you have one, a suggested fix. We acknowledge within two business days and keep you informed until it is resolved. Please do not open a public issue for a vulnerability and do not test against other people's accounts or data.

## Scope

In scope: the hosted service endpoints above, this repository's manifests, and the plugin's behaviour inside ChatGPT, Codex, Claude and Claude Code. Out of scope: the registries Metis Check queries (Crossref, PubMed, arXiv, GLEIF and others), which are operated by their issuers.
