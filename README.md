# Leonida Verification Desk

**Which community GTA 6 map markers survived contact with the real game.**

Every marker on every community Leonida map was traced by hand from trailers and
screenshots, because the game did not exist yet. On 19 November 2026 it exists,
and every one of those markers becomes checkable. Nobody is keeping score.

This desk keeps score. It records, per marker, whether the community was right —
**Confirmed**, **Corrected**, or **Debunked** — with the evidence and a measured
position error where the marker was misplaced.

---

## Why this is worth building

There are more than twenty GTA 6 map sites and virtually all of them published a
marker set built from pre-release material. The verification record is the one
artifact the ecosystem lacks and cannot easily produce: it requires structured
per-marker verdicts, not prose. Once it exists it is licensable back to the map
sites whose data it verifies, because a corrected marker is a map that stops
misleading its readers.

## What is in here

| Path | What it is |
|---|---|
| `index.html` | The public site. Reads the two JSON payloads and renders the tally. |
| `ingest.py` | Dependency-free importer: pulls the licensed datasets into the register. |
| `data/register.json` | The register — one row per marker, in the desk's column order. |
| `data/corrections.json` | The publishable output — verdicts, accuracy, correction list. |
| `data/seed-regions.json` | The six officially named regions, always carried. |
| `vercel.json` | CORS and caching headers so the JSON is consumable from anywhere. |
| `leonida-verification-desk.xlsx` | The working desk for launch night, where verdicts get entered. |

## Workflow

```bash
# 1. Seed the register from the live CC BY 4.0 sources
python3 ingest.py --register

# 2. Work the desk on launch night
#    Open leonida-verification-desk.xlsx, enter a verdict + evidence per marker.

# 3. Export the register to JSON, drop it at data/register.json, then:
python3 ingest.py --corrections
```

The site is static and needs no build step:

```bash
python3 -m http.server 5173
```

## Verdict vocabulary

| Verdict | Meaning |
|---|---|
| **Confirmed** | Marker is where and what the community said. |
| **Corrected** | Real, but the position or description was wrong. Fix recorded. |
| **Debunked** | No such place exists in the shipping game. |
| **Inconclusive** | Could not reach or could not tell. Not scored as a failure. |

## Sources and licence

Built on other people's cartography, used under the terms they set:

| Dataset | Publisher | Licence | Records |
|---|---|---|---|
| GTA VI Landmarks Data & map tiles (Yanis base art) | gtadb.org | CC BY 4.0 | 2,198 |
| GTA 6 map points | mapheist.com | CC BY 4.0 | 94 (61 with a real-world prototype) |
| Weekly GTA data feed | grindmap.com | CC BY 4.0 | — |

CC BY 4.0 permits commercial reuse with attribution. Attribution strings are
embedded in both JSON payloads so a consumer that never loads the page still
carries the credit.

**Not covered by that licence:** Rockstar Games artwork, trailers, screenshots
and the official printable Leonida map. Those are not redistributed here.

> Marker coordinates are community estimates assembled from pre-release material.
> They are not official data, and a marker being present in this register is not
> confirmation by Rockstar Games.

## Disclaimer

Leonida Verification Desk is an independent project. It is not affiliated with,
endorsed by, sponsored by or associated with Rockstar Games, Take-Two
Interactive or any of their subsidiaries. "Grand Theft Auto", "GTA", "Vice City"
and "Rockstar" are trademarks of their respective owners, used here for
identification and commentary only.

## Licence

Code: MIT. Data payloads: CC BY 4.0, attributed as above.
