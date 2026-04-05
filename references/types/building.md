# Building Tokens (`[OBJECT:BUILDING]`)

Building tokens are used to define custom workshops (`BUILDING_WORKSHOP`) and furnaces (`BUILDING_FURNACE`) in Dwarf Fortress.

## Core Identity
- `[NAME:string]` - The name of the custom building.
- `[NAME_COLOR:fg:bg:bright]` - Color of the building's name when queried (0-7).
- `[TOOLTIP:string]` - Tooltip description for the build menu.
- `[BUILD_KEY:key]` - Shortcut key for the build menu.

## Dimensions & Placement
- `[DIM:width:height]` - Size in tiles (Default 3:3, Max 31x31).
- `[WORK_LOCATION:x:y]` - Tile where the worker stands (Default 3:3).
- `[BLOCK:row:tiles...]` - Movement blocking (0 = nonblocking, 1 = blocking).

## Construction Requirements
- `[BUILD_LABOR:labor_id]` - The labor required to build it. See [references/shared/labors.md](../shared/labors.md) for the list of labors.
- `[BUILD_ITEM:qty:item_type:material]` - Item required for construction.
- `[NEEDS_MAGMA]` - Requires a tile over magma; functions without fuel.

### Common [BUILD_ITEM] Modifiers:
- `[ANY_BONE_MATERIAL]`, `[ANY_LEATHER_MATERIAL]`
- `[BUILDMAT]` - (Bar/Block/Boulder/Wood)
- `[FIRE_BUILD_SAFE]`, `[MAGMA_BUILD_SAFE]`
- `[WORTHLESS_STONE_ONLY]`

## Visuals & Stages
- `[TILE:stage:row:tiles...]` - ASCII representation at various construction stages.
- `[COLOR:stage:row:colors...]` - Colors for the tiles at various stages.

## Example Custom Workshop
```text
[BUILDING_WORKSHOP:MY_WORKSHOP]
    [NAME:My Workshop]
    [NAME_COLOR:7:0:1]
    [DIM:3:3]
    [WORK_LOCATION:2:2]
    [BUILD_LABOR:CARPENTER]
    [BLOCK:1:111]
    [BLOCK:2:101]
    [BLOCK:3:111]
    [TILE:4:1:178:178:178]
    [TILE:4:2:178:15:178]
    [TILE:4:3:178:178:178]
    [BUILD_ITEM:1:BLOCKS:NONE][BUILDMAT][WORTHLESS_STONE_ONLY]
```
