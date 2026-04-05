# Glove Tokens (`[ITEM_GLOVES]`)

Glove tokens define coverage, layering, and material requirements for hand-based garments.

## 1. Core Identity
- `[ITEM_GLOVES:ID]` - Starts a new glove definition.
- `[NAME:singular:plural]` - Display name.

## 2. Coverage & Steps
- `[UPSTEP:n]` - Extends coverage toward the torso (e.g., `1` covers the forearms).
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
- `[HARD]` - Default; prevents cloth usage.
- `[METAL]` - Can be made from metal.
- `[LEATHER]` - Can be made from leather.
- `[BARRED]` / `[SCALED]` - Bone or shell.
