# Changelog

## 1.3.0 (2026-10-15)

Listing updated for toolset v1.10.0.

### Toolset 1.10.0 (2026-10-15)

- Contact photos: one photo per person (matched by name) shows next to their name in ShowDocs, rundown people cells, phone views and shares. If you have a photo of someone (attached, a website or LinkedIn), add it with contact_set_photo.
- Added: `contact_list`, `contact_set_photo`
- Changed: `add_schedule_rows`, `add_section`, `add_sections`, `add_show_run_column`, `add_show_run_rows`, `create_schedule`, `create_show_run`, `diagram_update`, `get_playbook`, `get_schedule`, `get_show_run`, `place_content`, `submit_feedback`, `update_schedule_row`, `update_schedule_rows`, `update_section`, `update_show_run_row`, `update_show_run_rows`

## 1.2.0 (2026-10-15)

Listing updated for toolset v1.9.0.

### Toolset 1.9.0 (2026-10-15)

- Diagrams learn the rules: shared drawing rules (Knowledge), per-device rules, a cable library with automatic picks by signal and length, editable connections and a clean-up tool. Signal flow uses library equipment, never plain shapes; inputs left, outputs right.
- Added: `cable_get`, `cable_search`, `diagram_cleanup`, `knowledge_add`, `knowledge_get`, `knowledge_update`, `system_update_connection`
- Changed: `diagram_create`, `diagram_update`, `equipment_create`, `equipment_get`, `equipment_update`, `submit_feedback`, `system_add_devices`, `system_connect`, `system_undo`, `system_validate`

## 1.1.0 (2026-10-14)

