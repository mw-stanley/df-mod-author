# Biome Tokens

Biome tokens are used in RAW files to define the environments where creatures, plants, and entities can be found. These are most commonly used with the `[BIOME:<TOKEN>]` tag.

## Biome Sets (Groups)

These tokens encompass multiple individual biomes and are commonly used for broad distribution.

| Token | Description |
| :--- | :--- |
| **ALL** | Every biome except subterranean ones. |
| **ANY_LAND** | All land biomes (excludes oceans, lakes, and pools). |
| **NOT_FREEZING** | All land biomes except Mountain, Glacier, and Tundra. |
| **ANY_TEMPERATE** | All temperate biomes. |
| **ANY_TROPICAL** | All tropical biomes. |
| **ANY_FOREST** | All forest types (Taiga, Coniferous, Broadleaf). |
| **ANY_DESERT** | Badlands, Rocky Wasteland, and Sand Deserts. |
| **ANY_TEMPERATE_BROADLEAF** | Temperate broadleaf forests, grasslands, savannas, shrublands, and marshes. |
| **ANY_TROPICAL_BROADLEAF** | Tropical dry/moist broadleaf forests, grasslands, savannas, shrublands, and marshes. |

---

## Individual Biome Tokens

### Land Biomes

| Token | Category |
| :--- | :--- |
| **MOUNTAIN** | Mountains |
| **GLACIER** | Polar |
| **TUNDRA** | Polar |
| **TAIGA** | Taiga |
| **FOREST_TEMPERATE_CONIFER** | Temperate Coniferous Forest |
| **FOREST_TEMPERATE_BROADLEAF** | Temperate Broadleaf Forest |
| **FOREST_TROPICAL_CONIFER** | Tropical Coniferous Forest |
| **FOREST_TROPICAL_DRY_BROADLEAF** | Tropical Dry Broadleaf Forest |
| **FOREST_TROPICAL_MOIST_BROADLEAF** | Tropical Moist Broadleaf Forest |
| **GRASSLAND_TEMPERATE** | Temperate Grassland |
| **GRASSLAND_TROPICAL** | Tropical Grassland |
| **SAVANNA_TEMPERATE** | Temperate Savanna |
| **SAVANNA_TROPICAL** | Tropical Savanna |
| **SHRUBLAND_TEMPERATE** | Temperate Shrubland |
| **SHRUBLAND_TROPICAL** | Tropical Shrubland |
| **DESERT_BADLAND** | Badlands Desert |
| **DESERT_ROCK** | Rocky Desert |
| **DESERT_SAND** | Sand Desert |

### Wetlands (Swamps & Marshes)

| Token | Category |
| :--- | :--- |
| **SWAMP_TEMPERATE_FRESHWATER** | Temperate Freshwater Swamp |
| **SWAMP_TEMPERATE_SALTWATER** | Temperate Saltwater Swamp |
| **SWAMP_TROPICAL_FRESHWATER** | Tropical Freshwater Swamp |
| **SWAMP_TROPICAL_SALTWATER** | Tropical Saltwater Swamp |
| **SWAMP_MANGROVE** | Tropical Saltwater (Mangrove) |
| **MARSH_TEMPERATE_FRESHWATER** | Temperate Freshwater Marsh |
| **MARSH_TEMPERATE_SALTWATER** | Temperate Saltwater Marsh |
| **MARSH_TROPICAL_FRESHWATER** | Tropical Freshwater Marsh |
| **MARSH_TROPICAL_SALTWATER** | Tropical Saltwater Marsh |

### Water Biomes

| Token | Category |
| :--- | :--- |
| **OCEAN_ARCTIC** | Arctic Ocean |
| **OCEAN_TEMPERATE** | Temperate Ocean |
| **OCEAN_TROPICAL** | Tropical Ocean |
| **LAKE_TEMPERATE_FRESHWATER** | Temperate Freshwater Lake |
| **LAKE_TEMPERATE_BRACKISHWATER** | Temperate Brackish Lake |
| **LAKE_TEMPERATE_SALTWATER** | Temperate Saltwater Lake |
| **LAKE_TROPICAL_FRESHWATER** | Tropical Freshwater Lake |
| **LAKE_TROPICAL_BRACKISHWATER** | Tropical Brackish Lake |
| **LAKE_TROPICAL_SALTWATER** | Tropical Saltwater Lake |
| **POOL_TEMPERATE_FRESHWATER** | Temperate Freshwater Pool |
| **POOL_TEMPERATE_BRACKISHWATER** | Temperate Brackish Pool |
| **POOL_TEMPERATE_SALTWATER** | Temperate Saltwater Pool |
| **POOL_TROPICAL_FRESHWATER** | Tropical Freshwater Pool |
| **POOL_TROPICAL_BRACKISHWATER** | Tropical Brackish Pool |
| **POOL_TROPICAL_SALTWATER** | Tropical Saltwater Pool |

### Subterranean (Underground)

| Token | Category |
| :--- | :--- |
| **SUBTERRANEAN_WATER** | Underground Water |
| **SUBTERRANEAN_CHASM** | Underground Chasm |
| **SUBTERRANEAN_LAVA** | Underground Lava |
