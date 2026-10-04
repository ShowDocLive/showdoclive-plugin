# Changelog

## Unreleased

- README: the tool list now matches the live connector: 35 actions (5 off by default), including move/undo section, duplicate/archive/delete ShowDoc and show run row and column editing. `request_feature` is replaced by `submit_feedback`, structured feedback to the ShowDocLive developers about missing tools, bugs or confusing behaviour. `request_feature` still works for older clients.
- Logo: the stacked ShowDocLive wordmark (`assets/logo.png`). The previous symbol is kept at `assets/alternates/logo-symbol.png`.

## 1.0.0

- Initial release: hosted Streamable HTTP MCP server at `https://mcp.showdoclive.com/mcp` with OAuth 2.1 (PKCE S256, client ID metadata documents and dynamic client registration). No API key or client ID to configure.
