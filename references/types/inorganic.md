# Inorganic Tokens (`[OBJECT:INORGANIC]`)

Inorganic definitions define stones, metals, ores, and other non-living materials. They use the same property tokens as organic materials but include specific tokens for geological occurrence.

## 1. Core Identity & Display
- `[INORGANIC:ID]` - Starts a new inorganic material definition.
- `[USE_MATERIAL_TEMPLATE:TEMPLATE_ID]` - Inherits properties from a template (e.g., `STONE_TEMPLATE`).
- `[MATERIAL_VALUE:n]` - Multiplier for item value (e.g., Gold is 30, Copper is 2).
- `[DISPLAY_COLOR:r:g:b]` - Color of the tile in-game.
- `[ITEM_SYMBOL:char]` - Character used for boulders/items (Default: `7`).
- `[STATE_NAME_ADJ:state:name]` - Names for states (e.g., `[STATE_NAME_ADJ:ALL_SOLID:gold]`).

## 2. Geological Occurrence
Defines where the material appears in the world.
- **Syntax:** `[ENVIRONMENT:CLASS:INCLUSION_TYPE:FREQUENCY]`
    - **Classes:** `ALL_STONE`, `SEDIMENTARY`, `IGNEOUS_INTRUSIVE`, `IGNEOUS_EXTRUSIVE`, `METAMORPHIC`, `SOIL`, `ALLUVIAL`.
    - **Inclusion Types:** `CLUSTER` (Large ovoids), `CLUSTER_SMALL` (3-9 tiles), `CLUSTER_ONE` (Single tiles), `VEIN` (Large streaks).
    - **Frequency:** 1-100; if all stones in an environment have equal frequency they are all equally likely to appear. 
- `[ENVIRONMENT_SPEC:STONE_ID:INCLUSION_TYPE:FREQUENCY]` - Occurs inside a specific stone type (e.g., `[ENVIRONMENT_SPEC:KIMBERLITE:CLUSTER_SMALL:100]`).
- `[METAL_ORE:METAL_ID:CHANCE]` - Defines the stone as an ore for a metal (Chance is d100).

## 3. Physical & Thermal Properties
- `[SOLID_DENSITY:n]` - Density in kg/m³. Affects weight and blunt impact.
- `[LIQUID_DENSITY:n]` - Density when molten.
- `[MELTING_POINT:temp]` - Temperature at which it melts (A custom scale defined as `Fahrenheit + 9968`; room temp is ~10015).
- `[BOILING_POINT:temp]` - Temperature at which it boils (Same scale as melting point).
- `[HEATDAM_POINT:temp]` - Temperature above which the material takes damage (Same scale as melting point).
- `[IGNITE_POINT:temp]` - Temperature at which it catches fire (Same scale as melting point).
- `[SPEC_HEAT:n]` - Energy required to raise temperature.

## 4. Mechanical Properties (Strength)
Used for combat and structural calculations.
- `[IMPACT_YIELD:n]` / `[IMPACT_FRACTURE:n]` - Resistance to blunt force.
- `[SHEAR_YIELD:n]` / `[SHEAR_FRACTURE:n]` - Resistance to cutting/slicing.
- `[TENSILE_YIELD:n]` / `[TENSILE_FRACTURE:n]` - Resistance to stretching.
- `[MAX_EDGE:n]` - Sharpness (10,000+ allows for effective stone weapons).

## 5. Usage Flags
- `[IS_STONE]` / `[IS_METAL]` - Identifies the material category.
- `[ITEMS_WEAPON]` / `[ITEMS_ARMOR]` - Allows use for specific equipment.
- `[ITEMS_DIGGER]` - Allows use for picks.
- `[ITEMS_AMMO]` - Allows use for ammunition.
- `[REACTION_CLASS:id]` - Groups materials for recipes (e.g., `FLUX`, `CALCIUM_CARBONATE`).

## Example: Iron Ore (Hematite)
```text
[INORGANIC:HEMATITE]
    [NAME:hematite]
    [STATE_NAME_ADJ:ALL_SOLID:hematite]
    [DISPLAY_COLOR:4:0:0]
    [ITEM_SYMBOL:7]
    [METAL_ORE:IRON:100]
    [ENVIRONMENT:SEDIMENTARY:VEIN:100]
    [IS_STONE]
    [MATERIAL_VALUE:3]
    [SOLID_DENSITY:5260]
```
