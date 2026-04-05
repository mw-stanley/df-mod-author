# Dwarf Fortress RAW Editing Guide (v53.11)

> [!IMPORTANT]
> **Version Compatibility:** This guide is current as of **Dwarf Fortress version 53.11**. Vanilla files may contain newer tokens, and the wiki may reference different versions. Use the vanilla files or the wiki as a reference as appropriate.

This guide provides the workflow and syntax for editing and creating Dwarf Fortress RAW files in the `objects/` folder of a mod.

## RAW File Header
Every RAW file MUST follow this header format:
1.  **Line 1:** Filename (without the `.txt` extension).
2.  **Line 2:** A blank line (Standard convention for clarity).
3.  **Line 3:** `[OBJECT:TYPE]` (e.g., `[OBJECT:CREATURE]`, `[OBJECT:ENTITY]`, `[OBJECT:ITEM]`).

## Workflows

### 1. Identify RAW Type
Before editing or creating a file, check the filename prefix (e.g., `creature_`, `item_weapon_`) against the table in [tokens.md](tokens.md). This determines the `[OBJECT:TYPE]` and which sub-reference file to consult for specific tokens.

### 2. Consult Sub-Reference
Once the type is identified (e.g., `CREATURE`), open the corresponding file in `types/` (e.g., `types/creature.md`) to find the relevant tokens and syntax for that object.

### 3. Read the Vanilla raws
When adding or editing objects, the vanilla raws are an important reference. Read the relevant vanilla raw file to understand the object definition.

### 4. Adding New Objects
To add new content, create a new RAW file (e.g., `creature_my_race.txt`) with the appropriate header and object definition.

### 5. Modifying Existing Objects
When modifying vanilla data, determine if the Object Type supports `SELECT_` and `CUT_`.

#### Supported Types ONLY (SELECT_/CUT_):
`SELECT_` and `CUT_` functions **ONLY** work for the following:
- `CREATURE`, `ENTITY`, `INTERACTION`, `ITEM`, `INORGANIC`, `PLANT`, `REACTION`, `WORD`, `TRANSLATION`, `SYMBOL`, `MUSIC`, `SOUND`

**Syntax:**
- `[SELECT_<TYPE>:<ID>]`: Target an existing object to add or overwrite tokens.
- `[CUT_<TYPE>:<ID>]`: Remove an object entirely (useful for "deleting" or rewriting an object).
- **Items:** Always use `ITEM` as the type (e.g., `[SELECT_ITEM:ITEM_HELM_HELM]`).

#### Unsupported Types (Full File Reproduction):
For types like `BODY`, `BUILDING`, `MATERIAL_TEMPLATE`, or `TISSUE_TEMPLATE` that are not supported by `SELECT_` and `CUT_`, you **MUST**:
1. Copy the entire vanilla RAW file into your mod's `objects/` folder.
2. Modify the new file directly.
3. Use `CONFLICTS_WITH_ID` in `info.txt` if removing objects.

### 6. Using Tokens
Tokens are enclosed in square brackets with arguments separated by colons. Consult the sub-reference files in `types/` for the specific tokens available for that object type. It is critically important that you do not hallucinate tokens or arguments. Verify all tokens and arguments against the vanilla raws or the sub-reference files.

## Researching Vanilla Data

Always locate the original object in the vanilla RAWs to verify existing tokens before modifying. **DO NOT use external search engines (Google/Wiki) if the local files are available.**

### Vanilla RAW Location (v50+)
Vanilla RAWs are found in module-specific folders under the `data/vanilla/` directory:
`<DF_PATH>/data/vanilla/<module_name>/objects/*.txt`

Example modules:
- `vanilla_creatures/objects/`
- `vanilla_items/objects/`

### How to Search
To find a definition like `[CREATURE:DWARF]`:
1.  Identify the base directory: `<DF_PATH>/data/vanilla/`.
2.  Use `grep_search` with the pattern `\[TYPE:ID\]`.
    - **Example:** `grep_search(pattern='\[CREATURE:DWARF\]', dir_path='<DF_PATH>/data/vanilla/', include_pattern='*.txt')`
3.  Read the resulting file to understand the original object structure.
