# Ammunition Tokens (`[ITEM_AMMO]`)

Ammunition is defined in `[OBJECT:ITEM]` files and is linked to ranged weapons via matching class tokens.

## Core Tokens
- `[ITEM_AMMO:ID]` - Starts a new ammunition definition.
- `[NAME:singular:plural]` - Display name of the ammo.
- `[CLASS:string]` - Specifies the ammo type. This MUST match the `[AMMUNITION:string]` token defined in the weapon that fires it.
    - **Common Values:** `BOLT` (Default), `ARROW`, `BLOWDART`.
- `[SIZE:n]` / `[WEIGHT:n]` - Defines the size/weight of a single unit of ammo.

## Combat Properties
- `[ATTACK:type:contact:penetration:verb2nd:verb3rd:noun:velocity]` - Defines impact characteristics.
    - **type:** `BLUNT` or `EDGE`.
    - **contact:** Surface area of impact.
    - **penetration:** Depth of penetration.
    - **verb2nd / verb3rd:** Strings for combat logs (e.g., `bash:bashes`).
    - **noun:** Description of the impact (e.g., `blunt bolt`).
    - **velocity:** Multiplier for projectile force.

## Common Item Flags
These general item tokens are frequently used with ammunition to define material and behavior:
- `[METAL]` - Can be made of metal.
- `[WOOD]` - Can be made of wood.
- `[BONE]` - Can be made of bone.
- `[LEATHER]` - Can be made of leather.

## Example: Standard Bolt
```text
[ITEM_AMMO:ITEM_AMMO_BOLTS]
    [NAME:bolt:bolts]
    [CLASS:BOLT]
    [SIZE:150]
    [ATTACK:EDGE:20:1000:stab:stabs:bolt:1000]
```
