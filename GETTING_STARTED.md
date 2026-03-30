# RateFinder — Getting Started

## What is RateFinder?

Stop guessing your rates. RateFinder analyzes how YOU actually fly and recommends Betaflight and Actual rates tuned to your stick patterns. Connect your radio, fly some exercises in your simulator, and get a personalized rate profile in minutes.

## What you need

- **FPV simulator** — VelociDrone recommended, but any sim works
- **Radio connected via USB in joystick mode** — EdgeTX: System > Hardware > USB Mode > Joystick
- **RateFinder running alongside your simulator** — both apps open at the same time

## Two ways to use RateFinder

### Path A — Find My Rates (start here if new)

Use this if you want to discover your ideal rates from scratch. Best starting point: fly with Betaflight defaults (RC Rate 1.0, Super Rate 0.70, Expo 0) during the exercises.

**Step by step:**

1. Click **"Find My Rates"** on the Welcome screen
2. Fill in your pilot profile — grip style, spring tension, stick ends, flying style, camera angle
3. Connect your radio and follow the axis calibration wizard — it maps which stick axis controls roll, pitch, yaw, and throttle
4. Push each stick to your comfortable max deflection — not the physical limit, just where you'd naturally max out
5. Tell RateFinder what rates you're flying with in VelociDrone right now — **this is your baseline anchor**. The algorithm computes your new rates relative to these values. BF defaults (RC Rate 1.0, Super Rate 0.70, Expo 0) are recommended for your first run.
6. Fly the 6 calibration exercises in your simulator. Exercises are tailored to your flying style:

   **Racing:**
   - **Exercise 1 — Center Precision:** Hover and hold position. Small corrections only.
   - **Exercise 2 — Hard 180s:** Throttle up, throw full snap 180 turns. Commit to full stick.
   - **Exercise 3 — Splits (S-Turn):** Fly above a gate, invert, dive through. Both directions.
   - **Exercise 4 — Corkscrews:** Arc through gates using combined roll and pitch. Alternate sides.
   - **Exercise 5 — Ladders:** Vertical gate stack — roll and pitch through ascending, then descending.
   - **Exercise 6 — Combo:** Fly naturally on your favorite race track. Mix everything from the previous exercises.

   **Freestyle:**
   - **Exercise 1 — Hover Precision:** Hover and hold position. Small corrections only.
   - **Exercise 2 — Powerloops:** Dive at a structure, full throttle + full back pitch to loop over it.
   - **Exercise 3 — Matty Flips:** Roll inverted, pull back pitch to loop backward over an obstacle.
   - **Exercise 4 — Flicks and Snaps:** Juicy flicks (snap then reverse), full snap rolls, yaw spins.
   - **Exercise 5 — Orbits and Trippy Spins:** Orbit an object, then try inverted orbits with yaw spin.
   - **Exercise 6 — Flow Combo:** Chain tricks naturally — powerloop into matty, stall rewinds, whatever flows.

   **Cinematic:**
   - **Exercise 1 — Extended Hover (45s):** Use the parked car as your point of interest. Set camera tilt to 25°. Frame the car and hold position — zero visible camera movement for the full 45 seconds.
   - **Exercise 2 — Orbit a Point of Interest (45s):** Orbit the car in the parking lot. One direction first, then reverse. Constant radius, camera locked on the car the entire time.
   - **Exercise 3 — Dive and Pull-Out:** Dive toward the tree line at 30-45°. Smooth pull-out to level before reaching the trees. Repeat multiple times — consistent smooth arcs, no jerky inputs.
   - **Exercise 4 — Subject Tracking (45s):** Wait for cars to come into view on the track, then click Go and follow them. Smooth continuous yaw adjustments to keep the car framed. Let the subject lead — you follow.
   - **Exercise 5 — Indoor Flow:** Navigate the bridge and signs on the Drift Track as if doing a real estate shoot. Slow, deliberate movement through tight spaces. Treat every structural element like a room — glide through gaps, reveal architecture, keep all axes at low deflection. No snaps.
   - **Exercise 6 — Cinematic Combo (45s):** Chain a reveal shot (rise over an obstacle to reveal the scene), orbit the parking lot car, a proximity pass along the track, and a pull-back reveal. Fly the Drift Track at cinematic pace.

   **Mixed:** A combination of exercises from all three styles.

7. Review your results on the Rates tab

### Path B — Refine My Rates (use this to iterate)

