# srv

Minimal static site development server with HTTPS, htmx, and Cloudflare tunnels.

## Overview

Single bash script that manages static site projects with:
- Per-project file servers via Caddy
- Central reverse proxy for `https://<project>.localhost`
- Project scaffolding with htmx pre-installed
- Optional Cloudflare tunnel integration

## Files

- `srv` - main script (self-contained bash)
- `AGENTS.md` - this file

## Config Locations

- `~/.config/srv/` - config directory
- `~/.config/srv/projects.json` - project registry
- `~/.config/srv/Caddyfile` - central proxy config
- `~/.config/srv/template/` - project template
- `~/.config/srv/config.json` - tunnel settings (optional)
- `~/Library/LaunchAgents/land.charm.srv.proxy.plist` - proxy service

## Dependencies

- `caddy` - web server and reverse proxy
- `gum` - terminal UI styling
- `jq` - JSON processing
- `cloudflared` - tunnel support (optional)

## Commands

```
srv install           # first-time setup
srv new <name>        # create project
srv start             # start current project
srv stop              # stop current project
srv list              # show all projects
srv open              # open in browser
srv tunnel            # quick public URL
srv tunnel --persist  # persistent subdomain
srv proxy <action>    # manage central proxy
srv remove [name]     # unregister project
```

## Development

When modifying:
- Test `srv install` on clean system
- Test full flow: new → start → open → tunnel → stop
- Verify launchd service loads correctly
- Check Caddyfile generation with multiple projects

## Style

- Use gum for styled output when available
- Fallback to basic echo with ANSI colors
- Keep functions small and focused
- Validate inputs early
