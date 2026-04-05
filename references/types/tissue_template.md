# Tissue Template Tokens (`[OBJECT:TISSUE_TEMPLATE]`)

Tissue templates define the properties of organic materials used in body parts (e.g., SKIN, MUSCLE, BONE).

## Identification & Appearance
- `[TISSUE_NAME:singular:plural]` - Name of the tissue. Plural can be `NP` (No Plural) or `STP` (Standard Plural).
- `[TISSUE_SHAPE:shape]` - Physical form: `LAYER` (normal behaviour), `STRANDS` (allows spinning into thread), `FEATHERS` (causes edged attacks to pass through), `SCALES`, or `CUSTOM`.
- `[COSMETIC]` - Tissue is for appearance only; no structural impact.
- `[STYLEABLE]` - Can be styled (e.g., hair/beards) if defined in entity.

## Material & State
- `[TISSUE_MATERIAL:material_token]` - Links to a material (e.g., `LOCAL_CREATURE_MAT:SKIN`).
- `[TISSUE_MAT_STATE:state]` - Forces a state: `SOLID`, `LIQUID`, `GAS`, `SOLID_POWDER`.
- `[TISSUE_LEAKS]` - Tissue leaks if layers above are pierced.

## Structural & Physical
- `[RELATIVE_THICKNESS:value]` - Thickness relative to other layers. Higher is harder to penetrate.
- `[STRUCTURAL]` - Holds the body part together; fracturing disables the part.
- `[CONNECTS]` - Part is not severed until all `CONNECTS` tissues are severed.
- `[CONNECTIVE_TISSUE_ANCHOR]` - Site for ligaments/tendons; damage disables the limb.
- `[SUBORDINATE_TO_TISSUE:tissue]` - Attached to another tissue (e.g., hair to skin); falls off if parent is destroyed.
- `[INSULATION:value]` - Provides heat insulation.
- `[THICKENS_ON_STRENGTH]` - Thickness scales with creature strength.
- `[THICKENS_ON_ENERGY_STORAGE]` - Thickness (like fat) scales with food/exercise.

## Physiological & Healing
- `[HEALING_RATE:value]` - Healing speed (lower is faster). If omitted, never heals.
- `[VASCULAR:value]` - Bleeding rate (higher is more).
- `[ARTERIES]` - Contains arteries; edged attacks cause major blood loss.
- `[MAJOR_ARTERIES]` - Severe bleeding when damaged, regardless of `VASCULAR`.
- `[PAIN_RECEPTORS:value]` - Amount of pain felt when damaged.
- `[SCARS]` - Tissue leaves a scar after healing.
- `[SETTABLE]` - Requires a bone doctor to "set" before healing.
- `[SPLINTABLE]` - Can be fixed with a cast/splint.
- `[MUSCULAR]` - Affects nerve location and limb utility.

## Functional & Sensory
- `[FUNCTIONAL]` - Performs a vital function; stops if tissue is destroyed.
- `[THOUGHT]` - Required for movement/breathing (brain tissue).
- `[SIGHT]`, `[BREATHE]`, `[HEAR]`, `[SMELL]`, `[FLIGHT]` - Specific sensory/locomotive functions.

## Creature-Level Overrides (`TL_`)
Used within `[SELECT_TISSUE_LAYER]` or `BP_LAYERS` in creature raws:
- `[TL_RELATIVE_THICKNESS:value]`
- `[TL_VASCULAR:value]`
- `[TL_PAIN_RECEPTORS:value]`
- `[TL_HEALING_RATE:value]`
- `[TL_CONNECTS]`
- `[TL_MAJOR_ARTERIES]`
