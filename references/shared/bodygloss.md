# Bodygloss Tokens (`[BODYGLOSS]`)

Bodyglosses are used for simple string substitution on a creature's body parts. They allow you to reuse generic body templates while renaming specific parts to fit a creature's anatomy (e.g., changing "feet" to "paws").

## Mechanism
- **Literal Replacement:** The game performs a direct string replacement on the body part's name.
- **Side Effects:** Be careful with short strings, as they will replace any occurrence of the text within a word (e.g., "ear" will also be replaced in "heart").

## 1. Definition (Dictionary)
Definitions are typically found in `OBJECT:BODY` RAW files. They define the "rules" for the substitution.

- **Syntax:** `[BODYGLOSS:ID:singular_orig:singular_new:plural_orig:plural_new]`
- **Example:** `[BODYGLOSS:PAW:foot:paw:feet:paws]`

## 2. Application (Trigger)
Applications are found in `OBJECT:CREATURE` RAW files. This tells a specific creature to apply the substitution rules.

- **Syntax:** `[BODYGLOSS:ID]`
- **Example:** `[BODYGLOSS:PAW]`
    - A body part originally named "second right foot" will now be displayed in-game as "second right paw."

## Common Examples
- `[BODYGLOSS:HOOF:foot:hoof:feet:hooves]`
- `[BODYGLOSS:CLAW_HAND:hand:claw:hands:claws]`
- `[BODYGLOSS:INSECT_UPPERBODY:upper body:thorax:upper bodies:thoraxes]`

## Placement Rules
| Role | File Location | Context |
| :--- | :--- | :--- |
| **Definition** | `OBJECT:BODY` files | Defined anywhere in the file. |
| **Application** | `OBJECT:CREATURE` files | Placed beneath a `[CREATURE:ID]` definition. |
