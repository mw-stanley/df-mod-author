# Descriptor Pattern Tokens (`[OBJECT:DESCRIPTOR_PATTERN]`)

Descriptor patterns define complex visual designs (e.g., stripes, spots) and link them to colors.

## Core Tokens
- `[DESCRIPTOR_PATTERN:ID]` - Starts a new pattern definition.
- `[NAME:string]` - The name of the pattern.
- `[PATTERN:type]` - Defines the pattern logic. Supported types:
    - `SPOTS` - Requires at least one `CP_COLOR`. **Crashes** if no `CP_COLOR` is provided.
    - `STRIPES` - Takes any amount of `CP_COLOR` tokens.
    - `MOTTLED` - Takes any amount of `CP_COLOR` tokens.
    - `IRIS_EYE` - Technically takes any amount, but **only shows the third** `CP_COLOR` provided. **Crashes** if none are provided. If only 1 or 2 are provided, the tissue is described as "transparent."
    - `PUPIL_EYE` - Technically takes any amount, but **only shows the second** `CP_COLOR` provided. **Crashes** if none are provided. If only 1 is provided, the tissue is described as "transparent."

- `[CP_COLOR:color_id]` - Links a `DESCRIPTOR_COLOR` to the pattern.

## Usage
- **Creature Appearance:** Used in `TL_COLOR_MODIFIER` to apply patterns to specific body part groups.

## Example
```text
[DESCRIPTOR_PATTERN:TIGER_STRIPES]
    [NAME:tiger stripes]
    [PATTERN:STRIPES]
    [CP_COLOR:BLACK]
    [CP_COLOR:ORANGE]
```
