# Plant Tokens (`[OBJECT:PLANT]`)

Plant definitions define shrubs, trees, and crops, including their growth cycles, materials, and derived products like drinks and seeds.

## 1. Basic Identity & Environment
- `[PLANT:ID]` - Starts a new plant definition.
- `[NAME:singular:plural:adjective]` - Basic nomenclature.
- `[ALL_NAMES:string]` - Sets all three name forms to the same string.
- `[BIOME:biome_id]` - Valid biomes. See [references/shared/biomes.md](../shared/biomes.md) for a list of tokens.
- `[UNDERGROUND_DEPTH:min:max]` - Cavern levels (0:0 for surface).
- `[FREQUENCY:0-100]` - Chance of appearing in a valid biome.
- `[GROWDUR:n]` - Time to grow in farm plots (hundreds of ticks, Default: 300).
- `[SPRING]`, `[SUMMER]`, `[AUTUMN]`, `[WINTER]` - Valid growing seasons.

## 2. Visuals & Tiles
- `[SHRUB_TILE:char]` / `[DEAD_SHRUB_TILE:char]` - Character in the wild (Default: `"`).
- `[PICKED_TILE:char]` / `[DEAD_PICKED_TILE:char]` - Character when harvested (Default: `τ`).
- `[SHRUB_COLOR:f:b:br]` / `[PICKED_COLOR:f:b:br]` - Colors for tiles.

## 3. Materials & Templates
Plants define their composition using local materials linked to global templates.
- `[USE_MATERIAL_TEMPLATE:local_id:template_id]` - Creates a local material (e.g., `STRUCTURAL`, `SEED`, `LEAF`).
- `[BASIC_MAT:local_mat_id]` - The primary material harvested when picked (usually `LOCAL_PLANT_MAT:STRUCTURAL`).

## 4. Products (Seeds, Drinks, Processing)
- `[SEED:name:plural:f:b:br:local_mat_id]` - Defines the seed item.
- `[DRINK:local_mat_id]` - Material used for brewing.
- `[MILL:local_mat_id]` - Material produced when milled into powder.
- `[THREAD:local_mat_id]` - Material produced when processed for thread.
- `[EXTRACT_BARREL:local_mat_id]` - Liquid extract stored in barrels.

## 5. Growths (Fruit & Leaves)
- `[GROWTH:ID]` - Defines a part like fruit or flowers.
    - `[GROWTH_NAME:singular:plural]`
    - `[GROWTH_ITEM:item_type:SUBTYPE local_mat_id]`
    - `[GROWTH_TIMING:start:end]` - Tick range when the growth appears.
    - `[GROWTH_PRINT:char:f:b:br:condition]` - How the growth appears on the map tile.

## Example: Plump Helmet
```text
[PLANT:MUSHROOM_HELMET_PLUMP]
    [NAME:plump helmet:plump helmets:plump helmet]
    [ALL_NAMES:plump helmet]
    [BIOME:SUBTERRANEAN_WATER]
    [UNDERGROUND_DEPTH:1:3]
    [GROWDUR:300]
    [PICKED_TILE:6]
    [PICKED_COLOR:5:0:0]
    [USE_MATERIAL_TEMPLATE:STRUCTURAL:STRUCTURAL_PLANT_TEMPLATE]
    [BASIC_MAT:LOCAL_PLANT_MAT:STRUCTURAL]
    [SEED:plump helmet spawn:plump helmet spawns:5:0:0:LOCAL_PLANT_MAT:SEED]
    [DRINK:LOCAL_PLANT_MAT:DRINK]
    [WINTER][SPRING][SUMMER][AUTUMN]
```
