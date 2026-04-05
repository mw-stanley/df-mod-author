# Trap Component Tokens (`[ITEM_TRAPCOMP]`)

Trap components are large weapon-like items used in weapon traps, upright spike traps, and screw pumps.

## Core Tokens
- `[ITEM_TRAPCOMP:ID]` - Starts a new trap component definition.
- `[NAME:singular:plural]` - Display name.
- `[HITS:n]` - Number of times the component strikes per trap activation (Default: 1).
- `[MATERIAL_SIZE:n]` - Determines material cost (Bars = size / 3).

## Usage Flags
- `[IS_SCREW]` - Can be used to build screw pumps.
- `[IS_SPIKE]` - Can be used in upright spear/spike traps.

## Combat Properties
Trap components use standard weapon attack syntax. Multiple attacks can be defined.
- `[ATTACK:type:contact:penetration:verb2nd:verb3rd:noun:velocity]`
    - **type:** `BLUNT` or `EDGE`.
    - **contact:** Surface area of impact.
    - **penetration:** Depth of penetration.
    - **verb2nd / verb3rd:** Log strings (e.g., `bash:bashes`).
    - **noun:** Part used (e.g., `blade`, `head`).
    - **velocity:** Force multiplier (Standard: 1000).

## Material Flags
- `[METAL]` - Can be made of metal.
- `[WOOD]` - Can be made of wood.

## Example: Giant Axe Blade
```text
[ITEM_TRAPCOMP:ITEM_TRAPCOMP_GIANT_AXEBLADE]
    [NAME:giant axe blade:giant axe blades]
    [SIZE:800]
    [MATERIAL_SIZE:3]
    [HITS:1]
    [ATTACK:EDGE:20000:8000:slash:slashes:blade:1250]
```
