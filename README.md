# Finn's Facets & Finds

Business tool for Finley "Finn" Anderson — dredging, chiseling, cutting, work orders, factions, relics, perks and lives — in one HTML page.

The page is public (GitHub Pages). Everything that's yours — the spell database, the relic database and the save — lives in a **private** repo, `finns-facets-data`, the same split as Loot Ledger.

## Setup

1. **Create two repos** on GitHub under `8BitBoar`:
   - `finns-facets` — **public**. Upload `index.html` and this README.
   - `finns-facets-data` — **private**. Upload `spells.json`, `relics.json` and its README. (`save.json` is created by the page on first connect.)
2. **Turn on Pages** for `finns-facets`: Settings → Pages → Deploy from a branch → `main` / root. The page will be at `https://8bitboar.github.io/finns-facets/`.
3. **Make a fine-grained token**: GitHub → Settings → Developer settings → Fine-grained tokens → Generate.
   - Repository access: *Only select repositories* → `finns-facets-data`
   - Permissions → Repository → **Contents: Read and write**
4. Open the page → **Settings** → owner `8BitBoar`, repo `finns-facets-data`, branch `main`, paste the token → **Save & connect**.

The token is stored only in that browser. Do it once per device (laptop, iPhone); the save syncs through the data repo.

## Saving

- Every change saves to the browser instantly.
- **Auto-save** (Settings): *After changes* pushes `save.json` to GitHub ~12 seconds after you stop clicking; *After End Day* pushes once per day; *Manual* only when you press the button.
- If two devices both changed the save, the page asks which one to keep.
- **Download save.json** in Settings gives you a manual backup.

## Daily loop

1. **Sea** — tap a Dredge Node, sail out (pay its fuel), dredge until the node fades or the hold fills, return home to unload.
2. **Workroom** — chisel geodes, then cut stones plain or with a spell.
3. **Work Orders** — accept offers, fill each slot from inventory (or "Cut from rough" straight into a slot, "Order parts" for mountings/ornaments), assemble, pack, send.
4. **Relics** — socket matching spell-cut gems; once active, crate it and send it to the Survey.
5. **End Day** — registered factions roll for commissions, new nodes appear, bath soaks finish, offers expire, deadlines tick; a new month brings dues and the monthly life.
