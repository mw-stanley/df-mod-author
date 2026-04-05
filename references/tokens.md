# Dwarf Fortress RAW Object Types

Use this table to identify the `[OBJECT:TYPE]` based on the filename prefix of the RAW file you are editing. This is the first step before consulting specific sub-references for tokens.

## RAW Types & Filename Prefixes

| Object Type | Filename Prefix | Description | Sub-Reference |
| :--- | :--- | :--- | :--- |
| **BODY** | `body_` | Defines body parts and structures. | [body.md](types/body.md) |
| **BODY_DETAIL_PLAN** | `b_detail_plan_` | Defines materials and tissues for body parts. | [body_detail_plan.md](types/body_detail_plan.md) |
| **BUILDING** | `building_` | Defines custom workshops and smelters. | [building.md](types/building.md) |
| **CREATURE** | `creature_` | Defines creatures, stats, and behaviors. | [creature.md](types/creature.md) |
| **CREATURE_VARIATION** | `c_variation_` | Templates for modifying creatures. | [creature_variation.md](types/creature_variation.md) |
| **DESCRIPTOR_COLOR** | `descriptor_color_`| Named colors for patterns. | [descriptor_color.md](types/descriptor_color.md) |
| **DESCRIPTOR_PATTERN**| `descriptor_pattern_`| Color patterns for creatures. | [descriptor_pattern.md](types/descriptor_pattern.md) |
| **DESCRIPTOR_SHAPE** | `descriptor_shape_` | Shapes for engravings/descriptions. | [descriptor_shape.md](types/descriptor_shape.md) |
| **ENTITY** | `entity_` | Civilizations, ethics, and social structures. | [entity.md](types/entity.md) |
| **GRAPHICS** | `graphics_` | Graphic tiles and animations. | [graphics.md](types/graphics.md) |
| **INTERACTION** | `interaction_` | Magical or special abilities. | [interaction.md](types/interaction.md) |
| **INORGANIC** | `inorganic_` | Stones, metals, and inorganic materials. | [inorganic.md](types/inorganic.md) |
| **ITEM** | `item_` | Base category for all items. | [item.md](types/item.md) |
| **LANGUAGE** | `language_` | Words and symbols for languages. | [language.md](types/language.md) |
| **MATERIAL_TEMPLATE** | `material_template_`| Templates for material properties. | [material_template.md](types/material_template.md) |
| **MUSIC** | `music_` | Audio file assignments. | [music.md](types/music.md) |
| **PALETTE** | `palette_` | Color palettes for graphics. | [palette.md](types/palette.md) |
| **PLANT** | `plant_` | Plants, trees, and their materials. | [plant.md](types/plant.md) |
| **REACTION** | `reaction_` | Workshop recipes and processes. | [reaction.md](types/reaction.md) |
| **SOUND** | `sound_` | Sound effect associations. | [sound.md](types/sound.md) |
| **TEXT_SET** | `text_set_` | Conversation strings. | [text_set.md](types/text_set.md) |
| **TILE_PAGE** | `tile_page_` | Maps image files to IDs. | [tile_page.md](types/tile_page.md) |
| **TISSUE_TEMPLATE** | `tissue_template_` | Templates for organic tissues. | [tissue_template.md](types/tissue_template.md) |

## Item Sub-Types

When the prefix is `item_`, the specific type is usually indicated by the second part of the filename:

- `item_ammo.txt` -> [ITEM_AMMO.md](types/item_ammo.md)
- `item_armor.txt` -> [ITEM_ARMOR.md](types/item_armor.md)
- `item_food.txt` -> [ITEM_FOOD.md](types/item_food.md)
- `item_gloves.txt` -> [ITEM_GLOVES.md](types/item_gloves.md)
- `item_helm.txt` -> [ITEM_HELM.md](types/item_helm.md)
- `item_instrument.txt` -> [ITEM_INSTRUMENT.md](types/item_instrument.md)
- `item_pants.txt` -> [ITEM_PANTS.md](types/item_pants.md)
- `item_shield.txt` -> [ITEM_SHIELD.md](types/item_shield.md)
- `item_shoes.txt` -> [ITEM_SHOES.md](types/item_shoes.md)
- `item_siegeammo.txt` -> [ITEM_SIEGEAMMO.md](types/item_siegeammo.md)
- `item_tool.txt` -> [ITEM_TOOL.md](types/item_tool.md)
- `item_toy.txt` -> [ITEM_TOY.md](types/item_toy.md)
- `item_trapcomp.txt` -> [ITEM_TRAPCOMP.md](types/item_trapcomp.md)
- `item_weapon.txt` -> [ITEM_WEAPON.md](types/item_weapon.md)
