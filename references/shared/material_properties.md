# Shared Material Properties

These tokens are used across `MATERIAL_TEMPLATE`, `INORGANIC`, `PLANT`, and `CREATURE` (local materials) definitions to define physical, thermal, and functional properties.

## 1. State Descriptors (Naming & Display)
Defines how the material is named and colored in different physical states (SOLID, LIQUID, GAS, etc.).
- **Syntax:** `[STATE_NAME_ADJ:state:name]` or `[STATE_NAME:state:name]` and `[STATE_ADJ:state:name]`.
    - **Common States:** `ALL_SOLID`, `SOLID`, `LIQUID`, `GAS`, `SOLID_POWDER`, `SOLID_PASTE`, `PRESSED`.
- **Display:** `[STATE_COLOR:state:color_id]` (Links to `DESCRIPTOR_COLOR`).
- **Map Descriptors:** `[BLOOD_MAP_DESCRIPTOR:id]`, `[SWEAT_MAP_DESCRIPTOR:id]`, etc. (Used for splatters).

## 2. Physical & Thermal Properties
- `[SOLID_DENSITY:n]` - kg/m³. Affects weight and blunt impact.
- `[LIQUID_DENSITY:n]` - Density when molten.
- `[MOLAR_MASS:n]` - Used for gas calculations.
- `[ABSORPTION:n]` - 0 (waterproof) to 100.
- `[MELTING_POINT:temp]` - (Room temp is ~10015).
- `[BOILING_POINT:temp]` - Temperature at which it turns to gas.
- `[HEATDAM_POINT:temp]` / `[COLDDAM_POINT:temp]` - Damage thresholds.
- `[IGNITE_POINT:temp]` - Temperature it catches fire.
- `[SPEC_HEAT:n]` - Energy required to raise temperature.

## 3. Mechanical Properties (Strength)
- `[IMPACT_YIELD:n]` / `[IMPACT_FRACTURE:n]` - Blunt force resistance.
- `[SHEAR_YIELD:n]` / `[SHEAR_FRACTURE:n]` - Cutting/slicing resistance.
- `[TENSILE_YIELD:n]` / `[TENSILE_FRACTURE:n]` - Stretching resistance.
- `[COMPRESSIVE_YIELD:n]` / `[COMPRESSIVE_FRACTURE:n]` - Crushing resistance.
- `[MAX_EDGE:n]` - Sharpness (10,000+ for effective weapons).

## 4. Usage Flags (Behaviors)
Flags that determine how the game treats the material.
- **Edibility:** `[EDIBLE_RAW]`, `[EDIBLE_COOKED]`, `[EDIBLE_VERMIN]`.
- **Types:** `[IS_METAL]`, `[IS_STONE]`, `[IS_GLASS]`, `[IS_GEM]`, `[WOOD]`, `[BONE]`, `[LEATHER]`, `[SILK]`.
- **Item Creation:** `[ITEMS_WEAPON]`, `[ITEMS_ARMOR]`, `[ITEMS_AMMO]`, `[ITEMS_DIGGER]`, `[ITEMS_SOFT]`, `[ITEMS_HARD]`.
- **Biological:** `[MEAT]`, `[ALCOHOL]`, `[CHEESE]`, `[ROTS]`, `[GENERATES_MIASMA]`, `[ENTERS_BLOOD]`.

## 5. Reaction & Processing
- `[REACTION_CLASS:id]` - Reagent group (e.g., `FLUX`, `GYPSUM`, `FAT`).
- `[MATERIAL_REACTION_PRODUCT:type:mat_id]` - Links a material to a product (e.g., `TAN_MAT`).
- `[ITEM_REACTION_PRODUCT:item_type:mat_id]` - Links a material to a produced item.
- `[METAL_ORE:metal_id:chance]` - Smeltable into bars.
- `[HARDENS_WITH_WATER]` - Used for casts.
