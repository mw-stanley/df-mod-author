# Dwarf Fortress Tile Page Reference (v50+)

Tile pages define the source image files and how they are sliced into individual tiles for use in graphics definitions. These are found in `tile_page_*.txt` files.

## Core Tokens

| Token | Parameters | Description |
| :--- | :--- | :--- |
| `[TILE_PAGE:<ID>]` | `UNIQUE_ID` | Begins the definition for a tile page. This ID is used by graphics files. |
| `[FILE:<PATH>]` | `RELATIVE_PATH` | Path to the `.png` image (e.g., `graphics/images/my_sprites.png`). |
| `[TILE_DIM:<W>:<H>]` | `WIDTH`, `HEIGHT` | The size of each individual tile in pixels (e.g., `32:32`). |
| `[PAGE_DIM:<W>:<H>]` | `WIDTH_IN_TILES`, `HEIGHT_IN_TILES` | The total number of tiles wide and high the image contains. |

## Usage Example

```text
tile_page_my_mod
  [OBJECT:TILE_PAGE]
  [TILE_PAGE:MY_UNIQUE_PAGE_ID]
    [FILE:graphics/images/my_sprites.png]
    [TILE_DIM:32:32]
    [PAGE_DIM:10:10]
```
