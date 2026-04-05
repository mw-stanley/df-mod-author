# Shield Tokens (`[ITEM_SHIELD]`)

Shields and bucklers provide protection by blocking incoming attacks. They share many tokens with armor but have unique defensive properties.

## 1. Core Identity
- `[ITEM_SHIELD:ID]` - Starts a new shield definition.
- `[NAME:singular:plural]` - Display name.
- `[VALUE:n]` - Base monetary value (Default: 10).
- `[MATERIAL_SIZE:n]` - Determines material cost and weight.

## 2. Defensive Properties
- `[BLOCKCHANCE:n]` - Effectiveness in blocking (Default: 10).
- `[UPSTEP:n]` - For shields, this **only affects weight** calculations.

## 3. Layering & Levels
- `[LAYER:type]` - Position: `UNDER`, `OVER`, `ARMOR`, `COVER` (Default: `UNDER`).
- `[ARMORLEVEL:n]` - Protection level: 0-3 (Default: 1).
- `[LAYER_SIZE:n]` - Bulkiness (Default: 10).
- `[LAYER_PERMIT:n]` - Space allowed underneath (Default: 10).

## 4. Material Flags
- `[METAL]` - Can be made from metal (or wood if civilization has `WOOD_ARMOR`).
- `[LEATHER]` - Can be made from leather.
- `[SOFT]` - Can be made from cloth.
- `[HARD]` - Default; prevents cloth usage.