Use this if you already have rates that feel close but not perfect. Your previous session's final rates (with multipliers applied) are loaded as the starting baseline.

**Step by step:**

1. Click **"Refine My Rates"** and select your saved profile
2. Re-run axis calibration if needed (or skip if your radio is already set up)
3. Your previous rates are pre-loaded into the Known Rates screen — no re-entering values
4. Fly the same 6 exercises for your flying style at full pace
5. Results show adjustments relative to your existing rates — green arrows for increases, orange for decreases

---

## What each flying style profile does

### Racing profile

**Goal:** Tight precision at center stick for gate tracking, high authority at full stick for snaps and direction changes.

**What the exercises measure:**
- **Center Precision** captures your hover corrections — how tight your gate tracking instincts are
- **Hard 180s** and **Ladders** capture your full-deflection commitment — how hard you snap for direction reversals
- **Splits and Corkscrews** capture your mid-range transitions — how you flow between center and full stick through gates

**What the algorithm targets:**
- **High center sensitivity** (100–400 deg/s) — racing pilots need immediate response for line corrections. The gap between center and max rate is large, bridged by higher expo.
- **High max rate** (500–1000 deg/s) — full snaps and 180s require fast rotation to complete before you lose momentum
- **Higher expo** (0.3–1.0) — large gap between center sens and max rate needs a steep expo curve to transition smoothly. Without it, mid-stick feels either too sluggish or too twitchy.

**Typical rate curve shape:** Gradual slope near center (precision for tracking gates), steep ramp toward full stick (authority for snaps and flips).

**Multiplier guidance:** Most racing pilots end up at 1.1x–2.0x roll, 1.0x–1.5x pitch, 1.0x yaw.

---

### Freestyle profile

**Goal:** Smooth, flowing mid-range arcs for tricks with snappy authority at full stick for flicks and snaps.

**What the exercises measure:**
- **Powerloops** and **Matty Flips** capture your sustained mid-range pitch — how you hold arcs through loops and inverted maneuvers
- **Flicks and Snaps** capture your full-deflection speed — how aggressively you commit to juicy flicks and snap rolls
- **Orbits and Trippy Spins** capture your multi-axis coordination — how you hold sustained partial deflections on yaw + roll simultaneously

**What the algorithm targets:**
- **Low center sensitivity** (50–150 deg/s) — freestyle pilots need smooth mid-range for arcs and sustained holds. Low center sens means the transition through mid-stick feels buttery, not jumpy.
- **Moderate max rate** (400–600 deg/s) — enough authority for committed flicks and snaps, but not so high that tricks become uncontrollable
- **Moderate-to-high expo** (0.4–0.8) — bridges the gap between smooth center and snappy edges. The expo curve keeps arcs feeling smooth while still allowing committed full-stick snaps to feel sharp.

**Typical rate curve shape:** Very gentle slope near center (smooth arcs), progressive ramp through mid-range (flowing transitions), sharp steepening near full stick (committed flicks).

**Key insight:** Roll center sensitivity is typically lower than pitch in freestyle — arcs and orbits need smooth roll, while powerloop diameter control needs more pitch authority near center.

**Multiplier guidance:** Start at 1.0x across the board. If flicks feel sluggish, bump roll to 1.2x. Pitch usually stays closer to 1.0x since powerloop feel is more about expo than raw rate.

---

### Cinematic profile

**Goal:** Ultra-smooth, invisible corrections. The audience should never know the camera is on a drone.

**What the exercises measure:**
- **Extended Hover** and **Indoor Flow** capture sub-5% deflection precision — how steady your hands are during sustained shots
- **Orbit** and **Subject Tracking** capture sustained low yaw — how smoothly you can hold a coordinated turn or follow a moving target
- **Dive and Pull-Out** captures mid-range pitch transitions — how smoothly you arc from a dive to level flight

**What the algorithm targets:**
- **Very low center sensitivity** (50–120 deg/s) — cinematic pilots live in the 0–20% deflection range. Low center sensitivity means tiny stick movements produce gentle, filmable motion.
- **Low max rate** (300–500 deg/s) — cinematic flying never uses full deflection. Lower max rates mean the entire stick range produces controllable, smooth output.
- **Moderate expo** (0.4–0.7) — smooths the transition from center to mid-range without making near-center feel dead

**Typical rate curve shape:** Nearly flat near center (ultra-precise micro-corrections), gentle consistent slope through mid-range (smooth transitions for reveals and orbits).

