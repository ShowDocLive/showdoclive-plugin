# Changelog

## 1.7.0 (2026-10-25)

Listing updated for toolset v1.34.0: README tool list regenerated from the live connector (172 actions, grouped), rehearsal-only note for live control; changelog entries added for toolsets 1.27.0-1.34.0.

### Toolset 1.34.0 (2026-10-25)

- Live show control for rehearsals: read where the show is, start and end a rehearsal, GO, stop, resume, keep to time and set the timer mode. You can only drive a rehearsal you started; a real live show answers 403 LIVE_CONTROL_REHEARSAL_ONLY.
- Added: `show_run_go`, `show_run_keep_to_time`, `show_run_live_get`, `show_run_rehearsal_end`, `show_run_rehearsal_start`, `show_run_set_timer_mode`, `show_run_start`, `show_run_stop`
- Changed: `submit_feedback`

### Toolset 1.33.0 (2026-10-25)

- One-call tools for diagrams (rename with baseRev, soft delete with restore, PDF link, relink), patch check, groups, cables, knowledge, address book, saved shows and mic edit locks. Creates take an idempotencyKey; destructive tools are off by default.
- Added: `address_book_add_note`, `address_book_create`, `address_book_delete`, `address_book_get`, `address_book_list`, `address_book_merge`, `address_book_set_project_role`, `address_book_suggestion_accept`, `address_book_suggestion_dismiss`, `address_book_suggestions`, `address_book_update`, `cable_create`, `cable_delete`, `cable_update`, `contact_remove_photo`, `diagram_delete`, `diagram_get_meta`, `diagram_pdf`, `diagram_rename`, `equipment_group_create`, `equipment_group_delete`, `equipment_group_update`, `knowledge_delete`, `mics_share_lock_get`, `mics_share_lock_set`, `patch_get`, `patch_reset`, `patch_set`, `project_rename`, `show_run_archive_delete`, `show_run_archive_get`, `show_run_archive_save`, `show_run_archives_list`, `system_relink`
- Changed: `diagrams_list`, `submit_feedback`

### Toolset 1.32.0 (2026-10-25)

- Wireless and kits: equipment carries structured RF bands, kits and needs; diagrams pair transmitters with receivers and suggest missing gear; mics on a diagram can be added to the rundown's mic list (Add from diagram).
- Added: `mics_diagram_preview`, `mics_import_from_diagram`, `system_wireless`
- Changed: `equipment_create`, `equipment_update`, `submit_feedback`, `system_add_devices`

### Toolset 1.31.2 (2026-10-25)

- The built-in mic types can be replaced per project (e.g. Lapel with Countryman E6, label E6), hidden, and restored; assignments carry over. Removing an own type no longer needs its counts at 0 first, only no assigned mics.
- Changed: `mics_get`, `mics_set_inventory`

### Toolset 1.31.1 (2026-10-25)

- Projects can have their own mic types besides HH, LAP and HS (e.g. Countryman, Gooseneck, IEM). mics_set_inventory adds, renames and removes them with micTypes; mics_get lists them in plan.types.
- Changed: `mics_get`, `mics_set_inventory`

### Toolset 1.31.0 (2026-10-22)

- Mic'd: read and plan speaker mics per day (inventory per type, who has which mic, live availability with changeover gaps, conflicts and reallocation suggestions).
- Added: `mics_assign`, `mics_get`, `mics_set_inventory`
- Changed: `submit_feedback`

### Toolset 1.30.0 (2026-10-21)

- Contacts are now a full address book: search, read, notes, merge and a per-ShowDoc role (e.g. Lead Facilitator on one show, Presenter on another), separate from the global title.
- Added: `contact_add_note`, `contact_get`, `contact_merge`, `contact_search`, `contact_set_role`
- Changed: `contact_create`, `contact_delete`, `contact_list`, `contact_update`, `contact_usage`, `submit_feedback`, `contact_set_photo`

### Toolset 1.29.0 (2026-10-20)

- Each rundown day now has its own run state (actual times, notes, live progress); a live show stays on its day, so activate_show_run_day works during a show.
- Changed: `activate_show_run_day`

### Toolset 1.28.0 (2026-10-20)

