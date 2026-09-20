# SPOT THE BUG

A tiny hunting game by Ernie: a herd of bugs wanders the field. One of them behaves
wrongly. Click it before the timer drains.

Every anomaly in the game mirrors a real bug archetype:
- moves too fast (unbalanced speed)
- turns early (off-by-one on a waypoint)
- frame stutter (per-frame hitch)
- phases through walls (missing collision)
- pulses off-beat (desynced timer)

## Builds
- `spot-the-bug-v10a.html` - first release candidate
- `spot-the-bug-v10b.html` - feature-flood build (bug-story experiment)
- `spot-the-bug-v12-20260919.1.html` - current build: repaired music/timing, cage, radar, cargo, terrain

## How to play
Download an HTML file and open it in any browser, or play the hosted build (link on request).

## V.1 gardens (2026-09-19)
- `spot-the-bug-colony-v1.html` - ants, 5 attempts
- `spot-the-bug-hive-v1.html` - bees, 4 attempts (playtest build)

## V.2 hit-stop patch (2026-09-20)
Feature: catch juice. Applied to both gardens.
- `spot-the-bug-colony-v2.html` - ants, polished graphics (Astra reskin) + hit-stop/quick-draw
- `spot-the-bug-hive-v1.1.html` - bees + hit-stop/quick-draw

What the patch adds:
- Hit-stop: on a correct catch the sim freezes 150ms and the screen flashes white (alpha fades over the 150ms).
- Quick draw: catch within 3s of the round start = x1.5 score, with a "QUICK DRAW! +50% SCORE" tag.
- Haptics: 40ms buzz on a correct catch, [80,40,80] pattern on a wrong click (guarded, mobile only).

Engine unchanged. Verified headless (Chromium): 14 checks green on each file - quick-draw math,
3s cutoff, hit-stop freeze, flash draw clean, vibration guarded, all 8 anomalies finite, freeze,
heist, 3 layouts, empty error ledger.
