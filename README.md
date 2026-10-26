# finns-facets-data (private)

Data for the Finn's Facets & Finds page. After editing any file here, reload the page. **Codex → Database check** flags mistakes.

## spells.json
319 D&D 5e spells (mostly SRD 5.1). Add a spell by adding an entry to the `"spells"` list:

```json
{"name": "Fireball", "level": 3, "school": "Evocation"}
```

- `name` must be unique — work orders and the Codex's cut counts match spells by name, so don't rename one that's already in use.
- `level`: 0 (cantrip) to 9.
- `school`: one of Abjuration, Conjuration, Divination, Enchantment, Evocation, Illusion, Necromancy, Transmutation (spelled exactly, capitalized).
- Order doesn't matter; the tool sorts them.

## relics.json
Add a relic by adding an entry to the `"relics"` list:

```json
{
 "id": "relic-21",
 "name": "Anchor of the Drowned Queen",
 "size": "Medium",
 "base": 320,
 "description": "What it is and what it shows when it wakes.",
 "sockets": [
  {"school": "Abjuration", "level": 2},
  {"school": "Divination", "level": 0},
  {"school": "Evocation", "level": 1}
 ]
}
```

- `id` must be unique and never change once used — the Codex counts finds by it.
- `size` and `base`: Small 100–200, Medium 250–400, Large 500–800, Monumental 1,000–1,500 Cr.
- Socket count: Small 2–3, Medium 3–5, Large 5–7, Monumental 7–10.
- Each socket needs at least one spell of that school and level in spells.json (there's no 3rd-level Enchantment, for example), or it can never be filled.

## factions.json
Organizations and people for each faction; commissions read "Faction on behalf of X". The file is shaped like this (one faction shown; the real file has all eight under `"factions"`):

```json
{
 "planes": ["Alara", "Amonkhet", "...every plane..."],
 "factions": {
  "peer": {
   "name": "Peerage Assembly & Heraldic Council",
   "organizations": [
    {"id": "aldermoor", "name": "House Aldermoor", "planes": ["Belenon"], "note": "Knightly house with strict heraldry"}
   ],
   "people": [
    {"name": "Lord Castellan Ives", "title": "castellan", "org": "aldermoor"},
    {"name": "Dame Isolde Marrow", "title": "private collector", "planes": ["Serra's Realm"]}
   ]
  }
 }
}
```

To add an organization, add an entry to that faction's `"organizations"` list. To add a person, add one to its `"people"` list — the first person above is linked to House Aldermoor (and uses its plane); the second is independent and lists her own plane.

- Faction keys stay `adv`, `arc`, `sch`, `col`, `peer`, `syn`, `tem`, `forge`.
- Organization: `id` (unique in its faction), `name`, `planes`, optional `note`.
- Person: `name`, optional `title`, optional `org` (an organization id in the same faction). A linked person uses the org's planes unless they list their own `planes`.
- `planes` at the top lists every plane from the Timeline Notes; the Database check uses it to catch typos.

The starter organizations and people are drafts — rename, add or delete freely.

## save.json
Written by the page. Don't hand-edit while the page is open on another device.

Spell names from the D&D 5e System Reference Document 5.1 are used under CC-BY-4.0 (Wizards of the Coast).