**Multiplier guidance:** Start at 1.0x. Cinematic rates should feel slow and controllable. If anything, you may want to reduce multipliers below 1.0x.

---

### Mixed profile

**Goal:** A balanced rate profile that works across racing, freestyle, and cinematic flying.

**What the exercises measure:** A combination of exercises from all three styles — hover precision, smooth turns, snaps, yaw work, proximity flying, and free combo.

**What the algorithm targets:** Moderate values across all parameters, balanced between precision and authority. Good for pilots who fly multiple styles in a single session or haven't committed to one style yet.

**Multiplier guidance:** Adjust per-axis based on which style you lean toward. Bump roll if you want more freestyle snap, reduce center sensitivity if you want more cinematic smoothness.

---

## Rate convergence — how your rates evolve through calibration

RateFinder doesn't just give you a one-shot recommendation. Each refinement pass brings your rates closer to your natural flying style. Below is real session data showing how rates converge from stock Betaflight defaults through calibration and multiple free fly refinement passes.

### Freestyle convergence example

Known rates anchor: **Betaflight defaults** (RC Rate 1.0, Super Rate 0.70, Expo 0) = Center Sensitivity 200, Max Rate 667, Expo 0.00. The algorithm computes all values relative to this baseline.

| Stage | Mult | Roll CS | Roll MR | Roll Expo | Pitch CS | Pitch MR | Pitch Expo | Yaw CS | Yaw MR | Yaw Expo |
|-------|------|---------|---------|-----------|----------|----------|------------|--------|--------|----------|
| BF Defaults | 1.0x | 200 | 667 | 0.00 | 200 | 667 | 0.00 | 200 | 667 | 0.00 |
| After Calibration | 1.0x | 132 | 430 | 0.72 | 123 | 434 | 0.76 | 175 | 398 | 0.49 |
| Free Fly #1 (91s) | 1.0x | 92 | 444 | 0.64 | 97 | 446 | 0.72 | 169 | 404 | 0.46 |
| Free Fly #2 (81s) | 1.0x | 53 | 444 | 0.55 | 103 | 446 | 0.76 | 146 | 411 | 0.53 |
| Free Fly #3 (72s) | 1.0x | 62 | 465 | 0.66 | 122 | 460 | 0.69 | 147 | 418 | 0.64 |
| Free Fly #4 (76s) | 1.0x | 62 | 458 | 0.64 | 128 | 460 | 0.66 | 151 | 417 | 0.51 |

**The final freestyle signature:** Low center sensitivity (~60 roll, ~128 pitch), moderate max rate (~458), moderate expo (~0.65). Buttery mid-range arcs with full authority when committing to flicks.

Yaw was the most stable axis throughout — yaw behavior is consistent regardless of which freestyle tricks you do, which is why yaw rates tend to converge fastest.

---

### Racing convergence example

Known rates anchor: **Betaflight defaults** = Center Sensitivity 200, Max Rate 667, Expo 0.00.

| Stage | Mult | Roll CS | Roll MR | Roll Expo | Pitch CS | Pitch MR | Pitch Expo | Yaw CS | Yaw MR | Yaw Expo |
|-------|------|---------|---------|-----------|----------|----------|------------|--------|--------|----------|
| BF Defaults | 1.0x | 200 | 667 | 0.00 | 200 | 667 | 0.00 | 200 | 667 | 0.00 |
| After Calibration | 1.0x | 50 | 503 | 0.53 | 125 | 445 | 0.69 | 172 | 408 | 0.22 |
| Free Fly #1 (95s) | 1.0x | 50 | 553 | 0.37 | 75 | 450 | 0.78 | 156 | 416 | 0.31 |
| Free Fly #2 (84s) | 1.0x | 50 | 540 | 0.40 | 57 | 450 | 0.66 | 158 | 409 | 0.31 |
| Free Fly #3 (76s) | 1.0x | 50 | 540 | 0.34 | 63 | 444 | 0.67 | 157 | 409 | 0.30 |
| → Pilot applied 1.2x roll | 1.2x | 60 | 648 | 0.28 | 63 | 444 | 0.67 | 157 | 409 | 0.30 |
| Free Fly #4 (87s) | 1.2x | 60 | 663 | 0.38 | 58 | 450 | 0.66 | 157 | 416 | 0.35 |
| Free Fly #5 (77s) | 1.2x | 60 | 679 | 0.33 | 59 | 450 | 0.67 | 158 | 422 | 0.33 |
| Free Fly #6 (71s) | 1.2x | 60 | 679 | 0.37 | 58 | 463 | 0.66 | 159 | 423 | 0.32 |
| Free Fly #7 (72s) | 1.2x | 60 | 695 | 0.35 | 57 | 463 | 0.65 | 160 | 422 | 0.30 |

