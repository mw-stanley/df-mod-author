# Creature Variation Tokens (`[OBJECT:CREATURE_VARIATION]`)

Creature variations act as macros or scripts that modify a base creature's raw data. They are commonly used to create templates like `GIANT_CREATURE` or `MAN_CREATURE`.

## Core Modification Tokens

### 1. Addition (`CV_NEW_TAG` / `CV_ADD_TAG`)
Adds a new token (including arguments) to the creature definition.
- **Syntax:** `[CV_NEW_TAG:token_to_add]`
- **Example:** `[CV_NEW_TAG:BIOME:ANY_FOREST]` adds `[BIOME:ANY_FOREST]` to the creature. See [references/shared/biomes.md](../shared/biomes.md) for a list of valid biome tokens.

### 2. Removal (`CV_REMOVE_TAG`)
Removes existing tokens that match the specified argument chain.
- **Syntax:** `[CV_REMOVE_TAG:argument_chain]`
- **Example:** `[CV_REMOVE_TAG:BODY:HUMANOID]` removes `[BODY:HUMANOID:2EYES]` but leaves `[BODY:QUADRUPED]`.

### 3. Conversion (`CV_CONVERT_TAG` Block)
Used to find and replace specific strings within existing creature tokens.
- **Syntax:**
    - `[CV_CONVERT_TAG]` - Starts the conversion block.
    - `[CVCT_MASTER:leading_args]` - Limits the search to tokens starting with these arguments (e.g., `BODY`).
    - `[CVCT_TARGET:search_string]` - The text to find.
    - `[CVCT_REPLACEMENT:new_string]` - The text to replace the target with. If blank, the target is removed.

## Conditional Modifications (`CTAG`)
These only execute if a specific argument passed to the variation matches a required value.
- `[CV_NEW_CTAG:arg_num:match_val:token]`
- `[CV_REMOVE_CTAG:arg_num:match_val:arg_chain]`
- `[CV_CONVERT_CTAG]` - Followed by `CVCT_` tokens, used conditionally.

## Application Order
The game processes modifications in a fixed sequence, regardless of their order in the variation file:
1. **Removals:** All `CV_REMOVE_TAG` tokens are processed first.
2. **Conversions:** All `CV_CONVERT_TAG` blocks are processed second (processed bottom-to-top).
3. **Additions:** All `CV_NEW_TAG` tokens are processed last (processed top-to-bottom).

## Usage & Arguments
Variations can accept arguments using `!ARG1`, `!ARG2`, etc., making them highly flexible templates.

**Example Variation Definition:**
```text
[CREATURE_VARIATION:GIANT_CREATURE]
    [CV_REMOVE_TAG:NAME]
    [CV_NEW_TAG:NAME:giant !ARG1:giant !ARG2:giant !ARG3]
    [CV_NEW_TAG:BODY_SIZE:0:0:1000000]
```

**Applying the Variation:**
```text
[CREATURE:RAT]
    [APPLY_CREATURE_VARIATION:GIANT_CREATURE:rat:rats:ratty]
```
In this case, `!ARG1` becomes `rat`, `!ARG2` becomes `rats`, and `!ARG3` becomes `ratty`.