- ShowDoc sections can show a speakers line: photo chips of contacts on the section header, set with set_section_speakers (ids or names; names become contacts).
- Added: `set_section_speakers`
- Changed: `submit_feedback`, `update_section`

### Toolset 1.27.0 (2026-10-20)

- People are contacts now: rundown Responsible / Speakers and schedule Who cells can link contacts (id or name, created when missing) with titles and photos; contacts can be created, edited, checked for usage and deleted.
- Added: `contact_create`, `contact_delete`, `contact_update`, `contact_usage`
- Changed: `add_schedule_rows`, `add_show_run_rows`, `contact_list`, `submit_feedback`, `update_schedule_row`, `update_schedule_rows`, `update_show_run_row`, `update_show_run_rows`

## 1.6.0 (2026-10-19)

Listing updated for toolset v1.26.6: README tool list regenerated from the live connector (114 actions); changelog entries added for toolsets 1.13.0-1.26.6.

### Toolset 1.26.6 (2026-10-19)

- Bots are offline-aware: users may work offline in the PWA (cached, synced later, user-only conflict resolution). On stale reads suggest reconnecting; on 409 re-read and surface both versions, never blind-retry force. Rehearsal actuals stay local; only show actuals sync.

### Toolset 1.26.5 (2026-10-18)

- system_get now shows the crew's on-site patch checklist: which cables are patched or flagged as a problem. Read-only; ticks are made on the phone diagram view.
- Changed: `system_get`

### Toolset 1.26.4 (2026-10-17)

- Visual links now run at right angles with sharp corners and carry an arrowhead at the to end: from → to is the direction (e.g. Zoom host to receiving laptops).
- Changed: `system_update_connection`, `system_visual_link_create`

### Toolset 1.26.3 (2026-10-17)

- Port names are the physical connector only (HDMI In, XLR Out, USB 1, USB-C), never what is connected. The library is deduplicated: one item per real device type, so search and reuse instead of adding variants.
- Changed: `equipment_create`, `equipment_update`, `system_get`, `system_update_device`

### Toolset 1.26.2 (2026-10-17)

- Diagram lines default to right angles with sharp corners. Edges you send without edgeStyle or rounded now get edgeStyle=orthogonalEdgeStyle;rounded=0 instead of drawing as straight diagonals; set edgeStyle or rounded yourself to keep another look.
- Changed: `diagram_create`, `diagram_update`

### Toolset 1.26.1 (2026-10-16)

- Visual links: one dot can now carry several links (one host to many remotes), and a link has no label unless the item has a Default link name or one is given.
- Changed: `system_visual_link_create`

### Toolset 1.26.0 (2026-10-16)

- Delete a library item safely: equipment_usage shows where it is used and suggests a replacement; equipment_delete swaps every placed device to the replacement first (off by default).
- Added: `equipment_delete`, `equipment_usage`
- Changed: `submit_feedback`

### Toolset 1.25.0 (2026-10-16)

- Visual links: dashed, labelled lines (Zoom, Teams…) between items that join a call, separate from cables. Turn on visualLink for an item, then add or remove links.
- Added: `system_visual_link_create`, `system_visual_link_remove`
- Changed: `equipment_create`, `equipment_update`, `submit_feedback`

### Toolset 1.24.2 (2026-10-16)

- Ports can be put on a chosen side of the card (left, right, or a split like 2 left and 2 right), and the port list order is the row order on the card; diagrams follow both.
- Changed: `equipment_create`, `equipment_update`

### Toolset 1.24.1 (2026-10-16)

- Runs of show are now shared through their linked ShowDoc's link: create_share_link shares both, and get_share_status returns rundownUrl (the rundown on its own page, same password). Per-rundown crew links are now the older option.
- Changed: `create_crew_share_link`, `create_share_link`, `get_share_status`, `turn_off_crew_share_link`, `turn_off_share_link`

### Toolset 1.24.0 (2026-10-16)

- New get_attachment_download: a 15-minute download URL (no login) for any file card in Fast Storage or Google Drive, with optional inline content for files up to 256 KB.
- Added: `get_attachment_download`
- Changed: `list_attachments`, `submit_feedback`

### Toolset 1.23.0 (2026-10-16)

