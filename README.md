<img src="assets/logo.png" width="96" height="96" alt="ShowDocLive logo">

# ShowDocLive for Grok Bot

Live production playbooks (ShowDocs) for technical crew: sections, templates, run of show and crew share links.

This plugin connects Grok Bot (and other MCP clients) to the hosted ShowDocLive MCP server:

    https://mcp.showdoclive.com/mcp

On first use you sign in with your ShowDocLive account (OAuth 2.1 with PKCE). No API keys are stored in this plugin.
Manage what Grok Bot may do at https://mcp.showdoclive.com/grokbot.

## Requirements

A ShowDocLive **Pro** or **Team** plan (see https://showdoclive.com/pricing). Signing in with a Free account shows an upgrade page instead of connecting. Format & Tidy and content placement spend the account's AI credits, as in the app.

## Documentation

https://showdoclive.com/grok-bot.html

## Tools

- `list_playbooks` — List ShowDocs (read-only)
- `get_playbook` — Read a ShowDoc (read-only)
- `contact_set_photo` — Set a contact's photo (writes)
- `contact_list` — List contact photos (read-only)
- `create_playbook` — Create a ShowDoc (writes)
- `add_section` — Add a section (writes)
- `add_sections` — Add several sections (writes)
- `update_section` — Update a section (writes)
- `set_section_visibility` — Hide or show a section to crew (writes)
- `tidy_section` — Format & Tidy a section (writes)
- `undo_section_change` — Undo last section change (writes)
- `move_section` — Move a section (writes)
- `undo_section_move` — Undo last section move (writes)
- `delete_section` — Delete a section (destructive, off by default)
- `place_content` — Suggest where text belongs (writes)
- `create_attachment_upload` — Upload a file from your computer (writes)
- `get_attachment_upload` — Check an upload (read-only)
- `attach_file_to_section` — Attach a file (Fast Storage or Google Drive) (writes)
- `list_storage_options` — Where can files go? (read-only)
- `list_attachments` — List file cards (read-only)
- `remove_attachment` — Remove a file card (destructive, off by default)
- `set_file_upload_link` — File Upload Link for a section (writes)
- `list_templates` — List templates (read-only)
- `get_template` — Read a template (read-only)
- `create_playbook_from_template` — New ShowDoc from a template (writes)
- `duplicate_playbook` — Duplicate a ShowDoc (writes)
- `archive_playbook` — Archive a ShowDoc (writes)
- `unarchive_playbook` — Unarchive a ShowDoc (writes)
- `delete_playbook` — Delete a ShowDoc (destructive, off by default)
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
- `get_share_status` — See share link status (read-only)
- `set_share_run_of_show` — Show or hide run of show on the share link (writes)
- `create_share_link` — Turn on, resume or replace the share link (writes)
- `turn_off_share_link` — Pause the ShowDoc share link (writes)
- `create_crew_share_link` — Turn on, resume or replace a crew link (writes)
- `turn_off_crew_share_link` — Pause a run of show crew link (writes)
- `account_get` — Read my profile (read-only)
- `diagrams_list` — List diagrams (read-only)
- `diagram_get` — Read a diagram (read-only)
- `diagram_create` — Create a diagram (writes)
- `diagram_update` — Update a diagram (writes)
- `diagram_export` — Export a diagram (read-only)
- `equipment_search` — Search equipment (read-only)
- `equipment_get` — Get a device (read-only)
- `equipment_create` — Create a device (writes)
- `equipment_update` — Update a device (writes)
- `system_get` — Read a diagram's system (read-only)
- `system_update` — Replace a diagram from system JSON (writes)
- `system_add_devices` — Add devices to a diagram (writes)
- `system_connect` — Connect devices (writes)
- `system_validate` — Check a system (read-only)
- `system_swap` — Swap a device (writes)
- `system_undo` — Undo a system change (writes)
- `diagram_render_png` — See a diagram (read-only)
- `knowledge_get` — Get drawing rules (read-only)
- `knowledge_add` — Add a drawing rule (writes)
- `knowledge_update` — Update a drawing rule (writes)
- `cable_search` — Search cables (read-only)
- `cable_get` — Get a cable (read-only)
- `system_update_connection` — Update a connection (writes)
- `diagram_cleanup` — Clean up a diagram (writes)
- `system_update_device` — Update a device on a diagram (writes)
- `system_insert_converter` — Insert a converter (writes)
- `cable_add_length` — Save a cable length (writes)
- `diagram_lists` — Equipment and cable lists (read-only)
- `submit_feedback` — Send feedback to the ShowDocLive developers: missing tools, bugs, confusing behaviour (always available)
- `get_connector_updates` — What's new: toolset version, changelog, deprecated tools and replacements (read-only, always available)

The tool list is versioned by the hosted connector. When it changes, connected assistants get `notifications/tools/list_changed`, a blocking notice on their next tool call until they refresh the tool list, and can call `get_connector_updates` for the changelog.

## What's new (toolset v1.12.0, 2026-10-15)

Shorter connector instructions: detailed guidance moved into the tool descriptions. No rules changed, and no tools were added or removed.
- Changed: `delete_playbook`, `delete_schedule`, `delete_schedule_rows`, `delete_section`, `delete_show_run`, `delete_show_run_column`, `delete_show_run_day`, `get_show_run`, `remove_schedule_location`

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
