# Creature Tokens (`[OBJECT:CREATURE]`)

Creature definitions define a species, its sub-types (castes), biology, behavior, and personality.

## 1. Basic Identity & Visuals
- `[NAME:singular:plural:adjective]` - The species name.
- `[CASTE_NAME:singular:plural:adjective]` - Specific name for individuals of that caste.
- `[CREATURE_TILE:char]` - ASCII map symbol.
- `[COLOR:foreground:background:brightness]` - Tile color (0-7).
- `[DESCRIPTION:text]` - Flavor text for the creature.
- `[GENERAL_BABY_NAME:singular:plural]` - Name for babies.
- `[GENERAL_CHILD_NAME:singular:plural]` - Name for children.

## 2. Castes & Selection
Castes define sexes, sub-species, or special variations (e.g., workers vs. queens).
- `[CASTE:ID]` - Starts a new caste definition.
- `[SELECT_CASTE:ID]` - Re-selects a caste (or `ALL`) for modification.
- `[USE_CASTE:NewID:OldID]` - Inherits properties from an existing caste.
- `[POP_RATIO:number]` - Relative frequency of the caste in the population.
- `[MALE]` / `[FEMALE]` - Defines biological sex.

## 3. Biology & Lifespan
- `[MAXAGE:min:max]` - Natural lifespan in years.
- `[BABY:years]` / `[CHILD:years]` - Age thresholds for life stages.
- `[BODY_SIZE:years:days:size]` - Volume in cm³ at a specific age.
- `[BODY:parts...]` - Anatomical structure (references `OBJECT:BODY`).
- `[BODY_DETAIL_PLAN:plan:args...]` - Mass-applies materials/tissues.
- `[BLOOD:material:state]` - What the creature bleeds.
- `[INTELLIGENT]` - Shorthand for `CAN_SPEAK` and `CAN_LEARN`.
- `[CAN_LEARN]` - Allows skill gain and professions.
- `[CAN_SPEAK]` - Allows speech and social interactions.

## 4. Behavior & Temperament
- `[BENIGN]` - Non-aggressive; flees unless cornered.
- `[LARGE_PREDATOR]` - Aggressive; attacks smaller creatures.
- `[CRAZED]` - Always berserk; attacks non-species members.
- `[FLEEQUICK]` - Flees at the first sign of resistance.
- `[PRONE_TO_RAGE:chance]` - % chance to enrage upon seeing non-friends.
- `[CARNIVORE]` / `[HERBIVORE]` / `[OMNIVORE]` - Diet.
- `[GRAZER:value]` - Requires pasture (higher value = eats less).
- `[HUNTS_VERMIN]` - Kills nearby vermin.

## 5. Mannerisms
Mannerisms add flavor descriptions to behavior. Some require body part strings to correctly identify the anatomy being used.

### Standalone Mannerisms
- `[MANNERISM_LAUGH]`
- `[MANNERISM_SMILE]`
- `[MANNERISM_WALK]`
- `[MANNERISM_SIT]`
- `[MANNERISM_BREATH]`
- `[MANNERISM_POSTURE]`
- `[MANNERISM_STRETCH]`
- `[MANNERISM_EYELIDS]`

### Mannerisms Requiring Body Part Strings
- `[MANNERISM_FINGERS:singular:plural]` (e.g., `[MANNERISM_FINGERS:finger:fingers]`)
- `[MANNERISM_NOSE:string]` (e.g., `[MANNERISM_NOSE:nose]`)
- `[MANNERISM_EAR:string]` (e.g., `[MANNERISM_EAR:ear]`)
- `[MANNERISM_HEAD:string]` (e.g., `[MANNERISM_HEAD:head]`)
- `[MANNERISM_EYES:string]` (e.g., `[MANNERISM_EYES:eyes]`)
- `[MANNERISM_MOUTH:string]` (e.g., `[MANNERISM_MOUTH:mouth]`)
- `[MANNERISM_HAIR:string]` (e.g., `[MANNERISM_HAIR:hair]`)
- `[MANNERISM_KNUCKLES:string]` (e.g., `[MANNERISM_KNUCKLES:knuckles]`)
- `[MANNERISM_LIPS:string]` (e.g., `[MANNERISM_LIPS:lips]`)
- `[MANNERISM_CHEEK:string]` (e.g., `[MANNERISM_CHEEK:cheek]`)
- `[MANNERISM_NAILS:string]` (e.g., `[MANNERISM_NAILS:nails]`)
- `[MANNERISM_FEET:string]` (e.g., `[MANNERISM_FEET:feet]`)
- `[MANNERISM_ARMS:string]` (e.g., `[MANNERISM_ARMS:arms]`)
- `[MANNERISM_HANDS:string]` (e.g., `[MANNERISM_HANDS:hands]`)
- `[MANNERISM_TONGUE:string]` (e.g., `[MANNERISM_TONGUE:tongue]`)
- `[MANNERISM_LEG:string]` (e.g., `[MANNERISM_LEG:leg]`)

## 6. Personality Facets
Defines the statistical spread of personality traits for a species.

- **Syntax:** `[PERSONALITY:FACET:P1:P2:P3]`
    - `P1`: Minimum value (0-100).
    - `P2`: Median/Common value (0-100).
    - `P3`: Maximum value (0-100).

- **Facet Values (0-100):**
    - `0-24`: Lowest/Very Low.
    - `25-39`: Low.
    - `40-60`: Neutral (No report).
    - `61-75`: High.
    - `76-100`: Very High/Highest.

- **Full Facet List:** See [references/shared/personality_facets.md](../shared/personality_facets.md) for the list of all 50 facets and their descriptions.