- Library entries are the one source of truth for port names: equipment_update resyncs every placed device on every diagram by port id (cables survive renames), and system_update_device can set an explicit per-device port name override.
- Changed: `equipment_update`, `system_resync`, `system_update_device`

### Toolset 1.22.0 (2026-10-16)

- Per-port connection lists (system_get io, diagram_lists io), a swap preview (system_swap dryRun) and port-name matching on swaps; quote port names exactly as on the device.
- Changed: `diagram_lists`, `system_get`, `system_swap`

### Toolset 1.21.0 (2026-10-15)

- Users can make their own equipment groups (with a colour); group accepts their names, and equipment_groups lists all groups.
- Added: `equipment_groups`
- Changed: `equipment_create`, `equipment_search`, `equipment_update`, `submit_feedback`

### Toolset 1.20.0 (2026-10-15)

- Equipment has an explicit group (Video, Audio, Lighting, Control, Network, Computers & playback, Power, People, Other) that the left panel groups by.
- Changed: `equipment_create`, `equipment_search`, `equipment_update`

### Toolset 1.19.0 (2026-10-15)

- Equipment no longer has a separate Name: the label is derived from Brand + Model, else Model, else Item Type, plus an optional short variant to tell generic items apart.
- Changed: `equipment_create`, `equipment_search`, `equipment_update`

### Toolset 1.18.0 (2026-10-15)

- People and strict library links: Person items (Presenter, Audio Engineer, Slide Operator…) link with viewing, listening, operating and speaking (never cables); brands and models are only set when known; system_resync brings placed devices in line with their library entry.
- Added: `system_resync`
- Changed: `diagram_lists`, `equipment_create`, `equipment_search`, `equipment_update`, `submit_feedback`, `system_connect`, `system_swap`

### Toolset 1.17.0 (2026-10-15)

- diagram_cleanup now lines devices up by their connection points (up or down only, locked ones stay) so cables run straight.
- Changed: `diagram_cleanup`

### Toolset 1.16.0 (2026-10-15)

- Equipment model audit: equipment_create now keeps type and brand; modelName is brand plus model; a swap brings the new model and keeps function, notes and location; diagram_get shows cable waypoints; diagram_lists returns JSON by default.
- Changed: `diagram_get`, `equipment_get`, `equipment_search`, `system_get`, `system_swap`

### Toolset 1.15.0 (2026-10-15)

- Keep a device function a short card title (e.g. PPT Main, PPT Backup, Operator DSM) and put any longer explanation in the device notes, which show in the side panel. system_add_devices now takes notes and location per device.
- Changed: `system_add_devices`, `system_update_device`

### Toolset 1.14.0 (2026-10-15)

- Devices now have a function (what each one is used for, the card title), a type (Laptop, Projector…) and a model; library entries are models. Kit lists count per model.
- Changed: `diagram_lists`, `equipment_create`, `equipment_search`, `equipment_update`, `system_add_devices`, `system_get`, `system_update_device`

### Toolset 1.13.0 (2026-10-15)

- Cables are routed by the server for you (same router as the editor, now with readable spacing); just say what connects to what. New waypoints option for small route tweaks.
- Changed: `diagram_cleanup`, `system_connect`, `system_update_connection`

## 1.5.0 (2026-10-15)

Listing updated for toolset v1.12.0.

### Toolset 1.12.0 (2026-10-15)

- Shorter connector instructions: detailed guidance moved into the tool descriptions. No rules changed, and no tools were added or removed.
- Changed: `delete_playbook`, `delete_schedule`, `delete_schedule_rows`, `delete_section`, `delete_show_run`, `delete_show_run_column`, `delete_show_run_day`, `get_show_run`, `remove_schedule_location`

## 1.4.0 (2026-10-15)

Listing updated for toolset v1.11.0.

### Toolset 1.11.0 (2026-10-15)

- Diagrams v4: before drawing, ask whether the user wants a block diagram, a full wiring diagram or both. Cables are routed as clean schematic lines and devices can be auto-laid out; locked devices never move: on needsPermission ask the user, then retry with allowMoveLocked.
- Added: `cable_add_length`, `diagram_lists`, `system_insert_converter`, `system_update_device`
- Changed: `diagram_cleanup`, `diagram_export`, `submit_feedback`, `system_add_devices`, `system_connect`, `system_update_connection`

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
