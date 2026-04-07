---
name: df-mod-author
description: Use when creating, modifying, or debugging Dwarf Fortress mods, specifically when working with RAW files, graphics, mod structure, or searching vanilla game data for reference.
---

# Dwarf Fortress Mod Author

## Overview
This skill provides a comprehensive guide for authors creating and managing Dwarf Fortress mods. It covers mod structure, configuration, and how to safely reference vanilla game data.

> [!IMPORTANT]
> **Version Compatibility:** This skill's documentation is current as of **Dwarf Fortress version 53.11**. 
> - **Vanilla Files:** Content in your `data/vanilla` directory may be newer and use tokens that contradict this guide. 
> - **Wiki Content:** The Dwarf Fortress Wiki may contain information for versions newer or older than both this skill and your local game files. Always prioritize empirical evidence from the vanilla RAWs.

## When to Use
- Creating a new Dwarf Fortress mod from scratch.
- Modifying existing RAW objects (creatures, items, entities).
- Adding custom graphics, tilesets, or sprites.
- Cross-referencing vanilla files to avoid token hallucination.

## Mod Structure

Every Dwarf Fortress mod MUST reside in its own folder and follow this standard structure:

| Folder/File | Mandatory | Purpose | Reference |
| :--- | :--- | :--- | :--- |
| `info.txt` | **Yes** | Mod identity, versioning, and compatibility. | [info_txt.md](references/info_txt.md) |
| `objects/` | Optional | Contains text-based RAW files (.txt). | [v50_modding.md](references/v50_modding.md) |
| `graphics/` | Optional | Custom tilesets and sprite definitions. | [graphics.md](references/types/graphics.md) |
| `scripts/` | Optional | Lua scripts (e.g., `init.lua`). | *N/A* |
| `sound/` | Optional | Audio files and music/sound definitions. | *N/A* |
| `preview.png` | Optional | Mod thumbnail (Workshop/Mod Menu). | *N/A* |

## Configuration & Discovery

To research vanilla data, the skill must locate the **Dwarf Fortress Installation Directory**.

### Path Discovery Order
1.  **Memory:** Check `save_memory` for `dwarf_fortress_path`.
2.  **Environment:** Check common installation paths:
    - On Windows:
        - `C:\Program Files (x86)\Steam\steamapps\common\Dwarf Fortress`
    - On Linux:
        - `~/.steam/steam/steamapps/common/Dwarf Fortress`
        - `~/.local/share/Steam/steamapps/common/Dwarf Fortress`
    - On macOS:
        - `~/Library/Application Support/Steam/steamapps/common/Dwarf Fortress`
3.  **User Inquiry:** If not found, ask the user: "Where is your Dwarf Fortress installation directory located?" and save it to memory.

## Locating Vanilla Files

Once the `dwarf_fortress_path` is known, **DO NOT** use Google or external search to find vanilla raw definitions. Always search the local installation.

### Directory Structure (v50+)
Vanilla RAWs are organized into module that follow the same format as mods:
- `<dwarf_fortress_path>/data/vanilla/<module_name>/objects/*.txt`
- `<dwarf_fortress_path>/data/vanilla/<module_name>/graphics/*.txt`
- `<dwarf_fortress_path>/data/vanilla/<module_name>/scripts/*.txt`
- `<dwarf_fortress_path>/data/vanilla/<module_name>/sound/*.txt`
etc.

Common modules include:
- `vanilla_creatures` (e.g., `creature_standard.txt`)
- `vanilla_items` (e.g., `item_weapon.txt`)
- `vanilla_entities` (e.g., `entity_default.txt`)

### Search Strategy
To find a specific object definition (e.g., `[CREATURE:DWARF]`):
1.  Use `grep_search` within the `<dwarf_fortress_path>/data/vanilla/` directory.
2.  Pattern: `\[<TYPE>:<ID>\]` (e.g., `\[CREATURE:DWARF\]`).
3.  Include pattern: `*.txt`.

## Quick Reference Workflow

| Phase | Action | Reference |
| :--- | :--- | :--- |
| **1. Initialize** | Create folder, generate `info.txt`. | [info_txt.md](references/info_txt.md) |
| **2. Define Content** | Add files to `objects/`, `graphics/`, `scripts/`, or `sound/`. | [v50_modding.md](references/v50_modding.md) |
| **3. Modify Vanilla** | Use Modding API (`SELECT_`/`CUT_`) where supported. | [v50_modding.md](references/v50_modding.md) |

## Common Mistakes / Red Flags

- **Guessing tokens:** Never hallucinate or assume token names. Always use `grep_search` on the vanilla RAWs to verify syntax.
- **Direct vanilla edits:** Do not modify files in `data/vanilla/`. Always create a separate mod folder and use the Modding API (`[SELECT_...]` or `[CUT_...]`) if the entities being edited support it.
- **Missing info.txt:** Creating a mod folder without a valid `info.txt` will cause the mod to fail to load.

## Key Reference Links
- [info_txt.md](references/info_txt.md) - Mandatory mod metadata.
- [v50_modding.md](references/v50_modding.md) - RAW editing workflows and syntax.
- [tokens.md](references/tokens.md) - Exhaustive list of RAW object types and prefixes.
- [types/](references/types/) - Sub-references for specific RAW tokens.
