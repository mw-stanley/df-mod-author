# Item Tokens (`[OBJECT:ITEM]`)

The `[OBJECT:ITEM]` header acts as a container for various specific item definitions (e.g., weapons, armor, tools). While each sub-type has its own unique tokens, they share several core properties.

## 1. Shared Core Tokens
These tokens are common across most item types:
- `[NAME:singular:plural]` - The display name of the item.
- `[ADJECTIVE:string]` - Adds a descriptive prefix to the name.
- `[VALUE:n]` - Base monetary value.
- `[MATERIAL_SIZE:n]` - Determines material cost and weight.
- `[METAL_ARMOR_LEVEL:n]` - Sets effectiveness and "metal" status for uniforms.
- `[DESCRIPTION:text]` - Flavor text (common for tools and artifacts).

## 2. Storage & Containers
Tokens used for items that can hold other objects or liquids:
- `[CONTAINER]` - Item acts as a container (e.g., bags, bins).
- `[STORAGE:n]` - Capacity of the container.
- `[CAN_HOLD_LIQUID]` - Allows storage of liquids (e.g., buckets, flasks).

## 3. Structural Context
- **Independent Definitions:** Specific item types are defined using their own headers within an `[OBJECT:ITEM]` file:
    - `[ITEM_WEAPON:ID]` -> See [item_weapon.md](item_weapon.md)
    - `[ITEM_ARMOR:ID]` -> See [item_armor.md](item_armor.md)
    - `[ITEM_TOOL:ID]` -> See [item_tool.md](item_tool.md)
- **Sub-References:** For type-specific logic (like weapon attacks or armor coverage), consult the specialized sub-references in `references/types/`.

## Usage
Item definitions are found in `item_*.txt` files. They bridge the gap between materials and creature equipment.
