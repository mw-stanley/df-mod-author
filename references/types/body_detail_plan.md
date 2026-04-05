# Body Detail Plan Tokens (`[OBJECT:BODY_DETAIL_PLAN]`)

Body detail plans automate the assignment of materials, tissues, and physical properties to body parts across different creatures using templates and arguments.

## Core Tokens
- `[BODY_DETAIL_PLAN:ID]` - Starts a new body detail plan definition.
- `[ADD_MATERIAL:local_id:template]` - Adds a material to the creature using a template (e.g., `SKIN_TEMPLATE`).
- `[ADD_TISSUE:local_id:template]` - Adds a tissue to the creature using a template (e.g., `SKIN_TEMPLATE`).

## Layering Tokens
These tokens define tissue layers for body parts. They often use placeholders (`ARG1` to `ARG5`) which are filled when the plan is called in a creature RAW.

- `[BP_LAYERS:selector:part:tissue:thickness...]` - Defines a stack of tissue layers for the targeted parts.
- `[BP_LAYERS_OVER:selector:part:tissue:thickness...]` - Adds layers on top of existing ones.
- `[BP_LAYERS_UNDER:selector:part:tissue:thickness...]` - Adds layers beneath existing ones.

## Structural & Spatial Tokens
- `[BP_RELSIZE:selector:part:relsize]` - Sets the relative size of parts.
- `[BP_POSITION:selector:part:position]` - Defines spatial position (e.g., `FRONT`, `LEFT`, `TOP`).
- `[BP_RELATION:selector:part:relation:target:coverage]` - Defines relationships (e.g., `AROUND` for eyelids around eyes).

## Selectors
Selectors determine which body parts the tokens apply to:
- `BY_CATEGORY:category_id` - Targets parts with a specific `CATEGORY` token (e.g., `HEAD`, `FINGER`, `LIMB`).
- `BY_TYPE:type_id` - Targets parts by their type (e.g., `GRASP`, `STANCE`).
- `BY_TOKEN:part_id` - Targets a specific body part by its unique ID.

## Automation & Arguments
Body detail plans act like functions. When called in a creature definition, they accept arguments:

**Example Plan Definition:**
```text
[BODY_DETAIL_PLAN:VERTEBRATE_LAYERS]
  [BP_LAYERS:BY_CATEGORY:BODY:ARG1:50:ARG2:10:ARG3:5]
```

**Calling the Plan in a Creature:**
```text
[BODY_DETAIL_PLAN:VERTEBRATE_LAYERS:SKIN:FAT:MUSCLE]
```
In this case, `ARG1` becomes `SKIN`, `ARG2` becomes `FAT`, and `ARG3` becomes `MUSCLE`.
