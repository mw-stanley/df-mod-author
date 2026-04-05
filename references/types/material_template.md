# Material Template Tokens (`[OBJECT:MATERIAL_TEMPLATE]`)

Material templates define sets of properties that can be applied to many specific materials (e.g., `STRONGBONE_TEMPLATE`, `PLANT_ALCOHOL_TEMPLATE`).

## Core Definition
- `[MATERIAL_TEMPLATE:ID]` - Starts a new template definition.
- **Inheritance:** Most property tokens are shared with all material types. See [references/shared/material_properties.md](../shared/material_properties.md) for the exhaustive list of physical, thermal, and mechanical tokens.

## Template-Specific & Common Tokens
While most material tokens are shared, these are frequently used or prioritized in templates:

### Naming & Identity
- `[NAME:string]` - Internal name.
- `[MATERIAL_VALUE:n]` - Base value multiplier.
- `[MEAT_NAME:singular:plural:adjective]` - Names for butchered meat.
- `[EXTRACT_STORAGE:type]` - Container needed for liquid extracts (`BARREL` or `FLASK`).

### Biological & Graphics (Organic Templates)
- `[MEAT_CATEGORY:type]` - (e.g., `MEAT`, `OFFAL`, `ORGAN`).
- `[SYNDROME]` - Begins a syndrome definition attached to the material.
- `[HAIR]`, `[FEATHER]`, `[SCALE]`, `[HOOF]`, `[CHITIN]`, `[CARTILAGE]` - Identifies the material's biological role for graphics.

### Processing
- `[POWDER_DYE:color_id]` - Allows use as a dye.
- `[THREAD_METAL]` - Allows strand extraction (e.g., Adamantine).
- `[SOAP_LEVEL:n]` - Effectiveness as a soap.

## Usage
- **Inorganics:** Used via `[USE_MATERIAL_TEMPLATE:ID]` in `OBJECT:INORGANIC`.
- **Creatures:** Used in `[ADD_MATERIAL]` and `[USE_MATERIAL_TEMPLATE]` within creature/tissue definitions.
- **Plants:** Used for plant structural and product materials.

## Example: Standard Stone Template
```text
[MATERIAL_TEMPLATE:STONE_TEMPLATE]
    [STATE_NAME_ADJ:ALL_SOLID:stone]
    [DISPLAY_COLOR:7:0:0]
    [MATERIAL_VALUE:1]
    [SPEC_HEAT:800]
    [MELTING_POINT:11500]
    [SOLID_DENSITY:2670]
    [IS_STONE]
    [ITEMS_HARD]
```
