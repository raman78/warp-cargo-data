# warp-cargo-data

An automated mirror of the [STO Wiki](https://stowiki.net) Cargo tables,
published as plain JSON.

This repository contains **data only** — no tooling. Files are refreshed every
8 hours and a commit is made only when the data has actually changed, so the
history doubles as a changelog of the wiki's item database.

## Files

| File | Cargo table | Contents |
|---|---|---|
| `cargo/equipment.json` | `Infobox` | weapons, consoles, devices, kits, ground gear |
| `cargo/ship_list.json` | `Ships` | ship roster |
| `cargo/traits.json` | `Traits` | personal and reputation traits |
| `cargo/starship_traits.json` | `StarshipTraits` | starship traits |
| `cargo/doffs.json` | `Doffs` | duty officers |
| `cargo/modifiers.json` | `Modifiers` | equipment modifiers |
| `cargo/specializations.json` | `Specializations` | captain specializations |

Each file is a JSON array of rows. `Page` is the wiki page the row came from
(Cargo's built-in `_pageName`); the remaining keys are the table's own fields.
Every field the table defines is included, so these are supersets of the
narrower selections other mirrors publish.

Values carry one HTML-unescape pass. Rows are sorted by page and name so that
diffs between refreshes stay readable.

## Attribution

All content originates from [stowiki.net](https://stowiki.net) and remains
under that wiki's licence and terms. This repository is an unofficial mirror,
not affiliated with the STO Wiki, Cryptic Studios, or Star Trek Online. If you
reuse this data, attribute the STO Wiki.

Data is fetched at a polite rate from a normal, logged-out browser session.
