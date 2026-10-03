# Security policy

## Reporting a vulnerability

Please report security issues privately to **[info@showdoclive.com](mailto:info@showdoclive.com)** with "Security" in the subject.
Do not open a public issue for security problems.

Please include:

- what is affected: this plugin repo, the hosted MCP server at `https://mcp.showdoclive.com`, or showdoclive.com
- steps to reproduce, and the impact you observed
- how to reach you for follow-up

We aim to acknowledge reports within 3 working days and will keep you updated until the issue is resolved.
Please give us reasonable time to fix an issue before you disclose it publicly.

## Scope

This repository holds only plugin metadata (manifests, README, logo). No code runs from it and it stores no credentials.
The connector runs as a hosted service: users sign in with OAuth 2.1 (PKCE), and tokens are held by the MCP client, never by this plugin.
Supported version: the latest commit on `main`.
