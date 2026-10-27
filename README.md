<img src="assets/logo.png" width="96" height="96" alt="ShowDocLive logo">

# ShowDocLive for Grok Bot

Live production playbooks (ShowDocs) for technical crew: sections, files, templates, run of show, schedules, AV signal-flow diagrams with real equipment ports, address book and crew share links.

This plugin connects Grok Bot (and other MCP clients) to the hosted ShowDocLive MCP server:

    https://mcp.showdoclive.com/mcp

On first use you sign in with your ShowDocLive account (OAuth 2.1 with PKCE). No API keys are stored in this plugin.
Manage what Grok Bot may do at https://mcp.showdoclive.com/grokbot.

## Requirements

A ShowDocLive **Pro** or **Team** plan (see https://showdoclive.com/pricing). Signing in with a Free account shows an upgrade page instead of connecting. Format & Tidy and content placement spend the account's AI credits, as in the app.

## Documentation

https://showdoclive.com/grok-bot.html

## What it can do

- **ShowDocs and sections**: read, create, edit, move, hide and tidy sections, with undo and conflict checks so a newer human edit is never overwritten.
- **Files**: upload files from your computer (signed upload link, no base64), attach them to sections, list and download them.
- **Run of show and schedules**: rundowns with days, rows and columns, Mic'd plans, and schedules with locations, categories and export.
- **AV signal-flow diagrams and equipment**: equipment is reality. Devices keep the port names printed on the real gear (USB, HD-SDI, i2Net and so on), two-way ports for USB and network signals, duplicate checks, and reusable "Generic …" items when nothing specific is needed. Grok Bot asks before adding missing gear. Wireless (RF) links are drawn as dotted lines with no cable. Diagrams can be checked, rendered as PNG or PDF, and have cable and equipment lists.
- **Address book and contacts**: people and company contacts, roles on ShowDocs, notes, suggestions and merges; schedule Who links via contacts (company+role or bare role).
- **Sharing**: ShowDoc and crew share links.
- **Live show control, rehearsal only** (see below).

## Tools

Toolset v1.37.0: 176 ShowDocLive actions plus 2 built-in tools, in 11 groups. The 27 actions marked "off by default" start switched off; each user can switch any action on or off on their Grok Bot page (https://mcp.showdoclive.com/grokbot), which also shows what's new in each toolset version.

**Live show control is rehearsal-only.** Grok Bot can start, run and end a rehearsal it started itself (`show_run_rehearsal_start`); on a real live show every live-control action answers 403 `LIVE_CONTROL_REHEARSAL_ONLY` and the show stays with the human show caller. `show_run_go` and `show_run_stop` are off by default and need `confirm`.

### ShowDocs

- `list_playbooks` — List ShowDocs (read-only)
- `get_playbook` — Read a ShowDoc (read-only)
- `contact_set_photo` — Set a contact's photo (writes)
- `contact_list` — List contacts (read-only)
- `contact_create` — Add a contact (writes)
- `contact_update` — Edit a contact (writes)
- `contact_search` — Search contacts (read-only)
- `contact_get` — Read a contact (read-only)
- `contact_set_role` — Set a contact's role on a ShowDoc (writes)
- `contact_add_note` — Add a note to a contact (writes)
- `contact_merge` — Merge duplicate contacts (destructive, off by default)
- `contact_usage` — Where a contact is used (read-only)
- `contact_delete` — Delete a contact (destructive, off by default)
- `create_playbook` — Create a ShowDoc (writes)
- `duplicate_playbook` — Duplicate a ShowDoc (writes)
- `archive_playbook` — Archive a ShowDoc (writes)
- `unarchive_playbook` — Unarchive a ShowDoc (writes)
- `delete_playbook` — Delete a ShowDoc (destructive, off by default)
- `contact_remove_photo` — Remove a contact photo (destructive, off by default)
- `project_rename` — Rename a ShowDoc (writes)

### Sections

- `add_section` — Add a section (writes)
- `add_sections` — Add several sections (writes)
- `update_section` — Update a section (writes)
- `set_section_visibility` — Hide or show a section to crew (writes)
- `set_section_speakers` — Set a section's speakers (writes)
- `tidy_section` — Format & Tidy a section (writes)
- `undo_section_change` — Undo last section change (writes)
- `move_section` — Move a section (writes)
- `undo_section_move` — Undo last section move (writes)
- `delete_section` — Delete a section (destructive, off by default)
- `place_content` — Suggest where text belongs (writes)

### Files

- `create_attachment_upload` — Upload a file from your computer (writes)
- `get_attachment_upload` — Check an upload (read-only)
- `attach_file_to_section` — Attach a file (Fast Storage or Google Drive) (writes)
- `list_storage_options` — Where can files go? (read-only)
- `list_attachments` — List file cards (read-only)
- `get_attachment_download` — Download a file (read-only)
- `remove_attachment` — Remove a file card (destructive, off by default)
- `set_file_upload_link` — File Upload Link for a section (writes)

### Templates

- `list_templates` — List templates (read-only)
- `get_template` — Read a template (read-only)
- `create_playbook_from_template` — New ShowDoc from a template (writes)

### Show runs

- `list_show_runs` — List rundowns (read-only)
- `create_show_run` — Create a rundown (writes)
- `get_show_run` — Read a rundown (read-only)
- `add_show_run_rows` — Add rundown rows (writes)
- `update_show_run_row` — Edit a rundown row (writes)
- `update_show_run_rows` — Edit several rundown rows (writes)
- `move_show_run_row` — Move a rundown row (writes)
- `delete_show_run_rows` — Delete rundown rows (destructive, off by default)
- `undo_show_run_change` — Undo the last rundown API change (writes)
- `add_show_run_column` — Add a rundown column (writes)
- `update_show_run_column` — Edit a rundown column (writes)
- `delete_show_run_column` — Delete a rundown column (destructive, off by default)
- `rename_show_run` — Rename a rundown (writes)
- `update_show_run_settings` — Change rundown settings (writes)
- `add_show_run_day` — Add a show day (writes)
- `update_show_run_day` — Rename or date a show day (writes)
- `activate_show_run_day` — Switch the active day (writes)
- `delete_show_run_day` — Delete a show day (destructive, off by default)
- `delete_show_run` — Delete a rundown (destructive, off by default)
- `mics_get` — Read the Mic'd plan (read-only)
- `mics_set_inventory` — Set the day's mic inventory (writes)
- `mics_assign` — Assign mics to speakers (writes)
- `mics_diagram_preview` — Preview mics on the diagrams (read-only)
- `mics_import_from_diagram` — Add mics from the diagrams (writes)
- `mics_share_lock_get` — Read the mic edit locks (read-only)
- `mics_share_lock_set` — Set a mic edit lock (writes)
- `show_run_archives_list` — List saved shows (read-only)
- `show_run_archive_get` — Read a saved show (read-only)
- `show_run_archive_save` — Save the show (writes)
- `show_run_archive_delete` — Delete a saved show (destructive, off by default)
- `show_run_live_get` — Read the live show (read-only)
- `show_run_rehearsal_start` — Start a rehearsal (writes)
- `show_run_rehearsal_end` — End the rehearsal (writes)
- `show_run_set_timer_mode` — Set the timer mode (writes)
- `show_run_keep_to_time` — Keep to time (writes)
- `show_run_start` — Start or resume (writes)
- `show_run_go` — GO (destructive, off by default)
- `show_run_stop` — Stop (hold) (destructive, off by default)

### Schedules

- `list_schedules` — List schedules (read-only)
- `create_schedule` — Create a schedule (writes)
- `get_schedule` — Read a schedule (read-only)
- `export_schedule` — Export a schedule (read-only)
- `update_schedule_settings` — Update schedule settings (writes)
- `link_schedule_to_document` — Link a schedule to a document (writes)
- `add_schedule_rows` — Add schedule rows (writes)
- `update_schedule_row` — Edit a schedule row (writes)
- `update_schedule_rows` — Edit several schedule rows (writes)
- `move_schedule_row` — Move a schedule row (writes)
- `shift_schedule_items` — Shift schedule items (writes)
- `delete_schedule_rows` — Delete schedule rows (destructive, off by default)
- `undo_schedule_change` — Undo a schedule change (writes)
- `add_schedule_location` — Add a schedule location (writes)
- `rename_schedule_location` — Rename a schedule location (writes)
- `remove_schedule_location` — Remove a schedule location (destructive, off by default)
- `add_schedule_category` — Add a schedule category (writes)
- `update_schedule_category` — Rename or recolour a category (writes)
- `remove_schedule_category` — Remove a category (destructive, off by default)
- `add_schedule_column` — Add a schedule column (writes)
- `rename_schedule_column` — Rename a schedule column (writes)
- `remove_schedule_column` — Remove a schedule column (destructive, off by default)
- `duplicate_schedule` — Duplicate a schedule (writes)
- `delete_schedule` — Delete a schedule (destructive, off by default)

### Sharing

- `get_share_status` — See share link status (read-only)
- `set_share_run_of_show` — Show or hide run of show on the share link (writes)
- `create_share_link` — Turn on, resume or replace the share link (writes)
- `turn_off_share_link` — Pause the ShowDoc share link (writes)
- `create_crew_share_link` — Older crew link: resume or replace (writes)
- `turn_off_crew_share_link` — Pause a run of show crew link (writes)

### Account

- `account_get` — Read my profile (read-only)

### Diagrams

- `diagrams_list` — List diagrams (read-only)
- `diagram_get` — Read a diagram (read-only)
- `diagram_create` — Create a diagram (writes)
- `diagram_update` — Update a diagram (writes)
- `diagram_export` — Export a diagram (read-only)
- `diagram_render_png` — See a diagram (read-only)
- `knowledge_get` — Get drawing rules (read-only)
- `knowledge_add` — Add a drawing rule (writes)
- `knowledge_update` — Update a drawing rule (writes)
- `diagram_cleanup` — Clean up a diagram (writes)
- `diagram_stacks_list` — List device stacks (read-only)
- `diagram_stack_create` — Stack identical devices (writes)
- `diagram_stack_update` — Rename a stack or change its members (writes)
- `diagram_unstack` — Unstack devices (writes)
- `diagram_lists` — Equipment and cable lists (read-only)
- `diagram_rename` — Rename or move a diagram (writes)
- `diagram_get_meta` — Read a diagram's details (read-only)
- `diagram_delete` — Delete a diagram (destructive, off by default)
- `diagram_pdf` — Get a diagram PDF (read-only)
- `system_relink` — Relink devices to another library item (writes)
- `patch_get` — Read the patch check (read-only)
- `patch_set` — Tick or flag one cable (writes)
- `patch_reset` — Clear every patch tick (destructive, off by default)
- `knowledge_delete` — Delete a knowledge rule (destructive, off by default)

### Equipment

- `equipment_search` — Search equipment (read-only)
- `equipment_groups` — List equipment groups (read-only)
- `equipment_get` — Get a device (read-only)
- `equipment_create` — Create a device (writes)
- `equipment_update` — Update a device (writes)
- `equipment_usage` — Where an item is used (read-only)
- `equipment_delete` — Delete an item (destructive, off by default)
- `system_get` — Read a diagram's system (read-only)
- `system_update` — Replace a diagram from system JSON (writes)
- `system_add_devices` — Add devices to a diagram (writes)
- `system_wireless` — Read a diagram's wireless (RF) picture (read-only)
- `system_connect` — Connect devices (writes)
- `system_visual_link_create` — Add a visual link (writes)
- `system_visual_link_remove` — Remove a visual link (destructive, off by default)
- `system_validate` — Check a system (read-only)
- `system_swap` — Swap a device (writes)
- `system_resync` — Refresh devices from the library (writes)
- `system_undo` — Undo a system change (writes)
- `cable_search` — Search cables (read-only)
- `cable_get` — Get a cable (read-only)
- `system_update_connection` — Update a connection (writes)
- `system_update_device` — Update a device on a diagram (writes)
- `system_insert_converter` — Insert a converter (writes)
- `cable_add_length` — Save a cable length (writes)
- `equipment_group_create` — Add an equipment group (writes)
- `equipment_group_update` — Rename or recolour a group (writes)
- `equipment_group_delete` — Delete an equipment group (destructive, off by default)
- `cable_create` — Add a cable type (writes)
- `cable_update` — Change a cable type (writes)
- `cable_delete` — Delete a cable type (destructive, off by default)

### Address book

- `address_book_list` — List the address book (read-only)
- `address_book_get` — Read an address book contact (read-only)
- `address_book_create` — Add an address book contact (writes)
- `address_book_update` — Change an address book contact (writes)
- `address_book_delete` — Delete an address book contact (destructive, off by default)
- `address_book_merge` — Merge address book contacts (destructive, off by default)
- `address_book_suggestions` — List address book suggestions (read-only)
- `address_book_suggestion_accept` — Accept a suggestion (writes)
- `address_book_suggestion_dismiss` — Dismiss a suggestion (writes)
- `address_book_set_project_role` — Set an address-book contact's role on a ShowDoc (writes)
- `address_book_add_note` — Add a note to an address-book contact (writes)

### Built in (always on)

- `get_connector_updates` — What's new: toolset version, changelog, deprecated tools and replacements (read-only)
- `submit_feedback` — Send feedback to the ShowDocLive developers: missing tools, bugs, confusing behaviour

The tool list is versioned by the hosted connector. When it changes, connected assistants get `notifications/tools/list_changed`, a one-time connector-updated notice on the first tool result (calls are never refused for an old tool list; only removed or renamed tools are), and can call `get_connector_updates` for the changelog.

## What's new (toolset v1.37.0, 2026-10-27)

- Companies in Contacts (kind person|company) and schedule Who consistency: bots link Who via responsibleContacts; company+role is a company contact with role on the people item; bare roles use asRole; plain responsible auto-links.

## Network endpoints

- `https://mcp.showdoclive.com` — MCP server and OAuth authorization server (operated by ShowDocLive).

## Credentials

None stored in the plugin. Users sign in through OAuth; tokens stay with the MCP client.

## Privacy Policy

https://showdoclive.com/privacy

## Terms of Use

https://showdoclive.com/terms

## Support

[info@showdoclive.com](mailto:info@showdoclive.com)

## License

MIT
