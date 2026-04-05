# Personality Facets

Personality facets define the psychological traits of a creature, measured on a scale of 0 to 100. In creature RAWs, they are defined using a statistical spread: `[PERSONALITY:FACET:P1:P2:P3]`.

## Exhaustive Facet List

1.  **LOVE_PROPENSITY**: How easily a creature falls in love and develops positive feelings.
2.  **HATE_PROPENSITY**: How quickly a creature forms negative views and hatred.
3.  **ENVY_PROPENSITY**: Tendency to feel jealous of others' status or possessions.
4.  **CHEER_PROPENSITY**: How often a creature feels joy and maintains optimism.
5.  **DEPRESSION_PROPENSITY**: Susceptibility to feeling sad, discouraged, or dejected.
6.  **ANGER_PROPENSITY**: How quickly a creature becomes angry or enters a rage.
7.  **ANXIETY_PROPENSITY**: Level of nervousness, tension, and overall calm.
8.  **LUST_PROPENSITY**: Frequency and intensity of lustful passion.
9.  **STRESS_VULNERABILITY**: How well a creature handles pressure without becoming helpless.
10. **GREED**: Desire for wealth, possessions, and material goods.
11. **IMMODERATION**: Tendency to give in to strong cravings and overindulgence.
12. **VIOLENT**: Inclination toward physical confrontations and brawling.
13. **PERSEVERANCE**: How stubbornly a creature sticks with a task versus giving up.
14. **WASTEFULNESS**: Carefulness with resources and effort in projects.
15. **DISCORD**: Preference for harmonious living versus chaos and tumult.
16. **FRIENDLINESS**: How agreeable or quarrelsome a creature is socially.
17. **POLITENESS**: Adherence to etiquette, decorum, and rules of living.
18. **DISDAIN_ADVICE**: Reliance on own counsel versus seeking help from others.
19. **BRAVERY**: Courage or cowardice when confronted with danger.
20. **CONFIDENCE**: Belief in one's own abilities and likelihood of success.
21. **VANITY**: Concern for appearance, talents, and accomplishments.
22. **AMBITION**: Drive to better one's situation and pursue success.
23. **GRATITUDE**: Need to reciprocate favors and show appreciation.
24. **IMMODESTY**: Preference for austerity versus extravagant presentation.
25. **HUMOR**: Sense of humor and ability to find things funny.
26. **VENGEFUL**: Likelihood of seeking retribution and holding grievances.
27. **PRIDE**: Sense of self-worth, from humility to self-importance.
28. **CRUELTY**: Tendency toward sadism versus mercy and compassion.
29. **SINGLEMINDED**: Focus on a single task versus being scatterbrained.
30. **HOPEFUL**: Level of optimism and hope for the future.
31. **CURIOUS**: Eagerness to learn versus respect for privacy.
32. **BASHFUL**: Sensitivity to shyness and the opinions of others.
33. **PRIVACY**: Willingness to share personal information versus being private.
34. **PERFECTIONIST**: Attention to detail and desire to do things correctly.
35. **CLOSEMINDED**: Openness to changing one's mind or new ideas.
36. **TOLERANT**: Comfort with differences in culture, lifestyle, or appearance.
37. **EMOTIONALLY_OBSESSIVE**: Depth and persistence of emotional bonds with others.
38. **SWAYED_BY_EMOTIONS**: How much a creature is moved by others' emotions.
39. **ALTRUISM**: Internal reward and drive for assisting those in need.
40. **DUTIFULNESS**: Sense of duty, obligation, and respect for vows.
41. **THOUGHTLESSNESS**: Deliberation before acting versus acting impulsively.
42. **ORDERLINESS**: Obsession with neatness, organization, and placement.
43. **TRUST**: How naturally trustful or suspicious a creature is.
44. **GREGARIOUSNESS**: Enjoyment of company versus preferring solitude.
45. **ASSERTIVENESS**: How much a creature puts forth its point of view.
46. **ACTIVITY_LEVEL**: Natural pace of living, from languid to high-energy.
47. **EXCITEMENT_SEEKING**: Drive to seek out stressful or dangerous situations.
48. **IMAGINATION**: Inclination toward fantasy versus being grounded.
49. **ABSTRACT_INCLINED**: Preference for philosophical ideas over practical concerns.
50. **ART_INCLINED**: How much a creature is moved by art and beauty.

## Facet Conflicts & Interactions

### 1. Conflicts with Beliefs (Values)
Facets can conflict with a creature's internal beliefs (`OBJECT:ENTITY` values). This causes internal psychological friction.

| Facet | Conflicts with Belief (Value) |
| :--- | :--- |
| `LOVE_PROPENSITY` | `ROMANCE` |
| `CHEER_PROPENSITY` | `MERRIMENT` |
| `IMMODERATION` | `SELF_CONTROL` |
| `VIOLENT` | `TRANQUILITY`, `MARTIAL_PROWESS` |
| `PERSEVERANCE` | `PERSEVERANCE` (Value) |
| `DISCORD` | `HARMONY` |
| `FRIENDLINESS` | `HARMONY`, `FRIENDSHIP` |
| `POLITENESS` | `DECORUM` |
| `CRUELTY` | `POWER` |
| `PRIVACY` | `STOICISM` |
| `ALTRUISM` | `SACRIFICE` |
| `DUTIFULNESS` | `LAW`, `LOYALTY`, `INDEPENDENCE` |
| `EXCITEMENT_SEEKING` | `TRANQUILITY` |
| `ART_INCLINED` | `ARTWORK`, `NATURE` |

### 2. Grudge Formation
Certain facets contribute to "clashes of personality" between different creatures. A grudge is likely to form if one creature's facet value is **>60** and the other's is **<40**.

**Grudge-contributing facets:**
`VIOLENT`, `WASTEFULNESS`, `DISCORD`, `FRIENDLINESS`, `POLITENESS`, `VANITY`, `AMBITION`, `GRATITUDE`, `IMMODESTY`, `HUMOR`, `VENGEFUL`, `CRUELTY`, `HOPEFUL`, `CURIOUS`, `PERFECTIONIST`, `TOLERANT`, `ALTRUISM`, `DUTIFULNESS`, `THOUGHTLESSNESS`, `ORDERLINESS`, `EXCITEMENT_SEEKING`, `IMAGINATION`, `ABSTRACT_INCLINED`, `ART_INCLINED`.

### 3. Conceptual & Skill Opposites
While independent, these facets often represent opposing psychological states or interact to determine social skills:

- **Joy vs. Sadness:** `CHEER_PROPENSITY` (Optimism) vs. `DEPRESSION_PROPENSITY` (Discouragement).
- **Courage vs. Anxiety:** `BRAVERY` (Fearless) vs. `ANXIETY_PROPENSITY` (Nervous/Tense).
- **Social vs. Withdrawn:** `GREGARIOUSNESS` (Enjoys company) vs. `BASHFUL` (Shyness).
- **Impulse vs. Detail:** `THOUGHTLESSNESS` (No deliberation) vs. `PERFECTIONIST` (Obsessed with detail).
- **Social Skills:** High `BASHFUL` and low `GREGARIOUSNESS` both prevent learning the **Conversationalist** skill.
