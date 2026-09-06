# Installing PMX Canvas

Use this reference when the `pmx-canvas` skill is installed but the `pmx-canvas` command is not available yet.

## Prerequisites and scope

This vendored skill documents PMX Canvas **0.5.1**, which requires **Bun >=1.3.14**
even when installed through npm. Check `bun --version` first; if missing or older,
follow the [Bun installation guidance](https://bun.sh/docs/installation) with the
user's authorization. Ensure Bun is on the MCP host's PATH, not just an interactive
shell's PATH; use an absolute executable path when necessary.

Install or configure the runtime only when requested. Choose an absolute project
root before starting it, and use a disposable workspace for tests. Do not start a
Canvas in this shared skill directory or copy private boards into it. The examples
pin the documented release; upgrading requires checking runtime schemas and a
reviewed skill refresh, not blindly overwriting this vendored copy.

## From npm

```bash
npm install -g pmx-canvas@0.5.1
export PMX_CANVAS_WORKSPACE_ROOT=/absolute/path/to/project
export PMX_CANVAS_PORT=14313 # Example: choose a free port for this workspace.
unset PMX_CANVAS_URL # A stale URL overrides the CLI port selection.
pmx-canvas serve --daemon --no-open --port="$PMX_CANVAS_PORT" --wait-ms=20000
pmx-canvas serve status
# Confirm the reported workspace equals the selected absolute project root.
pmx-canvas open
```

In a managed environment, use its supervised-service mechanism with foreground
`pmx-canvas serve --no-open` instead of daemonizing. Expose a remote workbench only
through the host's supported authenticated preview mechanism, not a raw loopback URL.

## From a local checkout

```bash
git clone https://github.com/pskoett/pmx-canvas.git
cd pmx-canvas
git checkout 1ca1fc7207d85b266e3463c32ae4e7967b523266
bun install
bun run build
export PMX_CANVAS_WORKSPACE_ROOT=/absolute/path/to/project
export PMX_CANVAS_PORT=14313 # Choose a free port for this workspace.
unset PMX_CANVAS_URL
bun run src/cli/index.ts serve --daemon --no-open --port="$PMX_CANVAS_PORT" --wait-ms=20000
```

For development, run commands through Bun from the checkout:

```bash
bun run src/cli/index.ts status
bun run src/cli/index.ts node add --type markdown --title "Hello" --content "# PMX"
```

## MCP Config

For agents that support MCP, configure PMX Canvas as a stdio MCP server. Replace
the workspace placeholder and example port with the same root and port used by
the workbench. A root alone is not an isolation guarantee: MCP can attach to a
healthy different-workspace daemon on its preferred port. Use a distinct port
for an independent workspace (or deliberately configure
`PMX_CANVAS_ALLOW_WORKSPACE_SPLIT=1`), and always verify the actual target's health
workspace before mutations. Clear a stale inherited `PMX_CANVAS_URL` as well.

```json
{
  "mcpServers": {
    "canvas": {
      "command": "bunx",
      "args": ["pmx-canvas@0.5.1", "--mcp"],
      "env": {
        "PMX_CANVAS_WORKSPACE_ROOT": "/absolute/path/to/project",
        "PMX_CANVAS_PORT": "14313"
      }
    }
  }
}
```

If you are using a local checkout instead of the published package, point the command at the CLI entry:

```json
{
  "mcpServers": {
    "canvas": {
      "command": "bun",
      "args": ["run", "/path/to/pmx-canvas/src/cli/index.ts", "--mcp"],
      "env": {
        "PMX_CANVAS_WORKSPACE_ROOT": "/absolute/path/to/project",
        "PMX_CANVAS_PORT": "14313"
      }
    }
  }
}
```

## Verify

```bash
pmx-canvas --version
pmx-canvas serve status
pmx-canvas layout
```

Before any mutation, verify the returned workspace matches the intended root; a
healthy listener alone is not enough. Stop on mismatch and choose a free port,
then repeat the check. The CLI defaults to `http://localhost:4313`; use
`--port=<free-port>` for server startup and `PMX_CANVAS_PORT=<free-port>` for CLI
and MCP clients. `PMX_CANVAS_URL` can override the CLI target URL.

For a disposable test workspace, `pmx-canvas smoke` exercises the MCP handshake,
temporary-node create/search/remove round trip, and board validation. Inspect
its JSON report and exit status; do not claim success from installation alone.
