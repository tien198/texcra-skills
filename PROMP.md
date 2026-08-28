Your Pencil MCP is configured as a local STDIO process. Restart it from an external terminal with:

pkill -f '/opt/pencil/resources/app.asar.unpacked/out/mcp-server-linux-x64'

Also restart Pencil itself, because the earlier error showed that MCP could not connect to the desktop app:

pkill -f '^/opt/pencil/pen'
nohup /opt/pencil/pen >/tmp/pencil-desktop.log 2>&1 &

Then restart the Codex session/app. For Codex CLI, exit with Ctrl+C and run:

codex
