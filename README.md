[README (1).md](https://github.com/user-attachments/files/33067748/README.1.md)
# Smart Escape: Interactive Evacuation Route Simulator

- **Name:** Sara Tasfia
- **Registration number:** `<YOUR-REGISTRATION-NUMBER>`
- **Live site (HTTPS):** `https://github.com/sara-tasfia/devfest--aif_07d22d7391d3406e9186-.git
- **Repository:** `devfest-<YOUR-REGISTRATION-NUMBER>`

Smart Escape is an educational simulation, not a certified real-world evacuation planning tool.

## How to run
No build step. Open the live link above, or open `index.html` in Chrome (or run `python3 -m http.server` in the folder and visit `http://localhost:8000`).
Use **Load sample** for `building.json`, or **Import JSON** for your own file with the same schema.

## Main features
- JSON import with validation (counts, IDs, types, edge references, self-loops, repeated pairs, positive integer costs, initial_state categories). Bad files show a clear error and the previous map stays.
- Map drawn at the supplied coordinates with distinct room, junction and exit shapes, labels and corridor costs.
- Select a start room/junction; the lowest-cost route to an open exit is highlighted with node sequence, exit and total cost.
- Block/unblock rooms, junctions and corridors; close/reopen exits. Each state looks different. Route recalculates instantly.
- Reset restores the file's original `initial_state`.
- "No route available" and "Starting location blocked" messages.
- Bangla and English modes for all main UI text.
- Subtle route-draw and colour transitions (disabled with reduced-motion).

## Routing rules
Dijkstra on edge costs only. Blocked nodes (and their edges), blocked edges and closed exits are excluded. Ties: smallest exit ID, then lexicographically smallest node sequence.

## Bonus features
Keyboard-accessible nodes, dark mode support.

## Known problems
- Very dense or overlapping coordinates can make labels crowded.
- Corridor costs on overlapping lines may overlap.

## AI tools used
Claude (Anthropic)

## Most useful prompt
> "Build a frontend-only Smart Escape evacuation simulator in plain HTML/CSS/JS with SVG. Validate JSON, run Dijkstra on edge costs, exclude blocked nodes/edges and closed exits, break ties by smallest exit ID then smallest node sequence, support hazards, reset and Bangla/English."
