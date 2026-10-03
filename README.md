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

- `list_playbooks` — List ShowDocs (read-only)
- `get_playbook` — Read a ShowDoc (read-only)
- `create_playbook` — Create a ShowDoc (writes)
- `add_section` — Add a section (writes)
- `update_section` — Update a section (writes)
- `tidy_section` — Format & Tidy a section (writes)
- `undo_section_change` — Undo last section change (writes)
- `place_content` — Suggest where text belongs (writes)
- `list_templates` — List templates (read-only)
- `get_template` — Read a template (read-only)
- `create_playbook_from_template` — New ShowDoc from a template (writes)
- `list_show_runs` — List show runs (read-only)
- `create_show_run` — Create a show run (writes)
- `rename_show_run` — Rename a show run (writes)
- `delete_show_run` — Delete a show run (destructive)
- `get_share_status` — See share link status (read-only)
- `set_share_run_of_show` — Show or hide run of show on the share link (writes)
- `create_share_link` — Create or replace the share link (destructive)
- `account_get` — Read my profile (read-only)
- `request_feature` — Request a feature (always available)

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