Listing updated for toolset v1.8.0: README tool list matches the live connector (destructive actions marked off by default), canonical privacy and terms URLs (https://showdoclive.com/privacy, https://showdoclive.com/terms).

### Toolset 1.8.0 (2026-10-14)

- Equipment and systems for Diagrams: a shared equipment library plus your own devices, device shapes with labelled ports, auto-picked cable connections with automatic swaps when a device is full, plain-language validation, a lossless JSON view of the whole diagram, undo, and server PNG renders.
- Added: `diagram_render_png`, `equipment_create`, `equipment_get`, `equipment_search`, `equipment_update`, `system_add_devices`, `system_connect`, `system_get`, `system_swap`, `system_undo`, `system_update`, `system_validate`
- Changed: `diagram_export`, `submit_feedback`

### Toolset 1.7.0 (2026-10-14)

- Feedback asks you first and records what you tried, what was missing and a suggested change; three delete/remove actions now start switched off; small base64 files only (use upload links).
- Changed: `submit_feedback`, `attach_file_to_section`, `delete_show_run_rows`, `remove_schedule_category`, `remove_schedule_column`

### Toolset 1.6.0 (2026-10-14)

- New Diagrams tools: list, read, create (from Mermaid flowcharts or draw.io XML, auto-laid out, line jumps on every edge), update (merge cells by id or replace) and export draw.io-compatible diagrams.
- Added: `diagram_create`, `diagram_export`, `diagram_get`, `diagram_update`, `diagrams_list`
- Changed: `submit_feedback`

### Toolset 1.5.1 (2026-10-10)

- Schedule durations: the duration text in get_schedule and exports is now H:MM (0:30 = 30 min, 2:30 = 2 h 30). Duration inputs stay numbers and are documented as such.
- Changed: `add_schedule_rows`, `create_schedule`, `export_schedule`, `get_schedule`, `update_schedule_row`, `update_schedule_rows`

### Toolset 1.5.0 (2026-10-10)

- Rundown days can have their own planned start and end (falling back to the show's). Schedules gain colour categories, custom text columns, schedule-wide and per-day notes, and can link to a specific rundown by id.
- Added: `add_schedule_category`, `add_schedule_column`, `remove_schedule_category`, `remove_schedule_column`, `rename_schedule_column`, `update_schedule_category`
- Changed: `add_schedule_rows`, `add_show_run_day`, `create_schedule`, `export_schedule`, `get_schedule`, `get_show_run`, `link_schedule_to_document`, `submit_feedback`, `update_schedule_row`, `update_schedule_rows`, `update_schedule_settings`, `update_show_run_day`, `update_show_run_settings`

### Toolset 1.4.4 (2026-10-10)

- Untimed schedule items with start "", locations in bulk, section headers read and written as sectionTitle, sectionDescription and notes, and multi-day rundown writes no longer restamp other days.
- Changed: `add_schedule_location`, `add_schedule_rows`, `add_show_run_rows`, `create_schedule`, `get_show_run`, `update_schedule_row`, `update_schedule_rows`, `update_show_run_row`, `update_show_run_rows`

### Toolset 1.4.3 (2026-10-09)

- Attach real files without base64: create_attachment_upload gives a one-time URL your computer uploads the raw bytes to with curl. Parallel attaches no longer fail.
- Added: `create_attachment_upload`, `get_attachment_upload`
- Changed: `attach_file_to_section`, `list_storage_options`, `set_file_upload_link`, `submit_feedback`

### Toolset 1.4.2 (2026-10-09)

- New export_schedule returns a whole schedule as JSON or CSV. delete_schedule now refuses to delete the last schedule in a ShowDoc (409 LAST_SCHEDULE).
- Added: `export_schedule`
- Changed: `delete_schedule`, `submit_feedback`

### Toolset 1.4.1 (2026-10-09)

- Schedule fixes: shift_schedule_items toDate keeps time order, from/to reads include overlapping items, move_schedule_row accepts confirmOverwrite, and linking is undoable.
- Changed: `create_schedule`, `get_schedule`, `link_schedule_to_document`, `move_schedule_row`, `shift_schedule_items`, `update_schedule_settings`

### Toolset 1.4.0 (2026-10-09)

- Schedules are ready for bots: per-row conflict checks without baseRev, server-side undo, strict times (HH:MM, durationMinutes) with ISO startAt/endAt, filtered reads, and new tools for shifting items, locations, linking and duplicating.
- Added: `add_schedule_location`, `duplicate_schedule`, `link_schedule_to_document`, `remove_schedule_location`, `rename_schedule_location`, `shift_schedule_items`, `undo_schedule_change`
- Changed: `add_schedule_rows`, `create_schedule`, `delete_schedule_rows`, `get_schedule`, `list_schedules`, `move_schedule_row`, `submit_feedback`, `update_schedule_row`, `update_schedule_rows`, `update_schedule_settings`

### Toolset 1.3.1 (2026-10-08)

- Wording only: the app now calls show runs rundowns (or run of show). Tool titles, descriptions, scopes and server instructions say rundown; tool names, inputs and behaviour are unchanged.
- Changed: `activate_show_run_day`, `add_show_run_column`, `add_show_run_day`, `add_show_run_rows`, `create_crew_share_link`, `create_show_run`, `delete_show_run`, `delete_show_run_column`, `delete_show_run_day`, `delete_show_run_rows`, `duplicate_playbook`, `get_show_run`, `list_schedules`, `list_show_runs`, `move_show_run_row`, `rename_show_run`, `turn_off_crew_share_link`, `undo_show_run_change`, `update_show_run_column`, `update_show_run_day`, `update_show_run_row`, `update_show_run_rows`, `update_show_run_settings`

### Toolset 1.3.0 (2026-10-06)

- Schedules: a clock plan beside the rundown. Each item owns its start time, days sit in the same list, and Grok Bot can read and edit the whole schedule.
- Added: `add_schedule_rows`, `create_schedule`, `delete_schedule`, `delete_schedule_rows`, `get_schedule`, `list_schedules`, `move_schedule_row`, `update_schedule_row`, `update_schedule_rows`, `update_schedule_settings`
- Changed: `submit_feedback`

## Toolset 1.2.0 (2026-10-04)

- Sharing: turning a ShowDoc share link or a crew link off now pauses it; turning it on again resumes the same URL. Replacing a link (confirm) breaks the old URL. `get_share_status` reports on, paused or none for every link.
- Files: `list_storage_options` (Fast Storage and Google Drive availability, quota, Drive folder); `attach_file_to_section` now needs `target` (`fast_storage` or `google_drive`), takes `contentBase64` (up to 25 MB) or an https `sourceUrl`, refuses executables and scripts, and defaults to the single Files section; `list_attachments`; `remove_attachment` (off by default; Drive files stay in Drive unless `deleteFromStorage: true`).
- Show runs: over/under is correct across midnight. Rows report `startDayOffset`/`endDayOffset`, totals report `calculatedEndDayOffset`/`plannedEndDayOffset`, and the app shows "(+1)".
- Hidden sections: `add_section`, `add_sections` and `update_section` take `hidden`, `get_playbook` returns `hidden` per section, and the new `set_section_visibility` hides a section from crew and share links (owner only) so the owner can review it first.
- The connector now has a toolset version (v1.2.0) and the built-in `get_connector_updates` tool.
- README: the tool list now matches the live connector (toolset v1.2.0): 51 actions in groups (6 destructive actions off by default) plus the built-in `get_connector_updates` and `submit_feedback`, including file attachments (Fast Storage or Google Drive, 25 MB inline), hidden sections, move/undo section, duplicate/archive/delete ShowDoc and show run row, column and day editing. `request_feature` is replaced by `submit_feedback`, structured feedback to the ShowDocLive developers about missing tools, bugs or confusing behaviour. `request_feature` still works for older clients.
- Logo: the stacked ShowDocLive wordmark (`assets/logo.png`). The previous symbol is kept at `assets/alternates/logo-symbol.png`.

## 1.0.0

- Initial release: hosted Streamable HTTP MCP server at `https://mcp.showdoclive.com/mcp` with OAuth 2.1 (PKCE S256, client ID metadata documents and dynamic client registration). No API key or client ID to configure.
