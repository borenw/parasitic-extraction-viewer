# Parasitic Extraction (.cir) Table Viewer

Single-file, offline HTML tool. Drop a SPICE parasitic-extraction netlist (`.cir`) — or paste it — and get sortable/filterable tables plus copy-paste-ready Confluence/Markdown markup for:

- 🔗 **Mutual Inductance** — `K` couplings → M = k·√(Lₐ·L_b)
- 🌀 **Self Inductance** — `L` elements
- ⚡ **Mutual Capacitance** — coupling caps between nets
- ⏚ **Self Capacitance to GND** — caps to ground

## Filters

Each 🔍 box does a case-insensitive **substring** match, or a **glob** match when you use `*` / `?` (e.g. `*PWM*`, `CS_?`). Boxes also match the element name, so typing `K12` in a Net box finds that coupling.

The **Mutual Inductance** table ships with default filters **Net1 = `*PWM*`** and **Net2 = `*CS*`** — it opens showing the PWM-aggressor → current-sense-victim inductive couplings. Clear the boxes to see everything.

**Live:** https://borenw.github.io/parasitic-extraction-viewer/ — Page 35 of [Bo's Engineering Curriculum](https://borenw.github.io/).
