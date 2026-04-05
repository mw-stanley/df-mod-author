# Entity Tokens (`[OBJECT:ENTITY]`)

Entity definitions define civilizations, their species, ethics, cultural values, and internal hierarchies (positions).

## 1. Basic Identity & Control
- `[ENTITY:ID]` - Starts a new entity definition.
- `[TRANSLATION:language]` - Sets the language (e.g., `DWARF`, `HUMAN`, `ELF`).
- `[SITE_CONTROLLABLE]` - Enables **Fortress Mode** for this entity.
- `[ALL_MAIN_POPS_CONTROLLABLE]` - Enables **Adventure Mode** for this entity.
- `[CREATURE:creature_id]` - Defines the primary species of the civilization.

## 2. Civilization Properties
- `[START_BIOME:biome]` - Biomes where the civ can start and build.
- `[BIOME_SUPPORT:biome:freq]` - Controls territorial expansion speed.
- `[DEFAULT_SITE_TYPE:type]` - Sets the default structure.
    - **Valid Types:** `CITY`, `DARK_FORTRESS`, `TREE_CITY`, `CAVE`, `CAVE_DETAILED`, `PLAYER_FORTRESS`, `MONUMENT`.
- `[MAX_POP_NUMBER:n]` - Hard limit on total historical population.
- `[MAX_SITE_POP_NUMBER:n]` - Max population per individual site.
- `[SCHOLAR:type]` - Enables scholar types.
    - **Valid Types:** `ALL`, `ASTRONOMER`, `CHEMIST`, `DOCTOR`, `ENGINEER`, `GEOGRAPHER`, `HISTORIAN`, `MATHEMATICIAN`, `NATURALIST`, `PHILOSOPHER`.

## 3. Ethics
Ethics define a civilization's moral stance and are a primary cause of inter-species wars.
- **Syntax:** `[ETHIC:category:reaction]`

### Ethic Categories:
`ASSAULT`, `EAT_SAPIENT_KILL`, `EAT_SAPIENT_OTHER`, `KILL_ANIMAL`, `KILL_ENEMY`, `KILL_ENTITY_MEMBER`, `KILL_NEUTRAL`, `KILL_PLANT`, `LYING`, `MAKE_TROPHY_ANIMAL`, `MAKE_TROPHY_SAME_RACE`, `MAKE_TROPHY_SAPIENT`, `OATH_BREAKING`, `SLAVERY`, `THEFT`, `TORTURE_ANIMALS`, `TORTURE_AS_EXAMPLE`, `TORTURE_FOR_FUN`, `TORTURE_FOR_INFORMATION`, `TREASON`, `TRESPASSING`, `VANDALISM`.

### Reaction Values:
`NOT_APPLICABLE`, `ACCEPTABLE`, `PERSONAL_MATTER`, `JUSTIFIED_IF_NO_REPERCUSSIONS`, `JUSTIFIED_IF_GOOD_REASON`, `JUSTIFIED_IF_EXTREME_REASON`, `JUSTIFIED_IF_SELF_DEFENSE`, `ONLY_IF_SANCTIONED`, `MISGUIDED`, `SHUN`, `APPALLING`, `PUNISH_REPRIMAND`, `PUNISH_SERIOUS`, `PUNISH_EXILE`, `PUNISH_CAPITAL`, `UNTHINKABLE`, `REQUIRED`.

## 4. Cultural Values (Beliefs)
Sets the cultural stance on specific concepts.
- **Syntax:** `[VALUE:token:n]` (-50 to 50).
- **Randomized:** `[VARIABLE_VALUE:token:min:max]`.
- **Reference:** See [references/shared/values.md](../shared/values.md) for the exhaustive list of 33 value tokens.

## 5. Positions (Nobles & Officials)
Defines the internal hierarchy and duties of the civilization.
- `[POSITION:ID]` - Begins a position definition (e.g., `KING`, `MAYOR`).
- `[NAME:singular:plural]` - Basic title.
- `[NAME_MALE]` / `[NAME_FEMALE]` - Gender-specific titles.
- `[PRECEDENCE:n]` - Social importance (lower is more important; Monarch is 1).
- `[SUCCESSION:type]` - How the next holder is chosen.
    - **Valid Types:** `BY_HEIR`, `BY_POSITION:position_code`.
- `[RESPONSIBILITY:type]` - Defines the job.
    - **Valid Responsibilities:** `ACCOUNTING`, `ADVISE_LEADERS`, `ATTACK_ENEMIES`, `BUILD_MORALE`, `BUILDING_SAFETY`, `COLLECT_TAXES`, `CONSTRUCTION_PERMITS`, `DELIVER_MESSAGES`, `EQUIPMENT_MANIFESTS`, `ESCORT_TAX_COLLECTOR`, `ESPIONAGE`, `ESTABLISH_COLONY_TRADE_AGREEMENTS`, `EXECUTIONS`, `FIRE_SAFETY`, `FOOD_SUPPLY`, `HEALTH_MANAGEMENT`, `JUDGE`, `LAW_ENFORCEMENT`, `LAW_MAKING`, `MAINTAIN_BRIDGES`, `MAINTAIN_ROADS`, `MAINTAIN_SEWERS`, `MAINTAIN_TUNNELS`, `MAKE_INTRODUCTIONS`, `MAKE_PEACE_AGREEMENTS`, `MAKE_TOPIC_AGREEMENTS`, `MANAGE_ANIMALS`, `MANAGE_LEADER_HOUSEHOLD_CLEANLINESS`, `MANAGE_LEADER_HOUSEHOLD_DRINKS`, `MANAGE_LEADER_HOUSEHOLD_FOOD`, `MANAGE_PRODUCTION`, `MEET_WORKERS`, `MILITARY_GOALS`, `MILITARY_STRATEGY`, `OVERSEE_LEADER_HOUSEHOLD`, `PATROL_TERRITORY`, `PREPARE_LEADER_MEALS`, `RECEIVE_DIPLOMATS`, `RELIGION`, `SORT_AMMUNITION`, `TAME_EXOTICS`, `TRADE`, `UPGRADE_SQUAD_EQUIPMENT`.
- `[SITE]` - Marks the position as a site-level title (e.g., Mayor) rather than a civilization-level one (e.g., King).
