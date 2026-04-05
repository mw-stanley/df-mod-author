# Body Tokens (`[OBJECT:BODY]`)

Body definitions establish the anatomical structure of a creature, including parts, hierarchies, and biological functions.

## Definition & Structure
- `[BODY:ID]` - Defines a set of body parts that can be applied to a creature.
- `[BP:id:singular:plural]` - Starts a new body part definition. Use `STP` for standard plurals.
- `[NUMBER:value]` - Creates multiple identical parts (e.g., 10 fingers) under one definition.
- `[INDIVIDUAL_NAME:singular:plural]` - Names specific parts within a `[NUMBER]` group.
- `[CATEGORY:id]` - Assigns a part to a category (e.g., `HEAD`, `FINGER`, `LIMB`).
- `[DEFAULT_RELSIZE:value]` - Sets the relative size of the part within the creature's body.
- `[INTERNAL]` - Part is inside the body; cannot be directly targeted or severed.
- `[EMBEDDED]` - Part is on the surface of its parent (e.g., eyes on a head).
- `[SMALL]` - Hides the part from general lists; easily lost in world-gen duels.
- `[LEFT]` / `[RIGHT]` - Defines lateral orientation.

## Hierarchy & Connections
- `[CON:part_id]` - Connects this part to a specific parent part.
- `[CON_CAT:category_id]` - Connects this part to all parts of a specific category.
- `[CONTYPE:type]` - Connects to a functional type (e.g., `UPPERBODY`, `HEAD`, `GRASP`).
- `[CONNECTOR]` - Part is a structural bridge (e.g., neck, spine).
- `[JOINT]` - Defines the part as a breakable joint for wrestling.
- `[PREVENTS_PARENT_COLLAPSE]` - Parent is not "destroyed" until this part is (e.g., skull).

## Biological & Sensory Functions
- `[SIGHT]` / `[HEAR]` / `[SMELL]` - Enables sensory capabilities.
- `[MOUTH]` - Identifies the part as a mouth.
- `[BREATHE]` - Required for breathing; damage leads to suffocation.
- `[THOUGHT]` - The brain; damage usually causes instant death.
- `[NERVOUS]` - Nerve hub (e.g., spinal cord); damage causes paralysis.
- `[CIRCULATION]` - Responsible for blood flow.
- `[GUTS]` - Susceptible to nausea/vomiting from "low blows."
- `[UNDER_PRESSURE]` - Part spills out when body is cut (e.g., intestines).

## Combat & Movement
- `[GRASP]` - Allows holding items, wielding weapons, and wrestling.
- `[STANCE]` - Required for standing; loss causes the creature to fall.
- `[LIMB]` - Defines a limb for wrestling and armor coverage.
- `[FLIER]` - Required for flight (if creature has `[FLIER]` token).
- `[DIGIT]` - Defines fingers/toes; enables gouging attacks.
- `[HEAD]` / `[UPPERBODY]` / `[LOWERBODY]` - Defines vital regions and equipment slots.
- `[SKELETON]` - Structural bone framework.
- `[SOCKET]` - Part can be easily knocked out (e.g., teeth).
- `[THROAT]` - Enables targeting for strangulation.

## Miscellaneous
- `[APERTURE]` - Marks an opening (e.g., nostril).
- `[GELDABLE]` - Part can be gelded.
- `[TOTEMABLE]` - Part can be used to make totems.
- `[VERMIN_BUTCHER_ITEM]` - Recoverable from butchered vermin.