**The final racing signature:** Very low center sensitivity (60 roll at 1.2x, 57 pitch), high max rate (695 roll at 1.2x, 463 pitch), moderate expo (0.35 roll, 0.65 pitch). Tight line corrections at center stick with committed snap authority at full deflection.

---

### Cinematic convergence example

Known rates anchor: **Betaflight defaults** = Center Sensitivity 200, Max Rate 667, Expo 0.00.

| Stage | Mult | Roll CS | Roll MR | Roll Expo | Pitch CS | Pitch MR | Pitch Expo | Yaw CS | Yaw MR | Yaw Expo |
|-------|------|---------|---------|-----------|----------|----------|------------|--------|--------|----------|
| BF Defaults | 1.0x | 200 | 667 | 0.00 | 200 | 667 | 0.00 | 200 | 667 | 0.00 |
| After Calibration | 1.0x | 171 | 367 | 0.20 | 174 | 370 | 0.28 | 170 | 362 | 0.05 |
| Free Fly #1 (76s) | 1.0x | 164 | 368 | 0.24 | 175 | 382 | 0.12 | 172 | 366 | 0.07 |
| Free Fly #2 (102s) | 1.0x | 159 | 368 | 0.43 | 167 | 382 | 0.20 | 172 | 366 | 0.20 |

**The cinematic signature:** High center sensitivity (~160-175), low max rate (~366-382), low expo (0.05–0.43). Converged in just 2 free fly passes — cinematic stick patterns are the most consistent of all three styles.

---

### Reading the convergence table

Two things can change your rates between sessions:

**Algorithm updates** (Free Fly refinement) — the base recommendation changes based on new stick data. The change is driven by your flying patterns, not your input.

**Multiplier adjustments** (pilot override) — you moved a slider. The base recommendation hasn't changed — only your scaling of it has.

If the algorithm keeps pushing a value in one direction across multiple passes, that's a signal your rates genuinely need to change. If you keep overriding with the multiplier in the same direction, consider whether the algorithm's base recommendation is actually correct for you.

---

## Understanding your results

### The values table

| Value | What it means |
|-------|---------------|
| **Center Sensitivity** | How responsive the quad is near center stick. Higher = twitchier. |
| **Max Rate** | Rotation speed in deg/s at full stick deflection. Higher = faster flips. |
| **Expo** | How quickly the curve transitions from center feel to max rate. Higher = more gentle mid-stick. |
| **Confidence** | High/Medium/Low based on how consistent your stick patterns were across exercises. |

### Rate Multiplier sliders

The algorithm gives you a conservative baseline. Use the per-axis multipliers (0.5x to 2.0x) to dial in speed to taste:

- Most racing pilots end up at **1.1x to 2.0x roll**
- Start at 1.0x, fly a few laps in VelociDrone, adjust up if it feels slow
- Expo scales inversely — as you increase the multiplier, expo decreases to keep center feel proportional

### Global Curve Shape sliders

Three sliders that adjust the overall rate curve shape across all axes simultaneously. Use these before the per-axis Roll/Pitch/Yaw multipliers.

**Center Sensitivity (0.5x to 2.0x)**
- Lower (0.5x-0.8x): Higher center sensitivity — snappier response near center stick
- Default (1.0x): Center sensitivity as measured from your flying
- Higher (1.2x-2.0x): Lower center sensitivity — smoother, more forgiving center

**Max Rate (0.5x to 2.0x)**
- Lower (0.5x-0.8x): Lower max rate — more controlled full-stick authority
- Default (1.0x): Max rate as measured from your snap velocity
- Higher (1.2x-2.0x): Higher max rate — more authority at full deflection

**Expo (0.5x to 2.0x)**
- Lower (0.5x-0.8x): More curved — forgiving smooth transitions through mid-range
- Default (1.0x): Expo shaped by your mid-range time distribution
- Higher (1.2x-2.0x): More linear — direct proportional response throughout stick range

### Throttle settings

RateFinder also recommends Throttle Mid (your hover point) and Throttle Expo (softness around hover). These are computed from your actual throttle patterns during the exercises.

---

## Detailed workflows

### Racing workflow (VelociDrone)

Total time: ~45 minutes for calibration + 6 free fly passes.

