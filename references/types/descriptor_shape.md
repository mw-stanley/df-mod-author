# Descriptor Shape Tokens (`[OBJECT:DESCRIPTOR_SHAPE]`)

Descriptor shapes define the forms of engravings, gems, and dice.

## Core Tokens
- `[DESCRIPTOR_SHAPE:ID]` - Starts a new shape definition.
- `[NAME:singular:plural]` - The name and plural form of the shape (e.g., `[NAME:cross:crosses]`).
- `[ADJ:string]` - An adjective paired with the name (e.g., `[ADJ:thin]`).
- `[TILE:char/number]` - The character or tile ID used for engravings or items.
- `[CATEGORY:id]` - Groups the shape (Vanilla: `SIMPLE`, `PLATONIC`, `DICE`).
- `[SIDES:number]` - Specifically used for **dice** to define the number of sides.
- `[WORD:word]` - Effect currently unknown.

## Gem Usage Patterns
Shapes can specify how they appear in gem descriptions:
- `[GEMS_USE_ADJ]` - Result: `[ADJ] + [material]` (e.g., "thin conglomerate").
- `[GEMS_USE_NOUN]` - Result: `[material] + [NAME]` (e.g., "conglomerate cross").
- `[GEMS_USE_ADJ_NOUN]` - Result: `[ADJ] + [material] + [NAME]` (e.g., "thin conglomerate cross").

## Usage
- **Engravings:** Defines the available shapes for engravers to carve.
- **Dice:** Uses the `[SIDES:...]` token and `DICE` category.
- **Items:** Shapes for cut gems and other objects.
- **Descriptions:** Used in flavor text for various objects.

## Example
```text
[DESCRIPTOR_SHAPE:STAR_FIVE_POINTED]
    [NAME:five-pointed star:five-pointed stars]
    [ADJ:pointed]
    [TILE:15]
    [CATEGORY:SIMPLE]
```
