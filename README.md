# Arwen

A second-monitor companion for Elite Dangerous. Arwen reads the game as you play and shows where you
are, your ship and its engineering, the materials your saved blueprints still need and where to get
them, mining spots for powerplay merits or profit, market searches, routes and colony builds. A small
local agent answers questions in plain words, and an optional Stream Deck plugin puts views and live
values on keys.

> **Early access.** Arwen is for invited testers. Expect rough edges, and please report what you find
> (see [Feedback](#feedback)).

This repository holds Arwen's downloads only: the installers, their SHA-256 checksums and the release
notes. Arwen's source code is not published. Arwen checks here for updates.

Not affiliated with or endorsed by Frontier Developments. Elite Dangerous is a trademark of Frontier
Developments plc. See [DISCLAIMER.md](DISCLAIMER.md).

## Install

1. Download the newest `Arwen-Setup-<version>-win-x64.exe` from [Releases](../../releases). If you
   like, check it against `SHA256SUMS.txt` from the same release:
   `Get-FileHash .\Arwen-Setup-<version>-win-x64.exe` in PowerShell.
2. Run it. It installs for your Windows user only (no administrator rights), in
   `%LOCALAPPDATA%\Programs\Arwen`.
3. Choose the options you want:
   - **Stream Deck plugin:** offered when Stream Deck is installed. The installer copies the plugin
     into Stream Deck's plugin folder and restarts Stream Deck. In Stream Deck, drag the **Arwen key**
     onto a key, then pair it from Arwen's Settings, STREAM DECK.
   - **Desktop shortcut:** off by default.
   - **Let Claude use Arwen's tools (MCP):** off by default. You can turn it on or off later in
     Settings, CLAUDE · MCP.
4. Start Arwen from the Start menu, ideally on your second monitor.

Windows may warn that the installer is from an unknown publisher; it isn't signed yet. Choose
**More info**, then **Run anyway**.

### Requirements

- Windows 10 or 11, 64-bit.
- The Microsoft Edge WebView2 Runtime, which draws Arwen's window. Windows 11 and up-to-date
  Windows 10 have it; the installer tells you if it's missing.
- Elite Dangerous on PC (Steam, Epic or Frontier: all write the same journals).
- Optional, for the agent: [Ollama](https://ollama.com) with a model, e.g. `ollama pull bonsai-2:9b`.
  The views work without it. A cloud model (OpenAI-compatible or Anthropic) can be picked in
  Settings, AGENT MODEL, with your own API key.

## Updates

From 0.2.7, Arwen looks here for a newer version shortly after it starts and asks before doing
anything: **UPDATE NOW**, **LATER** or **SKIP THIS VERSION**. UPDATE NOW downloads the installer,
checks it against its published SHA-256, closes Arwen, installs the update with the choices you made
before, and starts Arwen again. Your data stays.

Settings, UPDATES shows your version, has **CHECK FOR UPDATES**, and turns the check at start off.
The check sends nothing but a request to GitHub with Arwen's version.

## What Arwen reads and sends

Arwen only reads the files Elite Dangerous writes to your Saved Games folder. It never changes them,
and never presses keys in the game. Look-ups (Spansh, Ardent, EDSM) send only the system and item you
search for.

Everything Arwen stores is on your PC, in `%LOCALAPPDATA%\Arwen`: your settings, saved blueprints,
lists and routes, the agent's chat log (kept 30 days; Settings turns it off) and logs. API keys for a
cloud model and the Stream Deck pairing token go to Windows Credential Manager, never to a file.

## Uninstall

Windows Settings, Apps, **Arwen**, Uninstall. Your data in `%LOCALAPPDATA%\Arwen` stays, so a
reinstall keeps your blueprints; delete that folder to remove it too.

## AI disclaimer

AI has been used in the design phase of Arwen: to plan the architecture, and to write code comments
and release notes.

## Feedback

Tell the person who invited you: what you did, what you expected, and what happened. Please include
`%LOCALAPPDATA%\Arwen\logs\arwen.log`. For agent problems, the chat log
(`%LOCALAPPDATA%\Arwen\logs\chat`) and the FLAG button on an answer help too.

## Licence

Copyright © 2026 ObiKan. All rights reserved; see [LICENSE](LICENSE). Arwen includes other people's
work under their own licences: see [THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md) and
[licenses](licenses/).
