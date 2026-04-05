# Armor Tokens (`[ITEM_ARMOR]`)

Body armor tokens define coverage, layering, and material requirements for torso-based garments.

## 1. Core Identity
- `[ITEM_ARMOR:ID]` - Starts a new body armor definition.
- `[NAME:singular:plural]` - Display name.
- `[PREPLURAL:phrase]` - Changes plural form (e.g., "suits of" platemail).
- `[ADJECTIVE:string]` - Adds a descriptive prefix.

## 2. Coverage & Steps
- `[UBSTEP:n]` - Sleeve length: `0` (torso only) to `MAX` (covers hands).
- `[LBSTEP:n]` - Leg/hem length: `0` (lower body only) to `MAX` (covers feet).
- `[COVERAGE:n]` - % chance to block contaminants or attacks (Default: 100).

## 3. Layering & Levels
- `[LAYER:type]` - Position: `UNDER`, `OVER`, `ARMOR`, `COVER`.
- `[ARMORLEVEL:n]` - 0 (Clothing), 1 (Ranged), 2 (Melee), 3 (Uniform).
- `[LAYER_SIZE:n]` - Bulkiness of the item.
- `[LAYER_PERMIT:n]` - Maximum volume allowed underneath this item.
- `[SHAPED]` - Restricts the wearer to only one shaped item per body slot.
- `[METAL_ARMOR_LEVELS]` - Metal versions count as one `ARMORLEVEL` higher.

## 4. Material Flags
- `[SOFT]` - Can be made from cloth.
- `[HARD]` - Default; prevents cloth usage (unless `[SOFT]` is present).
- `[METAL]` - Can be made from metal.
- `[LEATHER]` - Can be made from leather.
- `[BARRED]` / `[SCALED]` - Can be made from bone or shell.
