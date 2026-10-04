# Changelog

## Unreleased

- Sharing: turning a ShowDoc share link or a crew link off now pauses it; turning it on again resumes the same URL. Replacing a link (confirm) breaks the old URL. `get_share_status` reports on, paused or none for every link.
- Files: `list_storage_options` (Fast Storage and Google Drive availability, quota, Drive folder); `attach_file_to_section` now needs `target` (`fast_storage` or `google_drive`), takes `contentBase64` (up to 25 MB) or an https `sourceUrl`, refuses executables and scripts, and defaults to the single Files section; `list_attachments`; `remove_attachment` (off by default; Drive files stay in Drive unless `deleteFromStorage: true`).
- Show runs: over/under is correct across midnight. Rows report `startDayOffset`/`endDayOffset`, totals report `calculatedEndDayOffset`/`plannedEndDayOffset`, and the app shows "(+1)".
- Hidden sections: `add_section`, `add_sections` and `update_section` take `hidden`, `get_playbook` returns `hidden` per section, and the new `set_section_visibility` hides a section from crew and share links (owner only) so the owner can review it first.
- The connector now has a toolset version (v1.2.0) and the built-in `get_connector_updates` tool.
- README: the tool list now matches the live connector (toolset v1.2.0): 51 actions in groups (6 destructive actions off by default) plus the built-in `get_connector_updates` and `submit_feedback`, including file attachments (Fast Storage or Google Drive, 25 MB inline), hidden sections, move/undo section, duplicate/archive/delete ShowDoc and show run row, column and day editing. `request_feature` is replaced by `submit_feedback`, structured feedback to the ShowDocLive developers about missing tools, bugs or confusing behaviour. `request_feature` still works for older clients.
- Logo: the stacked ShowDocLive wordmark (`assets/logo.png`). The previous symbol is kept at `assets/alternates/logo-symbol.png`.

## 1.0.0

- Initial release: hosted Streamable HTTP MCP server at `https://mcp.showdoclive.com/mcp` with OAuth 2.1 (PKCE S256, client ID metadata documents and dynamic client registration). No API key or client ID to configure.
