<p align="center">
  <img src="assets/logo.png" width="96" height="96" alt="">
</p>

<h1 align="center">HLPlanet Keyboards &amp; Controllers for Cursor</h1>

<p align="center">
  Keyboard size and desk-fit answers from measured data, plus skills for building browser keyboard and gamepad testers.<br>
  By <a href="https://www.hlplanet.com/">HLPlanet</a>, the site that tests Hall effect and TMR keyboards and controllers.
</p>

## What's inside

| Component | What it does |
|---|---|
| **MCP server** `hlplanet` | Runs [hlplanet-mcp](https://github.com/hlplanet/hlplanet-mcp): compare keyboard sizes and 30 measured keyboards, check desk and mousepad fit, find which sizes have a key, search HLPlanet reviews, list HLPlanet's free testing tools |
| **Skill** `keyboard-size-advisor` | Recommends a keyboard size for coding or gaming, including which editor shortcuts (F5, F10, F12...) move to an Fn layer |
| **Skill** `browser-gamepad-input` | Gamepad API patterns: polling, standard mapping, analog triggers, stick drift and circularity tests, built-in deadzone detection, vibration |
| **Skill** `browser-keyboard-testing` | Keyboard tester patterns: `code` vs `key`, keys the browser misses, rollover, chatter, rapid trigger tap tests, SOCD / Snap Tap detection |
| **Rule** `browser-input-handling` | Short checklist of input gotchas the agent applies when it writes keyboard or gamepad code |

The skills describe the techniques behind HLPlanet's free browser tools, which also work as reference implementations:

- [Stick drift and gamepad tester](https://www.hlplanet.com/gamepad-tester/)
- [Online keyboard tester](https://www.hlplanet.com/online-keyboard-tester-tool/) with rollover, chatter, rapid trigger and SOCD tests
- [Keyboard size comparison](https://www.hlplanet.com/keyboard-layout/), drawn to scale
- [Controller reaction time test](https://www.hlplanet.com/controller-reaction-time-test/)
- [Rapid Trigger & SOCD Tester](https://github.com/hlplanet/rt-socd-tester) for Windows and browsers (open source)

## Install

**From the marketplace:** open **Customize** in Cursor, search for "HLPlanet" and select **Install**.

**From this repository:** clone it into your local plugins folder, then run **Developer: Reload Window**:

```bash
git clone https://github.com/hlplanet/hlplanet-cursor-plugin ~/.cursor/plugins/local/hlplanet
```

The MCP server runs with `npx`, so you need Node.js 18 or newer. No API key or account is needed.

## Try it

> "I code all day and play some Valorant. Is a 65% keyboard a bad idea?"
> "Will a TKL and a 45 cm mousepad fit on my 120 cm desk at 30 cm/360?"
> "Add a stick drift test to this controller page."
> "Why does my keyboard tester show keys stuck down after Alt+Tab?"
> "Detect whether a keyboard has SOCD / Snap Tap turned on."

## License

MIT. See [LICENSE](LICENSE).
