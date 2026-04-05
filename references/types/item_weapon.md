don't # Weapon Tokens (`[ITEM_WEAPON]`)

Weapon definitions define melee and ranged combat characteristics, including attack physics and size requirements.

## 1. Melee Combat
- `[ITEM_WEAPON:ID]` - Starts a new weapon definition.
- `[SKILL:skill_id]` - Melee skill used (e.g., `AXE`, `SWORD`, `MACE`, `SPEAR`, `DAGGER`).
- `[TWO_HANDED:size]` - Creatures smaller than this (in cm³) must use it with two hands (Default: 50,000).
- `[MINIMUM_SIZE:size]` - Minimum creature size to use the weapon at all (Default: 40,000).
- `[TRAINING]` - Restricts the weapon to wood only (sparring).
- `[CAN_STONE]` - Can be crafted from obsidian/sharp stone and wood.

## 2. Ranged Combat
- `[RANGED:skill_id:ammo_class]` - Defines the weapon as ranged (e.g., `[RANGED:CROSSBOW:BOLT]`).
- `[SHOOT_FORCE:n]` - Force applied to projectiles.
- `[SHOOT_MAXVEL:n]` - Maximum velocity of fired projectiles.

## 3. Attack Syntax (`ATTACK`)
Multiple attacks can be defined. The AI prefers `EDGE` attacks 100:1 over `BLUNT`.

**Syntax:** `[ATTACK:type:contact:penetration:verb2nd:verb3rd:noun:velocity]`
- **type:** `BLUNT` or `EDGE`.
- **contact:** Surface area of impact (High = slash, Low = pierce).
- **penetration:** Depth of strike (Ignored for `BLUNT`).
- **verb2nd / verb3rd:** Strings for logs (e.g., `bash:bashes`).
- **noun:** Weapon part (e.g., `blade`, `head`). Use `NO_SUB` for none.
- **velocity:** Momentum multiplier (Standard: 1000, Whip: 5000).

## Example: Battle Axe
```text
[ITEM_WEAPON:ITEM_WEAPON_AXE_BATTLE]
    [NAME:battle axe:battle axes]
    [SIZE:800]
    [SKILL:AXE]
    [TWO_HANDED:37500]
    [MINIMUM_SIZE:30000]
    [MATERIAL_SIZE:3]
    [ATTACK:EDGE:20000:8000:slash:slashes:blade:1250]
    [ATTACK:EDGE:50:4000:stab:stabs:point:1000]
    [ATTACK:BLUNT:20000:4000:bash:bashes:flat:1250]
```
