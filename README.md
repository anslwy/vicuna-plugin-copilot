# Vicuna plugin: GitHub Copilot harness

Adds the **GitHub Copilot CLI** to [Vicuna](https://github.com/anslwy/vicuna) as a Work harness.
Vicuna runs `copilot --acp --stdio` and talks to it over the
[Agent Client Protocol](https://agentclientprotocol.com) (ACP), the same way it drives
OpenCode, Antigravity and other ACP harnesses.

## Install

1. Install the Copilot CLI and sign in once:
   ```sh
   npm install -g @github/copilot
   copilot login
   ```
   (Or set `COPILOT_GITHUB_TOKEN` / `GH_TOKEN` in your environment.) Make sure `copilot` is on your PATH.
2. In Vicuna: **Settings → Plugins**, paste `anslwy/vicuna-plugin-copilot`, **Install**.
3. Vicuna shows the exact command it will run (`copilot --acp --stdio`). Click **Allow and enable**.
4. Pick **Copilot** in the Work harness picker. Models come from the agent itself.

## Notes

- Tool approvals go through Vicuna: with "Ask before running tools" on, Copilot's
  permission requests show up as Allow / Deny cards; otherwise Vicuna auto-approves them.
- Copilot CLI has no JSON quota command yet, so this plugin adds no Usage tab.
- This plugin ships no program; it only tells Vicuna how to start your own `copilot` CLI.

See [docs.github.com/en/copilot/reference/acp-server](https://docs.github.com/en/copilot/reference/acp-server).