**Setup:**
1. Open VelociDrone
2. Load the **WT Racing RateFinder** map (download from the WILDTYPE Discord)
3. Set your VelociDrone rates to **Betaflight defaults**: RC Rate 1.0, Super Rate 0.70, Expo 0
4. Open RateFinder alongside VelociDrone
5. Click **"Find My Rates"**, fill in your profile, complete axis calibration

**Calibration (exercises 1-6):**
6. **Exercise 1 (Center Precision):** Lower your camera tilt to ~25° for hover stability. Hover and make small corrections.
7. **Exercise 2-5:** Raise camera tilt back to your racing angle (typically 45-60°). Execute Hard 180s, Splits, Corkscrews, and Ladders on the map.
8. **Exercise 6 (Combo):** Load your **favorite race track**. Fly 3 laps at full race pace. (Example: Sandlot S1 Track 2)
9. Review results on the Rates tab

**Free Fly refinement (6 passes):**
10. Copy your new rates into VelociDrone (Copy Actual CLI or Copy BF CLI)
11. Click **"Refine in Free Fly"** in RateFinder
12. Fly 3 laps at **full race pace** — committed snaps, gate corrections, proximity lines. The algorithm needs your actual racing inputs, not a casual warmup.
13. Stop, review updated rates. Repeat steps 10-13 two more times (3 passes total, 9 laps).
14. After 3 passes, check if roll feels slow. If so, apply **1.2x roll multiplier**.
15. Run 3 more passes with multiplier applied (9 more laps). Copy updated rates each time.

**How to know you're done:**
- Lap times decreasing — the most objective measure
- Feeling less like you're fighting the quad and more like you're flowing through gates
- Diagnostics tab shows jerk decreasing between calibration and free fly
- Rates stabilizing between passes

**Multi-session:** Click **Save Profile** after every session. Next time, load your profile and click **Refine in Free Fly** — your calibration baseline is preserved and refinement picks up where you left off.

---

### Freestyle workflow (VelociDrone)

**Setup:**
1. Open VelociDrone and load the **WT Freestyle RateFinder** map
2. Set rates to **Betaflight defaults**: RC Rate 1.0, Super Rate 0.70, Expo 0
3. Open RateFinder → **"Find My Rates"** → fill in profile (select Freestyle) → axis calibration

**Calibration (exercises 1-6):**
4. Execute Hover Precision, Powerloops, Matty Flips, Flicks/Snaps, Orbits, and Flow Combo
5. Review results on the Rates tab

**Free Fly refinement (3-4 passes):**
6. Copy rates into VelociDrone → click **"Refine in Free Fly"**
7. Fly 60-90 seconds — include committed powerloops and snaps, not just orbits and cruising
8. Stop, review, copy updated rates. Repeat 2-3 more times.
9. Freestyle rates typically converge at 1.0x — if arcs feel smooth and flicks feel snappy, you're done.

**How to know you're done:**
- Mid-range arcs feel buttery, not jerky
- Full-stick flicks feel sharp and committed
- No oscillation at center stick after tricks
- Correction frequency decreasing in Diagnostics

---

### Cinematic workflow (VelociDrone)

**Setup:**
1. Open VelociDrone and load **Freestyle Map — Drift Track**
2. Click the **car icon (bottom right)** → set to **3 cars** (required for Subject Tracking exercise)
3. Set rates to **Betaflight defaults**: RC Rate 1.0, Super Rate 0.70, Expo 0
4. Open RateFinder → **"Find My Rates"** → fill in profile (select Cinematic) → axis calibration

**Calibration (exercises 1-6):**
5. Extended Hover (45s) → Orbit POI (45s) → Dive and Pull-Out → Subject Tracking (45s) → Indoor Flow → Cinematic Combo (45s)
6. Review results on the Rates tab

**Free Fly refinement (2-3 passes):**
7. Copy rates into VelociDrone → click **"Refine in Free Fly"**
8. Fly the Drift Track cinematically for 60-90 seconds — orbits, tracking shots, reveals, proximity passes
9. Cinematic rates converge fast — typically 2 passes is enough

**How to know you're done:**
- Camera movement feels invisible
- Orbits hold consistent radius without drift
- Very low jerk shown in Diagnostics

---

### General workflow (any style)

1. Run Path A with BF defaults
2. Complete all 6 exercises for your flying style
3. Copy rates into your simulator
4. Click "Refine in Free Fly" → fly 3 laps or 90+ seconds at full pace → stop
5. Copy updated rates → repeat 3-6 times
6. Adjust multiplier if any axis feels slow
7. **Save your profile** — required for multi-session refinement to work

