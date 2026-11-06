# Changelog

## 1.1.0

- The MCP server now connects to HLPlanet's hosted server at https://api.hlplanet.com/mcp, so Node.js is no longer needed.
- Added a portable Agent Plugins v1 package (`plugin.json` + `mcp.json` + `skills/`) for Hermes Agent and other clients. The Cursor manifest reads its MCP config from `.cursor-plugin/mcp.json`.

## 1.0.0

- First release: hlplanet MCP server, keyboard-size-advisor, browser-gamepad-input and browser-keyboard-testing skills, browser-input-handling rule.
