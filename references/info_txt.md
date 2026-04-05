# Dwarf Fortress `info.txt` Reference (v50+)

Every mod in Dwarf Fortress v50+ MUST contain an `info.txt` file in its root directory. This file defines the mod's identity, versioning, and relationship with other mods.

## Mandatory Tokens

| Token | Argument | Description |
| :--- | :--- | :--- |
| `ID` | `id` | Unique identifier (e.g., `my_mod`). IDs starting with `vanilla_` are reserved. |
| `NUMERIC_VERSION` | `integer` | Integer version (e.g., `1`). Must be $\ge$ `EARLIEST_COMPATIBLE_NUMERIC_VERSION`. |
| `DISPLAYED_VERSION` | `string` | Version string shown in-game (e.g., `1.0.2`). |
| `EARLIEST_COMPATIBLE_NUMERIC_VERSION` | `integer` | Oldest numeric version this mod is compatible with. |
| `EARLIEST_COMPATIBLE_DISPLAYED_VERSION` | `string` | Display version of the earliest compatible version. |
| `AUTHOR` | `string` | The name of the mod creator. |
| `NAME` | `string` | The display name of the mod. |

## Optional & Dependency Tokens

| Token | Argument | Description |
| :--- | :--- | :--- |
| `DESCRIPTION` | `string` | Brief description of the mod shown during loading. |
| `REQUIRES_ID` | `string` | Mod will NOT load unless the specified mod ID is present. |
| `REQUIRES_ID_BEFORE_ME` | `string` | Specified mod ID must be loaded earlier in the load order. |
| `REQUIRES_ID_AFTER_ME` | `string` | Specified mod ID must be loaded later in the load order. |
| `CONFLICTS_WITH_ID` | `string` | Mod will NOT load if the specified mod ID is present. |

## Steam Workshop Tokens

These tokens are only used for mods distributed on the Steam Workshop. Do not add them without asking the user first.

| Token | Requirement | Description |
| :--- | :--- | :--- |
| `STEAM_TITLE` | **Required if uploading to Steam Workshop** | The title of the mod on the Steam Workshop. |
| `STEAM_DESCRIPTION` | Optional | Workshop description (max 8000 bytes). |
| `STEAM_TAG` | Optional | Categorization tags (e.g., `[STEAM_TAG:ui]`). Can be used multiple times. |
| `STEAM_KEY_VALUE_TAG` | Optional | Specific key-value tags for Workshop queries. |
| `STEAM_METADATA` | Optional | Metadata that can be queried without downloading. |
| `STEAM_CHANGELOG` | Optional | Brief description of changes for the current update. |
| `STEAM_FILE_ID` | **Auto-gen** | Generated on first upload. Do not add manually. |

---

## Example `info.txt`

```text
[ID:my_cool_mod]
[NUMERIC_VERSION:1]
[DISPLAYED_VERSION:1.0]
[EARLIEST_COMPATIBLE_NUMERIC_VERSION:1]
[EARLIEST_COMPATIBLE_DISPLAYED_VERSION:1.0]
[AUTHOR:Mike]
[NAME:My Cool Mod]
[DESCRIPTION:Adds several new creatures to the game.]
[CONFLICTS_WITH_ID:vanilla_creatures]
[STEAM_TITLE:My Cool Mod]
[STEAM_DESCRIPTION:An awesome mod that adds stuff!]
[STEAM_TAG:creatures]
[STEAM_TAG:content]
```
