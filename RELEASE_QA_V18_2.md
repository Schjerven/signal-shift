# SIGNAL SHIFT — V18.2 verification

**Source of truth:** `main/index.html` (Git blob `8c0077816a3ede286283b4304aa3094c39cee9f4`).

**Scope:** Minimal pause-screen improvement only. Keep one prominent, central **FORTSETT** button when paused. Hide other resume affordances while paused, then restore the normal pause controls after resuming. No changes to game rules, music data, control bindings, collectibles, SHIFT logic, or expanded-mode behavior.

## Automated browser QA (Chromium)

| Device viewport | Start | Single resume | Resume | Expand / X | No scroll | No JS errors |
|---|---|---|---|---|---|---|
| Desktop 1440×900 | PASS | PASS | PASS | PASS | PASS | PASS |
| Mobile 390×844 | PASS | PASS | PASS | PASS | PASS | PASS |
| Small mobile 320×568 | PASS | PASS | PASS | PASS | PASS | PASS |
| Landscape 568×320 | PASS | PASS | PASS | PASS | PASS | PASS |

Additional checks:
- Settings music on/off: PASS (QA build).
- Share-score window, rendered score, close button: PASS (QA-injected score of 123).
- Actual final HTML with embedded music: decode/start, playback time advancing, pause/resume: PASS in Chromium.
- Music payload: same as V18.1 (1,830,780 base64 characters).
- JS game logic: unchanged except UI pause-state class.
- Visual review: paused screen screenshots in desktop and portrait mobile test environments.

## Release gate not yet closed

- Physical Samsung touch/swipe/playback check.
- Browser QA on the freshly deployed GitHub Pages site (tool environment cannot reach its domain).
- Independent confirmation of Suno music publication rights.

The repository is public and GitHub Pages is configured. Treat this as a **published test candidate**, not a fully verified cross-device release.
