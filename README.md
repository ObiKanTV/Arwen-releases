# Arwen

A second-monitor companion for Elite Dangerous on Windows. Arwen reads the game as you play and
keeps what you need in view: where you are and where you're going, your ship and its engineering,
the materials you still need and where to get them, where to mine, what to buy where, your colony
builds and your missions. Ask it questions in plain words, by typing or by voice, and put it on a
Stream Deck if you have one.

Arwen is free, in early access: expect rough edges, and please [report what you find](#help-and-bug-reports).

**[Download the newest version](../../releases/latest)** · [What's new](../../releases)

Not affiliated with or endorsed by Frontier Developments. Elite Dangerous is a trademark of Frontier
Developments plc. See the [disclaimer](DISCLAIMER.md).

- [Install](#install)
- [First start](#first-start)
- [The screen](#the-screen)
- [The views](#the-views)
- [Asking Arwen](#asking-arwen)
- [Stream Deck](#stream-deck)
- [Claude](#claude)
- [Updates](#updates)
- [Settings](#settings)
- [Your data and privacy](#your-data-and-privacy)
- [Help and bug reports](#help-and-bug-reports)

## Install

1. Download `Arwen-Setup-<version>-win-x64.exe` from the [newest release](../../releases/latest).
2. Run it. Windows may warn that the publisher is unknown, because the installer isn't signed yet:
   choose **More info**, then **Run anyway**. Arwen installs for your Windows user only, without
   administrator rights.
3. Pick your options:
   - **Stream Deck plugin**, offered when Stream Deck is installed.
   - **Desktop shortcut**, off by default.
   - **Let Claude use Arwen's tools**, off by default (see [Claude](#claude)).
4. Start Arwen from the Start menu and put its window on your second monitor. It remembers where
   you left it.

You need Windows 10 or 11 (64-bit) and Elite Dangerous on PC: Steam, Epic or Frontier all work.
Arwen's window needs the Microsoft Edge WebView2 Runtime, which Windows 11 and an up-to-date
Windows 10 already have; the installer tells you if it's missing.

To check the download, compare it with `SHA256SUMS.txt` from the same release:
`Get-FileHash .\Arwen-Setup-<version>-win-x64.exe` in PowerShell.

## First start

Arwen finds the game's journal folder by itself and catches up on what you've done. Start the game
and Arwen follows along. Three things are worth setting in **Settings** early:

- **HOME:** your home system. Engineers, market searches and mining spots are planned from there,
  and the Now bar shows how far you are from it. Type a system or use the one you're in.
- **AGENT MODEL:** the model that answers your questions (see [Asking Arwen](#asking-arwen)).
  Everything else works without one.
- **GAME JOURNAL:** only if Arwen says it can't find your journals, for example when the game
  writes them somewhere unusual.

## The screen

- **The Now bar** along the top: your ship, system, station, distance home, fuel, cargo, pips,
  current colony build, mining session and next engineering step. Choose which ones show in
  Settings, NOW BAR.
- **The rail** on the left: one button per view, with Back, Home and Settings. Back (also Alt+Left
  or your mouse's back button) returns to the previous view as you left it; Home goes to your home
  view.
- **The chat** on the right: ask Arwen anything about your game. Hide it when you only want the
  views.
- **The status bar** along the bottom: whether the game, the model and the online services are
  reachable.

Views keep their filters and scroll position when you switch away and back.

## The views

### Now

Where you are, your ship, fuel and cargo, your current route, your open missions (where to go, time left and reward, soonest
to expire first), and the last few things that happened.

### Commander

Your ranks and progress in each, navy ranks, Pilots' Federation, your powerplay power, rank and
merits, your reputation with the superpowers, your squadron, and your statistics.

### Nav

The system you're in, its bodies and stations, and your plotted route leg by leg: the next star,
jumps and distance left. A star you can't scoop fuel from is marked, so you know before you jump.

### Ship

Your ship's loadout and engineering, its power use, and every ship you own with where it's stored.
Arwen remembers your stored ships between sessions; you don't need to open a shipyard first.

### Engineering

Ship and on-foot engineering, from unlocking engineers to the last roll.

- **Ship engineers:** each engineer, whether you've unlocked them, your grade with them, where they
  are and what unlocks them next. Click an engineer to see more.
- **Saved blueprints:** pick the blueprints and grades you want for a ship. Arwen shows what you can
  roll now, and **all materials together**: what your blueprints need, what you hold and what's
  short.
- **The plan:** numbered steps to get there: which engineers to unlock, materials to trade or
  gather, and which engineer to visit for what. It picks the engineers nearest your home, so it
  won't send you to Colonia from the bubble. Progress ticks off as you play.
- **Tech broker:** pin the broker unlocks you want and see what they still need.
- **On foot:** your suits and weapons, with their grade and modification slots (one per grade above
  1, four at G5). Track the grades and modifications you want, and Arwen lists the materials for
  them all together and makes a plan: grades to raise at Pioneer Supplies first, then each
  engineer to unlock in the right order, with how far you are with each invitation, and what to
  apply where. If the game asks for a different amount than Arwen shows, you can correct it.

### Mining

Where to mine, for powerplay merits (reinforce, acquire or undermine) or for profit. Each ring is
paired with a place to sell, and Arwen says whether the sale counts for merits and why. Save one as
a route. **This session** counts tonnes refined and merits earned while you mine.

### Exploration

The system you're in: how much of it you've scanned, each body's scan and mapping, first discovery
and footfall, and what it's worth, with the bodies worth mapping marked. Your unsold exploration
data (lost if you die), exobiology samples on the body you're on, and the systems you've explored.

### Market

- **Buy near me:** where to buy a commodity near you or your home, by pad size and distance.
- **Nearest station with:** a material trader (of any type), technology broker, interstellar
  factors, Universal Cartographics, black market, shipyard, outfitting, repair and more.
- **Where to get a material:** the nearest trader or other source for it.

Any system name can be copied for the galaxy map with one click.

### Routes

Routes you save, from Mining, Engineering or by hand, with stops that tick off as you arrive, and
lists for anything else: shopping lists, bookmarks, notes and checklists.

### Starport

Your colony construction sites: what each still needs, what's delivered, what's in your hold and
how many runs are left. **Supply run** finds where to buy what's missing. **Set as current build**
pins one site to the Now bar and the Stream Deck.

### Log

What happened this session, event by event, and a log of every change made to your plans by you,
the agent or Claude.

## Asking Arwen

Type in the chat, or hold **HOLD TO TALK** (or TALK on the Stream Deck) and speak. Arwen answers
from your game and can open the view that shows the answer. For example:

- "How many merits do I need for rank 34?"
- "Where's the nearest raw material trader?"
- "What do I still need for my FSD blueprint?"
- "Where should I mine Platinum for merits?"

The answers come from a language model you choose in Settings, AGENT MODEL:

- **Local (recommended):** install [Ollama](https://ollama.com) and a model, e.g.
  `ollama pull bonsai-2:9b`. It runs on your PC, or another PC on your network; nothing leaves your
  network.
- **Cloud:** an OpenAI-compatible service or Anthropic, with your own API key. Your question and
  the game data it needs then go to that service.

Voice input runs on your PC's processor, in English. The speech model (about 70 MB) downloads the
first time you use it. The microphone is only open while you hold the key, and nothing is recorded.
Pick the microphone in Settings, VOICE. Arwen doesn't speak its answers yet.

A wrong answer? Press **FLAG** on it; it helps us fix it.

## Stream Deck

With the plugin installed, drag the **Arwen key** onto your keys; each key sets itself up from its
position, and you can change what it does in its settings. Pair the deck once in Arwen's Settings,
STREAM DECK: type the six-digit code into any key's settings.

Keys can open a view, go Back or Home, show live values (fuel, free cargo space, what your colony
build still needs, the next jump with a warning for stars you can't scoop, mining merits), show
your next engineering step, ask Arwen a question of your own, or push-to-talk. The keys follow
Arwen's colours.

## Claude

If you use Claude, it can read your game through Arwen and change your plans, lists and routes,
for example "plan the engineering for my ship". It's off unless you ticked it in the installer;
turn it on in Settings, CLAUDE · MCP, which also has the one-time setup for Claude Code and Claude
Desktop. Changes Claude makes show in the Log view.

## Updates

Arwen checks for a newer version shortly after it starts and asks first: **Update now**, **Later**
or **Skip this version**. Updating downloads the installer, checks it against its published
checksum, closes Arwen, installs with the choices you made before, and starts Arwen again. Your
data stays.

Settings, UPDATES shows your version, has **Check for updates**, and turns the check at start off.
The check asks GitHub for the newest release and sends nothing else.

## Settings

- **Theme:** the HUD colour (presets or your own), the chat terminal's colour, and CRT effects.
- **Game journal**, **Home**, **Now bar**: see above.
- **Startup:** the boot animation and its sound.
- **Agent model**, **Voice**, **Stream Deck**, **Claude · MCP**, **Updates**: see above.

## Your data and privacy

Arwen only reads the files Elite Dangerous writes to your Saved Games folder. It never changes them
and never presses keys in the game.

Everything Arwen keeps stays on your PC, in `%LOCALAPPDATA%\Arwen`: your settings, saved blueprints,
plans, lists and routes, the chat log (kept 30 days; Settings turns it off) and error logs. API keys
and the Stream Deck pairing go to Windows Credential Manager, never to a file.

Arwen goes online only for:

- searches: Spansh, Ardent and EDSM get the system and item you search for;
- a cloud agent model, if you choose one;
- the update check and the voice model download, from GitHub and Hugging Face.

To uninstall: Windows Settings, Apps, **Arwen**, Uninstall. Your data stays in
`%LOCALAPPDATA%\Arwen`, so a reinstall keeps your plans; delete that folder to remove it too.

## Help and bug reports

[Open an issue](../../issues) and say what you did, what you expected and what happened. Please
attach `%LOCALAPPDATA%\Arwen\logs\arwen.log`. For a wrong answer from the agent, the chat log in
`%LOCALAPPDATA%\Arwen\logs\chat` helps too.

## AI disclaimer

AI has been used in the design phase of Arwen: to plan the architecture, and to write code comments
and release notes.

## Licence

Arwen is free to download and use, but not open source: see [LICENSE](LICENSE). Please share the
[releases page](../../releases) rather than the installer. Arwen includes other people's work under
their own licences: see [THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md).
