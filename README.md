# warp-cargo-data

An automated mirror of the [STO Wiki](https://stowiki.net) Cargo tables,
published as plain JSON.

This repository contains **data only** — no tooling.

Refreshes are driven from a maintainer's workstation, because the wiki sits
behind a bot challenge that only a real browser clears. The intent is daily,
but a refresh happens only while that machine is running, so treat these files
as *usually recent* rather than guaranteed fresh. A commit is made only when
the data has actually changed, so the history doubles as a changelog of the
wiki's item database — and the gaps between commits are honest about when
nothing moved.

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
