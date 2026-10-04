<img src="assets/logo.png" width="96" height="96" alt="ShowDocLive logo">

# ShowDocLive for Grok Bot

Live production playbooks (ShowDocs) for technical crew: sections, templates, run of show and crew share links.

This plugin connects Grok Bot (and other MCP clients) to the hosted ShowDocLive MCP server:

    https://mcp.showdoclive.com/mcp

On first use you sign in with your ShowDocLive account (OAuth 2.1 with PKCE). No API keys are stored in this plugin.
Manage what Grok Bot may do at https://mcp.showdoclive.com/grokbot.

## Requirements

A ShowDocLive **Pro** or **Team** plan (see https://showdoclive.com/pricing.html). Signing in with a Free account shows an upgrade page instead of connecting. Format & Tidy and content placement spend the account's AI credits, as in the app.

## Documentation

https://showdoclive.com/grok-bot.html

## Tools

Toolset v1.2.0: 51 ShowDocLive actions plus 2 built-in tools. The 6 actions marked "(destructive, off by default)" start switched off. Each user can switch any action on or off on their Grok Bot page (https://mcp.showdoclive.com/grokbot), which also shows what's new in each toolset version.

### ShowDocs

- `list_playbooks`: List ShowDocs (read-only)
- `get_playbook`: Read a ShowDoc (read-only)
- `create_playbook`: Create a ShowDoc (writes)
- `duplicate_playbook`: Duplicate a ShowDoc (writes)
- `archive_playbook`: Archive a ShowDoc (writes)
- `unarchive_playbook`: Unarchive a ShowDoc (writes)
- `delete_playbook`: Delete a ShowDoc (destructive, off by default)

### Sections

- `add_section`: Add a section (writes)
- `add_sections`: Add several sections (writes)
- `update_section`: Update a section (writes)
- `set_section_visibility`: Hide or show a section to crew (writes)
- `tidy_section`: Format & Tidy a section (writes)
- `undo_section_change`: Undo last section change (writes)
- `move_section`: Move a section (writes)
- `undo_section_move`: Undo last section move (writes)
- `delete_section`: Delete a section (destructive, off by default)
- `place_content`: Suggest where text belongs (writes)

### Files

Bots can attach files to a section as file cards that crew can download. Before attaching, the bot asks you **"Fast Storage or Google Drive?"** (it never guesses; `list_storage_options` shows what your plan and account allow). Files go to the ShowDoc owner's storage, sent inline as base64 (`contentBase64`, up to **25 MB**) or as a public https link (`sourceUrl`, up to 50 MB) that ShowDocLive downloads. Programs, installers and scripts are refused.

- `attach_file_to_section`: Attach a file (Fast Storage or Google Drive) (writes)
- `list_storage_options`: Where can files go? (read-only)
- `list_attachments`: List file cards (read-only)
- `remove_attachment`: Remove a file card (destructive, off by default)
- `set_file_upload_link`: File Upload Link for a section (writes)

### Templates

- `list_templates`: List templates (read-only)
- `get_template`: Read a template (read-only)
- `create_playbook_from_template`: New ShowDoc from a template (writes)

### Show runs

- `list_show_runs`: List show runs (read-only)
- `create_show_run`: Create a show run (writes)
- `get_show_run`: Read a show run (read-only)
- `add_show_run_rows`: Add show run rows (writes)
- `update_show_run_row`: Edit a show run row (writes)
- `update_show_run_rows`: Edit several show run rows (writes)
- `move_show_run_row`: Move a show run row (writes)
- `delete_show_run_rows`: Delete show run rows (destructive)
- `undo_show_run_change`: Undo the last show run API change (writes)
- `add_show_run_column`: Add a show run column (writes)
- `update_show_run_column`: Edit a show run column (writes)
- `delete_show_run_column`: Delete a show run column (destructive, off by default)
- `rename_show_run`: Rename a show run (writes)
- `update_show_run_settings`: Change show run settings (writes)
- `add_show_run_day`: Add a show day (writes)
- `update_show_run_day`: Rename or date a show day (writes)
- `activate_show_run_day`: Switch the active day (writes)
- `delete_show_run_day`: Delete a show day (destructive, off by default)
- `delete_show_run`: Delete a show run (destructive, off by default)

### Sharing

- `get_share_status`: See share link status (read-only)
- `set_share_run_of_show`: Show or hide run of show on the share link (writes)
- `create_share_link`: Turn on, resume or replace the share link (writes)
- `turn_off_share_link`: Pause the ShowDoc share link (writes)
- `create_crew_share_link`: Turn on, resume or replace a crew link (writes)
- `turn_off_crew_share_link`: Pause a run of show crew link (writes)

### Account

- `account_get`: Read my profile (read-only)

### Built in (always on)

- `get_connector_updates`: What's new in this connector: changes since a toolset version (read-only)
- `submit_feedback`: Send feedback to the ShowDocLive developers: missing tools, bugs, confusing behaviour (replaces `request_feature`, which still works for older clients)

## Network endpoints

- `https://mcp.showdoclive.com` — MCP server and OAuth authorization server (operated by ShowDocLive).

## Credentials

None stored in the plugin. Users sign in through OAuth; tokens stay with the MCP client.

## Privacy Policy

https://showdoclive.com/privacy.html

## Terms of Use

https://showdoclive.com/terms.html

## Support

[info@showdoclive.com](mailto:info@showdoclive.com)

## License

MIT
