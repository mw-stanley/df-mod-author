# Dwarf Fortress Graphics Reference (v50+)

This guide covers the tokens used in `[OBJECT:GRAPHICS]` files (usually `graphics_*.txt`) for defining how creatures, items, and other objects appear in-game.

## Core Structure
Graphics definitions are linked to game objects (like creatures or items) and use `TILE_PAGE` IDs for their source images.

| Token | Parameters | Description |
| :--- | :--- | :--- |
| `[CREATURE_GRAPHICS:<ID>]` | `CREATURE_ID` | Begins the graphics definition for a specific creature. |
| `[CREATURE_CASTE_GRAPHICS:<C_ID>:<CASTE>]` | `CREATURE_ID`, `CASTE_ID` | Defines sprites for a specific caste. |
| `[ITEM_GRAPHICS:<ID>]` | `ITEM_ID` (e.g., `ITEM_WEAPON_AXE_BATTLE`) | Begins graphics for an item. |
| `[TILE_GRAPHICS:<ID>]` | `TILE_ID` (for map/terrain) | Defines sprites for terrain or specific tiles. |

## Creature Graphics (Basic)
Used within `CREATURE_GRAPHICS` to specify sprites for specific states.

| Token | Parameters | Description |
| :--- | :--- | :--- |
| `[DEFAULT:<PAGE_ID>:<X>:<Y>]` | `TILE_PAGE_ID`, `X`, `Y` | The fallback sprite for the creature. |
| `[CHILD:<PAGE_ID>:<X>:<Y>]` | `TILE_PAGE_ID`, `X`, `Y` | Sprite for young creatures. |
| `[BABY:<PAGE_ID>:<X>:<Y>]` | `TILE_PAGE_ID`, `X`, `Y` | Sprite for infants. |
| `[CORPSE:<PAGE_ID>:<X>:<Y>]` | `TILE_PAGE_ID`, `X`, `Y` | Sprite for the dead body. |
| `[SKELETON:<PAGE_ID>:<X>:<Y>]` | `TILE_PAGE_ID`, `X`, `Y` | Sprite for remains. |
| `[GHOST:<PAGE_ID>:<X>:<Y>]` | `TILE_PAGE_ID`, `X`, `Y` | Sprite for spirits. |
| `[LIST_ICON:<PAGE_ID>:<X>:<Y>]` | `TILE_PAGE_ID`, `X`, `Y` | Sprite used in UI lists/menus. |

## Layered Graphics (Advanced)
v50 introduced a complex layering system for compositing sprites (e.g., body + hair + clothing).

### Layer Structure
- `[LAYER_SET:<CONDITION>]`: Groups layers (e.g., `DEFAULT`, `PORTRAIT`, `CORPSE`).
- `[LAYER_GROUP]`: Only the **first** matching layer in this group will render.
- `[LAYER:<ID>:<PAGE_ID>:<X>:<Y>]`: Defines an individual sprite layer.
- `[END_LAYER_GROUP]`: Ends a layer group.

### Layer Conditions
These tokens determine *when* a layer is visible.

| Token | Parameters | Description |
| :--- | :--- | :--- |
| `[CONDITION_CASTE:<CASTE>]` | `CASTE_NAME` | Only shows for a specific caste. |
| `[CONDITION_ITEM_WORN:<SEL>:<PART>:<TYPE>:<ID>]` | Various | Shows if wearing a specific item (e.g., `BY_TOKEN:RH:GLOVES:ITEM_GLOVES_MITTENS`). |
| `[SHUT_OFF_IF_ITEM_PRESENT:<SEL>:<PART>:<TYPE>:<ID>]` | Various | Hides the layer if a specific item is equipped. |
| `[CONDITION_MATERIAL_FLAG:<FLAG>]` | `MATERIAL_FLAG` | Shows based on material properties (e.g., `METAL_ITEM_MATERIAL`). |
| `[CONDITION_TISSUE_LAYER:<SEL>:<CAT>:<TISSUE>]` | Various | Selects a tissue (like `SKIN`) for subsequent checks. |
| `[CONDITION_SYN_CLASS:<CLASS>]` | `SYN_CLASS` | Shows based on syndromes (e.g., `ZOMBIE`). |

### Coloring & Palettes
- `[LS_PALETTE:<NAME>]`: Defines a palette for the layer set.
- `[LS_PALETTE_FILE:<PATH>]`: Points to the 8-bit RGBA image file.
- `[USE_PALETTE:<PALETTE_NAME>:<ROW>]`: Colors the layer using a specific row.
- `[ATTRIBUTE_COLOR:<ATTR>:<DESC_ID>]`: Colors based on physical attributes (e.g., hair color).

## Item Graphics
Defines how items appear when on the ground or in menus.

| Token | Parameters | Description |
| :--- | :--- | :--- |
| `[WEAPON_GRAPHICS:<ID>]` | `ITEM_ID` | Begins weapon definition. |
| `[WEAPON_GRAPHICS_DEFAULT:<PAGE_ID>:<X>:<Y>]` | `TILE_PAGE_ID`, `X`, `Y` | Default sprite for the weapon. |
| `[ARMOR_GRAPHICS:<PAGE_ID>:<X>:<Y>:<ID>]` | `TILE_PAGE_ID`, `X`, `Y`, `ITEM_ID` | Graphics for armor (unworn). |
| `[TOOL_GRAPHICS:<PAGE_ID>:<X>:<Y>:<ID>]` | `TILE_PAGE_ID`, `X`, `Y`, `ITEM_ID` | Graphics for tools. |
| `[FOOD_GRAPHICS:<PAGE_ID>:<X>:<Y>:<ID>]` | `TILE_PAGE_ID`, `X`, `Y`, `ITEM_ID` | Graphics for food items. |

## Miscellaneous
- `[STATUE_CREATURE_GRAPHICS:<CREATURE_ID>]`: 1x2 vertical rectangle for statues.
- `[TILE_GRAPHICS_RECTANGLE:<CREATURE_ID>]`: 3x2 rectangle for Forgotten Beasts.
- `[LARGE_IMAGE:<X>:<Y>:<W>:<H>]`: Defines a multi-tile sprite dimensions.
