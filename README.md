# Parasitic Extraction (.cir) Table Viewer

Single-file, offline HTML tool. Drop a SPICE parasitic-extraction netlist (`.cir`) — or paste it — and get sortable/filterable tables plus copy-paste-ready Confluence/Markdown markup for:

- 🔗 **Mutual Inductance** — `K` couplings → M = k·√(Lₐ·L_b)
- 🌀 **Self Inductance** — `L` elements
- ⚡ **Mutual Capacitance** — coupling caps between nets
- ⏚ **Self Capacitance to GND** — caps to ground

## `.subckt` & Ansoft node translation

Handles netlists wrapped in `.SUBCKT … .ENDS` (dot-commands are skipped; the elements inside are still parsed). If the file carries an **Ansoft/ANSYS extraction header**:

```
*BEGIN ANSOFT HEADER
* node 1 CS0:U1_CS0_86_src
* node 2 PWM0:U2_HS_gate
...
*END ANSOFT HEADER
```

the numeric node references are translated to those signal names in every table. Toggle it with the **"Translate node #s → names"** checkbox (on by default).

## Filters

Each 🔍 box does a case-insensitive **substring** match, or a **glob** match when you use `*` / `?` (e.g. `*PWM*`, `CS_?`). Boxes also match the element name, so typing `K12` in a Net box finds that coupling.

The **Mutual Inductance** table ships with default filters **Net1 = `*PWM*`** and **Net2 = `*CS*`** — it opens showing the PWM-aggressor → current-sense-victim inductive couplings. Clear the boxes to see everything.

## Source window

A 5-line scrollable window of the original `.cir` (with line numbers) sits directly above the Mutual Inductance table. **Click any row** and the window highlights and zooms to that coupling's `K` line in the source.

**Live:** https://borenw.github.io/parasitic-extraction-viewer/ — Page 35 of [Bo's Engineering Curriculum](https://borenw.github.io/).
