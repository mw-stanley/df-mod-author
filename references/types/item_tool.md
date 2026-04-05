# Tool Tokens (`[ITEM_TOOL]`)

Tools are multi-purpose items that range from kitchenware and storage to minecarts and stepladders.

## 1. Core Tokens
- `[ITEM_TOOL:ID]` - Starts a new tool definition.
- `[NAME:singular:plural]` - Display name.
- `[VALUE:n]` - Base monetary value.
- `[TILE:n]` - Map character.
- `[SIZE:n]` / `[WEIGHT:n]` - Volume in cm³.
- `[DESCRIPTION:text]` - Flavor text.
- `[FURNITURE]` - Stored in furniture stockpiles; affects crafting skill.

## 2. Tool Uses (`TOOL_USE`)
The `[TOOL_USE:argument]` token defines the specific function of the tool.

| Argument | Description |
| :--- | :--- |
| `LIQUID_COOKING` | Used for cooking liquids (e.g., Cauldron). |
| `LIQUID_SCOOP` | Used for scooping (e.g., Ladle). |
| `GRIND_POWDER_RECEPTACLE` | Mortar. |
| `GRIND_POWDER_GRINDER` | Pestle. |
| `MEAT_CARVING` / `MEAT_BONING` | Carving/Boning knives. |
| `MEAT_SLICING` / `MEAT_CLEAVING` | Slicing/Cleaving knives. |
| `HOLD_MEAT_FOR_CARVING` | Carving fork. |
| `MEAL_CONTAINER` | Small bowl. |
| `LIQUID_CONTAINER` | Jug. |
| `FOOD_STORAGE` | Large pot. |
| `HIVE` | Beekeeping hive. |
| `NEST_BOX` | Poultry egg-laying box. |
| `SMALL_OBJECT_STORAGE` | Pouch. |
| `TRACK_CART` | Minecart. |
| `HEAVY_OBJECT_HAULING` | Wheelbarrow. |
| `STAND_AND_WORK_ABOVE` | Stepladder. |
| `ROLL_UP_SHEET` | Scroll rollers. |
| `PROTECT_FOLDED_SHEETS` | Book binding. |
| `CONTAIN_WRITING` | Scroll or Quire. |
| `BOOKCASE` | Library storage. |
| `DISPLAY_OBJECT` | Pedestal or Display case. |
| `PLACE_OFFERING` | Altar. |
| `DIVINATION` / `GAMES_OF_CHANCE` | Dice. |

## 3. Combat Tokens
If a tool is intended for use as a weapon (e.g., knives), it uses standard weapon tokens:
- `[ATTACK:type:contact:penetration:verb2nd:verb3rd:noun:velocity]`
- `[SKILL:token]` (e.g., `DAGGER`, `AXE`).
- `[TWO_HANDED:size]` / `[MINIMUM_SIZE:size]`.

## 4. Material Flags
- `[WOOD_MAT]`, `[METAL_MAT]`, `[STONE_MAT]`, `[BONE_MAT]`, `[LEATHER_MAT]`, `[GLASS_MAT]`, `[CERAMIC_MAT]`, `[HARD_MAT]`, `[SOFT_MAT]`.
