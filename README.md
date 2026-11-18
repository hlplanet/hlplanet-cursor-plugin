<p align="center">
  <img src="assets/logo.png" width="96" height="96" alt="">
</p>

<h1 align="center">HLPlanet Keyboards &amp; Controllers</h1>

<p align="center">
  Keyboard size and desk-fit answers from measured data, plus skills for building browser keyboard and gamepad testers.<br>
  An agent plugin for Kiro, Hermes Agent, Cursor and other Agent Plugins clients, by <a href="https://www.hlplanet.com/">HLPlanet</a>, the site that tests Hall effect and TMR keyboards and controllers.
</p>

## What's inside

| Component | What it does |
|---|---|
| **MCP server** `hlplanet` | Connects to HLPlanet's hosted server at `https://api.hlplanet.com/mcp` (Streamable HTTP, no sign-in, all tools read-only): compare keyboard sizes and 30 measured keyboards, check desk and mousepad fit, find which sizes have a key, search HLPlanet reviews, list HLPlanet's free testing tools |
| **Skill** `keyboard-size-advisor` | Recommends a keyboard size for coding or gaming, including which editor shortcuts (F5, F10, F12...) move to an Fn layer |
| **Skill** `browser-gamepad-input` | Gamepad API patterns: polling, standard mapping, analog triggers, stick drift and circularity tests, built-in deadzone detection, vibration |
| **Skill** `browser-keyboard-testing` | Keyboard tester patterns: `code` vs `key`, keys the browser misses, rollover, chatter, rapid trigger tap tests, SOCD / Snap Tap detection |
| **Rule** `browser-input-handling` (Cursor only) | Short checklist of input gotchas the agent applies when it writes keyboard or gamepad code |

The skills describe the techniques behind HLPlanet's free browser tools, which also work as reference implementations:

- [Stick drift and gamepad tester](https://www.hlplanet.com/gamepad-tester/)
- [Online keyboard tester](https://www.hlplanet.com/online-keyboard-tester-tool/) with rollover, chatter, rapid trigger and SOCD tests
- [Keyboard size comparison](https://www.hlplanet.com/keyboard-layout/), drawn to scale
- [Controller reaction time test](https://www.hlplanet.com/controller-reaction-time-test/)
- [Rapid Trigger & SOCD Tester](https://github.com/hlplanet/rt-socd-tester) for Windows and browsers (open source)

The MCP server is documented at [api.hlplanet.com/docs/mcp](https://api.hlplanet.com/docs/mcp), next to the free [HLPlanet Keyboard API](https://api.hlplanet.com/) that serves the same data as JSON.

## Install

### Hermes Agent

```bash
hermes plugins install hlplanet/hlplanet-cursor-plugin
hermes plugins enable hlplanet
```

This is a portable Agent Plugins v1 package (`plugin.json` + `mcp.json` + `skills/`), configuration only. The skills load as `hlplanet:keyboard-size-advisor`, `hlplanet:browser-gamepad-input` and `hlplanet:browser-keyboard-testing`.

### Kiro

This repository is a Kiro power. In Kiro, open **Powers**, choose **Add Custom Power** → **Import power from GitHub** and enter:

```text
https://github.com/hlplanet/hlplanet-cursor-plugin
```

Kiro activates the power when you mention keyboard sizes, gamepads, stick drift, rapid trigger or SOCD. The MCP server needs no sign-in.

### Cursor

**From the marketplace:** open **Customize** in Cursor, search for "HLPlanet" and select **Install**.

**From this repository:** clone it into your local plugins folder, then run **Developer: Reload Window**:

```bash
git clone https://github.com/hlplanet/hlplanet-cursor-plugin ~/.cursor/plugins/local/hlplanet
```

### Just the MCP server

Claude: add [HLPlanet Keyboard Sizes](https://claude.ai/directory/hlplanet-keyboard-sizes) from the Claude directory. Claude Code: `claude mcp add --transport http hlplanet https://api.hlplanet.com/mcp`. Other clients: add `{"mcpServers": {"hlplanet": {"url": "https://api.hlplanet.com/mcp"}}}`. To run it locally instead, use `npx -y hlplanet-mcp` ([hlplanet-mcp](https://github.com/hlplanet/hlplanet-mcp)).

## What it connects to

- **Network:** every MCP tool call goes to HLPlanet's server at `api.hlplanet.com` (a Cloudflare Worker, [source](https://github.com/hlplanet/hlplanet-keyboard-api)). `search_hlplanet` passes the search text on to the HLPlanet site search at `www.hlplanet.com`. Nothing else leaves your machine.
- **Accounts and credentials:** none. No API key, sign-in, cookies or stored tokens.
- **Local access:** none. The package runs no commands, reads no files outside itself and starts no background processes.
- **Data:** the server keeps no logs of tool arguments and collects no telemetry.
- **Approvals:** the package marks the server `untrusted` for Hermes. Every tool is annotated read-only, so calls run without prompts.
- **Privacy policy:** [api.hlplanet.com/privacy](https://api.hlplanet.com/privacy)
- **Support:** [pr@hlplanet.com](mailto:pr@hlplanet.com) or [open an issue](https://github.com/hlplanet/hlplanet-cursor-plugin/issues)

## Try it

> "I code all day and play some Valorant. Is a 65% keyboard a bad idea?"
> "Will a TKL and a 45 cm mousepad fit on my 120 cm desk at 30 cm/360?"
> "Add a stick drift test to this controller page."
> "Why does my keyboard tester show keys stuck down after Alt+Tab?"
> "Detect whether a keyboard has SOCD / Snap Tap turned on."

## License

MIT. See [LICENSE](LICENSE).
