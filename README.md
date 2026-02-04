# srv

Local HTTPS dev server for static sites.

## Install

```bash
./srv install
```

## Usage

```bash
srv new mysite        # creates ~/Code/mysite, starts server
srv start             # from project dir
srv stop
srv open              # browser
srv tunnel            # public URL via cloudflare
```

Projects live at `https://<name>.localhost` with auto-HTTPS.

## What you get

- Caddy file server per project
- Central reverse proxy (launchd)
- htmx pre-installed
- Optional cloudflare tunnels

## Commands

| Command | Description |
|---------|-------------|
| `install` | Setup dependencies and proxy service |
| `new <name>` | Scaffold project with htmx template |
| `start` | Start current project's server |
| `stop` | Stop current project's server |
| `list` | Show all projects and status |
| `open` | Open in browser |
| `tunnel` | Quick public URL |
| `tunnel --persist` | Persistent subdomain |
| `proxy start\|stop\|status` | Manage central proxy |
| `remove [name]` | Unregister project |
