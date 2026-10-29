# Third-party notices

Arwen is a private project. This file lists the third-party material that ships inside it.

## Game data: EDDiscovery EliteDangerousCore

`src/Arwen.GameData/Data/materials.json`, `commodities.json`, `blueprints.json`, `experimentals.json`,
`engineers.json`, `modules.json` and `ships.json` are derived from [EliteDangerousCore](https://github.com/EDDiscovery/EliteDangerousCore)
by the EDDiscovery development team, commit `0ee56d0327659dc704ce9540c240e05ef3e7edcd`.

`src/Arwen.GameData/Data/onfoot.json` (on-foot engineering: micro-resources, suit and weapon grade upgrades and
modifications) is built by `tools/gamedata/import_onfoot.py` from EliteDangerousCore's `MCMRType.cs` and
`RecipesEngineering.cs`, commit `dcc810fd26da4212fe3c02060fd0db0cfbff5403`, under the same licence. Changes: converted to
JSON; the suit and weapon makers come from the script's own table; the six maker-only weapon modifications, all named
"…: Kinematic Armaments" in the source, are named after the maker each is for.

`src/Arwen.GameData/ExplorationValue.cs` ports the exploration value formula from EliteDangerousCore's
`EliteDangerous/FrontierData/Enumerations/EstimatedValues.cs` (`ScanEstimatedValues`), commit
`5858d13e398c9c3a41872b8c48e634f55d869038`, under the same licence.

- Licence: Apache License 2.0, full text in [licenses/Apache-2.0-EliteDangerousCore.txt](licenses/Apache-2.0-EliteDangerousCore.txt).
- Copyright 2016-2024 EDDiscovery development team.
- Changes: the C# recipe, material and engineer tables were converted to JSON by
  `tools/gamedata/import_eddiscovery.py`, keeping ship blueprints, experimental effects, ship
  engineering materials, trade commodities (symbol, name, category), engineers, outfitting modules (name, class, rating, mount, mass, power) and ship types (name, pad size). Tech broker, on-foot and suit data were left out, and the
  source's `tbd` placeholder engineers were dropped. One mistake in the source is corrected (the
  script's `CORRECTIONS`): the mine launcher's weapon blueprints, listed a second time under life
  support, are dropped there. No other values were changed.

The game facts themselves (blueprints, materials, engineers) are Frontier Developments' and are
used, as across the Elite Dangerous tool community, for a private, non-commercial tool. Arwen is not
affiliated with or endorsed by Frontier Developments.

## Exobiology data

`src/Arwen.GameData/Data/exobiology.json` is built by `tools/gamedata/import_exobiology.py` from:

- **Species values:** EliteDangerousCore's `EliteDangerous/FrontierData/Enumerations/EstimatedValues.cs`
  (`OrganicEstimatedValues`, the post-Update 14 list), commit `5858d13e398c9c3a41872b8c48e634f55d869038`,
  Apache License 2.0 as above.
- **Minimum distance between samples per genus:** [EDMC-ExplorerLite](https://github.com/dwomble/EDMC-ExplorerLite)
  by dwomble, `explorer/valuation/exobiology_data.py`, commit `7a59187e96588dd1c29f2b4d91516a53e05bef4b`.
  Licence: MIT, full text in [licenses/MIT-EDMC-ExplorerLite.txt](licenses/MIT-EDMC-ExplorerLite.txt).
  Copyright (c) 2026 dwomble. Changes: the table was converted to JSON.

Game facts are Frontier Developments'.

## Fonts

Bundled as woff2 in `web/public/fonts/` (latin and latin-ext subsets, from the Fontsource 5.3.0
packages), all under the SIL Open Font License 1.1:

| Font | Copyright | Licence text |
| --- | --- | --- |
| Saira Semi Condensed | The Saira Project Authors | [licenses/OFL-saira-semi-condensed.txt](licenses/OFL-saira-semi-condensed.txt) |
| IBM Plex Mono | IBM Corp. | [licenses/OFL-ibm-plex-mono.txt](licenses/OFL-ibm-plex-mono.txt) |
| VT323 | The VT323 Project Authors | [licenses/OFL-vt323.txt](licenses/OFL-vt323.txt) |

The fonts are unmodified and are not sold on their own.

## Speech model

Voice input downloads Kroko ASR's English streaming model (2025-08-06) on first use, from the
sherpa-onnx export at huggingface.co/csukuangfj/sherpa-onnx-streaming-zipformer-en-kroko-2025-08-06
(revision 572aaf4e), into `%LOCALAPPDATA%\Arwen\models`. It is not part of Arwen's files.

| Model | Author | Licence |
| --- | --- | --- |
| Kroko ASR, English community model | Banafo | CC BY-SA 4.0 (huggingface.co/Banafo/Kroko-ASR) |

## Packages

NuGet and npm packages keep their licences in their own packages.