---

## How RateFinder reads your flying

RateFinder analyzes the **stick distribution patterns** underneath every maneuver. These patterns are consistent per pilot regardless of what they're flying.

### What your stick data reveals

| Metric | What it measures | What it means for rates |
|--------|-----------------|----------------------|
| **CPR — Center Precision Radius** | How far from center your stick drifts during hover/corrections | Higher CPR = wider corrections = lower center sensitivity needed |
| **CMV — Comfortable Max Velocity** | How fast you move the stick during snaps (95th percentile) | Higher CMV = you snap harder = higher max rate appropriate |
| **MDI — Mid-range Distribution Index** | % of active stick time spent between 30-70% deflection | Higher MDI = more time in mid-range = more expo needed |
| **Correction Frequency** | How often you make small corrective inputs | High = fighting your rates — they don't match your instincts |
| **Median Jerk** | Rate of change of stick velocity | High jerk = compensating for wrong rates |
| **Full Deflection Hold** | Average time spent at full stick per snap | Long holds = max rate may be too low |

### How the algorithm anchors to your known rates

RateFinder starts from your **known rates** and adjusts based on your measured stick patterns:

- **Center Sensitivity = known_center × (1.0 - CPR)**
- **Max Rate = known_max × (0.5 + CMV)**
- **Expo = known_expo + (MDI - 0.5) × 0.8**

If you skip the Known Rates screen, RateFinder uses Betaflight defaults (CS 200, MR 667, Expo 0.0).

### Rate fit indicators

After a Free Fly session, the Diagnostics tab shows before/after comparisons:

- **Jerk decreased** → your rates are working. You're flowing, not fighting.
- **Jerk increased** → rates may need adjustment. You're compensating.
- **Correction frequency decreased** → fewer micro-corrections needed. Rates match your instincts.
- **Correction frequency increased** → more corrections than during calibration. Something's off.

---

## Tips

- **Always fly at full pace during exercises and free fly** — conservative flying produces conservative rates
- **Commit to full stick on snap exercises** — the algorithm needs to see your true max deflection speed
- **Save your profile after every session** — this is what allows multi-session refinement to work correctly
- If center stick feels **twitchy**, lower center sensitivity (not expo)
- If full stick feels **sluggish**, increase max rate (not the multiplier)
- **Yaw rates are usually fine at 1.0x** — most pilots only need to adjust roll and pitch
- The **Refine tab** lets you manually edit any value and save iterations with notes
- The **Diagnostics tab** shows all raw analysis data, rate fit indicators, and per-exercise breakdowns

---

## Exporting to your simulator or flight controller

**Copy BF CLI** — paste directly into Betaflight Configurator CLI tab and run `save`.

**Copy Actual CLI** — paste into VelociDrone or Betaflight 4.3+ (Actual rates mode) and run `save`.

**Save Profile** — stores your rates, multipliers, calibration data, and session history. Load it next session to continue refining without re-running calibration.

**Export JSON** — saves the full recommendation as JSON for backup or sharing.

---

## The Results screen tabs

| Tab | What's there |
|-----|-------------|
| **Rates** | Rate curve chart, values table, multiplier sliders, copy/export buttons |
| **Diagnostics** | Session overview, throttle distribution, per-exercise breakdown, per-axis analysis |
| **Profiles** | Current profile, session history, all saved profiles on this machine |
| **Refine** | Manual rate editor — edit values directly and save versions with notes |

---

## Profile storage and backup

Your pilot profiles and session data are stored locally at:

```
C:\Users\<YourUsername>\AppData\Local\RateFinder\
```

This folder is **separate from the app installation** — profiles survive uninstalls and reinstalls. The only way to lose them is manually deleting that folder.

To back up: use **Export JSON** on the Results screen to save a full snapshot of your profile, rates, and session data.

| What | Where |
|------|-------|
| Profiles and sessions | `%LOCALAPPDATA%\RateFinder\saved_sessions\` |
| Profile metadata | `%LOCALAPPDATA%\RateFinder\profiles\` |

---

## Support

- **Discord:** [discord.gg/sscV4g7ECj](https://discord.gg/sscV4g7ECj) — rate tuning help, map downloads, community
- **Website:** [wildtypedrones.com](https://wildtypedrones.com)
- **Instagram / Facebook:** @wildtypefpv
