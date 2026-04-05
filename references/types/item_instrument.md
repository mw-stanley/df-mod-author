# Instrument Tokens (`[ITEM_INSTRUMENT]`)

Instruments are complex items composed of multiple pieces, defining sound production, pitch, and timbre.

## 1. Core Tokens
- `[ITEM_INSTRUMENT:ID]` - Starts a new instrument definition.
- `[DESCRIPTION:text]` - Flavor text.
- `[MUSIC_SKILL:skill_token]` - Determines skill used:
    - `PLAY_KEYBOARD_INSTRUMENT`
    - `PLAY_STRINGED_INSTRUMENT`
    - `PLAY_WIND_INSTRUMENT`
    - `PLAY_PERCUSSION_INSTRUMENT`
- `[PLACED_AS_BUILDING]` - If present, the instrument is **stationary furniture**. If absent, it is **portable**.

## 2. Instrument Pieces
Define the sub-parts required to craft the instrument.
- `[INSTRUMENT_PIECE:ID:TOOL_TOKEN:singular:plural:mode]`
    - `TOOL_TOKEN`: The item type consumed to make the piece.
    - `mode`: `STANDARD`, `ALWAYS_PLURAL`, `ALWAYS_SINGULAR`.
- `[DOMINANT_MATERIAL_PIECE:ID]` - Sets the primary material for the instrument.
- `SELF` - Use in place of a piece ID if the instrument has no sub-parts.

## 3. Sound Production & Pitch
### Sound Production
- `[SOUND_PRODUCTION:method]` - How sound is made:
    - `PLUCKED_BY_BP`, `STRUCK_BY_BP`, `STRUCK_TOGETHER`, `SHAKEN`.
    - `BLOW_AGAINST_FIPPLE`, `BLOW_OVER_OPENING_SIDE`, `BLOW_OVER_SINGLE_REED`.
    - `BOWED`, `SCRAPED`, `FRICTION`.
    - `AIR_OVER_REED`, `AIR_AGAINST_FIPPLE`, `BAG_OVER_REED`.

### Pitch & Volume
- `[PITCH_CHOICE:method]` - How pitch is varied:
    - `KEYBOARD`, `STOPPING_FRET`, `STOPPING_HOLE`, `SLIDE`, `VALVE_ROUTES_AIR`, `FOOT_PEDALS`.
- `[PITCH_RANGE:min:max]` - Range in cents (middle C is 0).
- `[INDEFINITE_PITCH]` - Used for percussion.
- `[TIMBRE:words]` - `BRIGHT`, `MELLOW`, `HARSH`, `REEDY`, `SONOROUS`.
- `[VOLUME_mB:min:max]` - Volume range in millibels.

## 4. Tuning & Registers
- `[TUNING:method:piece]` - `PEGS`, `TIGHTENING`, `LEVERS`.
- `[REGISTER:min:max:timbre]` - Overrides global timbre for a specific pitch range.
