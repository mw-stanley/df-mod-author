# Reaction Tokens (`[OBJECT:REACTION]`)

Reactions define workshop jobs, specifying the inputs (reagents), outputs (products), and requirements for a task.

## 1. Core Identity
- `[REACTION:ID]` - Starts a new reaction definition.
- `[NAME:string]` - Display name in workshop menus.
- `[BUILDING:building_id:hotkey]` - Workshop where the job is performed.
- `[SKILL:skill_id]` - Skill required and trained by the job.
- `[FUEL]` - Requires charcoal/coke (if building is not over magma).

## 2. Reagents (`REAGENT`)
Defines the items consumed by the reaction.
- **Syntax:** `[REAGENT:name:qty:item_token:material_token]`
    - `item_token`: `category:subtype` (e.g., `BAR:NONE`, `BOULDER:NONE`, `NONE:NONE`).
    - `material_token`: `type:id` (e.g., `INORGANIC:IRON`, `GET_MATERIAL_FROM_REAGENT:name:id`).

### Reagent Modifiers
Filter reagents by material properties or classes:
- `[REACTION_CLASS:id]` - Filters for materials with matching class (e.g., `FLUX`).
- `[ANY_BONE_MATERIAL]`, `[ANY_LEATHER_MATERIAL]`, `[ANY_PLANT_MATERIAL]`.
- `[METAL_ORE:metal_id]` - Filters for ores of a specific metal.
- `[HAS_EDGE]`, `[UNROTTEN]`, `[EMPTY]`.
- `[PRESERVE_REAGENT]` - Reagent is not consumed.

## 3. Products (`PRODUCT`)
Defines the items created by the reaction.
- **Syntax:** `[PRODUCT:probability:qty:item_token:material_token]`
    - `probability`: 1-100 percentage chance of creation.
    - `qty`: Number of items or stack size produced.
- `[PRODUCT_DIMENSION:n]` - Size for bulk items: Bars (150), Cloth (10,000), Thread (15,000).

### Dynamic Products
- `GET_MATERIAL_FROM_REAGENT:name:id` - Inherits material from a reagent.
- `GET_ITEM_DATA_FROM_REAGENT:name:id` - Inherits item and material from a reagent's `ITEM_REACTION_PRODUCT`.

## Example: Bronze Smelting
```text
[REACTION:BRONZE_MAKING]
    [NAME:smelt bronze from ore]
    [BUILDING:SMELTER:B]
    [REAGENT:A:1:BOULDER:NONE][METAL_ORE:TIN:100]
    [REAGENT:B:1:BOULDER:NONE][METAL_ORE:COPPER:100]
    [PRODUCT:100:2:BAR:NONE][GET_MATERIAL_FROM_REAGENT:A:METAL_MAT]
    [FUEL]
    [SKILL:SMELT]
```
