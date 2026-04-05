# Descriptor Color Tokens (`[OBJECT:DESCRIPTOR_COLOR]`)

Descriptor colors define named color values (e.g., `RED`, `DEEP_BLUE`) used for creature appearance, item variations, and patterns.

## Required Tokens
- `[DESCRIPTOR_COLOR:ID]` - Starts a new color definition.
- `[NAME:string]` - The in-game name of the color.
- `[RGB:r:g:b]` - Additive RGB value (0-255). Used for visual approximation in-game.
- `[WORD:tag]` - Associates the color with a language word for naming historical figures - these language words are defined in the language RAWs.

## Usage
- **Creature Appearance:** Used in `TL_COLOR_MODIFIER` to define skin, hair, or eye color.
- **Patterns:** Referenced in `DESCRIPTOR_PATTERN` via `CP_COLOR`.
- **Items:** Used for item variations and descriptions.

## Example
```text
[DESCRIPTOR_COLOR:MOSS_GREEN]
    [NAME:moss green]
    [RGB:173:223:173]
    [WORD:GREEN]
```
