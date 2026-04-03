# RateFinder — Getting Started

## What is RateFinder?

Stop guessing your rates. RateFinder analyzes how YOU actually fly and recommends Betaflight and Actual rates tuned to your stick patterns. Connect your radio, fly some exercises in your simulator, and get a personalized rate profile in minutes.

## What you need

- **FPV simulator** — VelociDrone recommended, but any sim works
- **Radio connected via USB in joystick mode** — EdgeTX: System > Hardware > USB Mode > Joystick
- **RateFinder running alongside your simulator** — both apps open at the same time

**Troubleshooting radio detection:** If your radio isn't detected, open the Windows Game Controllers panel (Win + R, type `joy.cpl`). If your radio doesn't appear there, RateFinder can't see it either. Ensure USB Joystick mode is active in EdgeTX/OpenTX (System > Hardware > USB Mode > Joystick). If you see a Bluetooth warning in RateFinder, switch to a USB cable connection.

## Two ways to use RateFinder

### Path A — Find My Rates (start here if new)

Use this if you want to discover your ideal rates from scratch. Best starting point: fly with Betaflight defaults (RC Rate 1.0, Super Rate 0.70, Expo 0) during the exercises.

**Step by step:**

1. Click **"Find My Rates"** on the Welcome screen
2. Fill in your pilot profile — grip style, spring tension, stick ends, flying style, camera angle
3. Connect your radio and follow the axis calibration wizard — it maps which stick axis controls roll, pitch, yaw, and throttle. If multiple joystick devices are connected (e.g., a radio and a game controller), a selection screen will appear — choose your radio by name.
4. (Optional) Assign a **trigger switch** — flip any spare switch on your radio to use it for starting/stopping recordings without alt-tabbing back to RateFinder
5. Push each stick to your comfortable max deflection — not the physical limit, just where you'd naturally max out
6. Tell RateFinder what rates you're flying with in VelociDrone right now — **this is your baseline anchor**. The algorithm computes your new rates relative to these values. BF defaults (RC Rate 1.0, Super Rate 0.70, Expo 0) are recommended for your first run.
7. Fly the 6 calibration exercises in your simulator. If you assigned a trigger switch, flip it to start each exercise instead of clicking Start — the 30-second timer stops automatically. Exercises are tailored to your flying style:

   **Racing:**
   - **Exercise 1 — Center Precision:** Hover and hold position. Small corrections only.
   - **Exercise 2 — Hard 180s:** Throttle up, throw full snap 180 turns. Commit to full stick.
   - **Exercise 3 — Splits (S-Turn):** Fly above a gate, invert, dive through. Both directions.
   - **Exercise 4 — Corkscrews:** Arc through gates using combined roll and pitch. Alternate sides.
   - **Exercise 5 — Ladders:** Vertical gate stack — roll and pitch through ascending, then descending.
   - **Exercise 6 — Combo:** Fly naturally. Mix everything from the previous exercises.

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
   - **Exercise 6 — Cinematic Combo (45s):** Chain a reveal shot (rise over an obstacle to reveal the scene), orbit the parking lot car, a proximity pass along a structure, and a pull-back reveal. Fly the Drift Track at cinematic pace.

   **Mixed:** A combination of exercises from all three styles.

8. Review your results on the Rates tab

### Path B — Refine My Rates (use this to iterate)

Use this if you already have rates that feel close but not perfect. Your previous session's final rates (with multipliers applied) are loaded as the starting baseline.

**Step by step:**

1. Click **"Refine My Rates"** and select your saved profile
2. Re-run axis calibration if needed (or skip if your radio is already set up)
3. Your previous rates are pre-loaded into the Known Rates screen — no re-entering values
4. Fly the same 6 exercises for your flying style at full pace
5. Results show adjustments relative to your existing rates — green arrows for increases, orange for decreases

## What each flying style profile does

### Racing profile

**Goal:** Tight precision at center stick for gate tracking, high authority at full stick for snaps and direction changes.

**What the exercises measure:**
- **Center Precision** captures your hover corrections — how tight your gate tracking instincts are
- **Hard 180s** and **Ladders** capture your full-deflection commitment — how hard you snap for direction reversals
- **Splits and Corkscrews** capture your mid-range transitions — how you flow between center and full stick through gates

**What the algorithm targets:**
- **High center sensitivity** (100-400 deg/s) — racing pilots need immediate response for line corrections. The gap between center and max rate is large, bridged by higher expo.
- **High max rate** (500-1000 deg/s) — full snaps and 180s require fast rotation to complete before you lose momentum
- **Higher expo** (0.3-1.0) — large gap between center sens and max rate needs a steep expo curve to transition smoothly. Without it, mid-stick feels either too sluggish or too twitchy.

**Typical rate curve shape:** Gradual slope near center (precision for tracking gates), steep ramp toward full stick (authority for snaps and flips).

**Multiplier guidance:** Most racing pilots end up at 1.1x-2.0x roll, 1.0x-1.5x pitch, 1.0x yaw.

---

### Freestyle profile

**Goal:** Smooth, flowing mid-range arcs for tricks with snappy authority at full stick for flicks and snaps.

**What the exercises measure:**
- **Powerloops** and **Matty Flips** capture your sustained mid-range pitch — how you hold arcs through loops and inverted maneuvers
- **Flicks and Snaps** capture your full-deflection speed — how aggressively you commit to juicy flicks and snap rolls
- **Orbits and Trippy Spins** capture your multi-axis coordination — how you hold sustained partial deflections on yaw + roll simultaneously

**What the algorithm targets:**
- **Low center sensitivity** (50-150 deg/s) — freestyle pilots need smooth mid-range for arcs and sustained holds. Low center sens means the transition through mid-stick feels buttery, not jumpy.
- **Moderate max rate** (400-600 deg/s) — enough authority for committed flicks and snaps, but not so high that tricks become uncontrollable
- **Moderate-to-high expo** (0.4-0.8) — bridges the gap between smooth center and snappy edges. The expo curve keeps arcs feeling smooth while still allowing committed full-stick snaps to feel sharp.

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
- **Very low center sensitivity** (50-120 deg/s) — cinematic pilots live in the 0-20% deflection range. Low center sensitivity means tiny stick movements produce gentle, filmable motion.
- **Low max rate** (300-500 deg/s) — cinematic flying never uses full deflection. Lower max rates mean the entire stick range produces controllable, smooth output.
- **Moderate expo** (0.4-0.7) — smooths the transition from center to mid-range without making near-center feel dead

**Typical rate curve shape:** Nearly flat near center (ultra-precise micro-corrections), gentle consistent slope through mid-range (smooth transitions for reveals and orbits).

**Multiplier guidance:** Start at 1.0x. Cinematic rates should feel slow and controllable. If anything, you may want to reduce multipliers below 1.0x.

---

### Mixed profile

**Goal:** A balanced rate profile that works across racing, freestyle, and cinematic flying.

**What the exercises measure:** A combination of exercises from all three styles — hover precision, smooth turns, snaps, yaw work, proximity flying, and free combo.

**What the algorithm targets:** Moderate values across all parameters, balanced between precision and authority. Good for pilots who fly multiple styles in a single session or haven't committed to one style yet.

**Multiplier guidance:** Adjust per-axis based on which style you lean toward. Bump roll if you want more freestyle snap, reduce center sensitivity if you want more cinematic smoothness.

## Rate convergence — how your rates evolve through calibration

RateFinder doesn't just give you a one-shot recommendation. Each refinement pass brings your rates closer to your natural flying style. Below is real session data showing how rates converge from stock Betaflight defaults through calibration and multiple free fly refinement passes.

### Freestyle convergence example

Known rates anchor: **Betaflight defaults** (RC Rate 1.0, Super Rate 0.70, Expo 0) = Center Sensitivity 200, Max Rate 667, Expo 0.00. The algorithm computes all values relative to this baseline.

All freestyle sessions ran at 1.0x — the algorithm's base recommendation landed in a flyable range without pilot override. Compare this to the racing profile which required 1.2x roll after FF #3.

| Stage | Mult | Roll CS | Roll MR | Roll Expo | Pitch CS | Pitch MR | Pitch Expo | Yaw CS | Yaw MR | Yaw Expo |
|-------|------|---------|---------|-----------|----------|----------|------------|--------|--------|----------|
| BF Defaults | 1.0x | 200 | 667 | 0.00 | 200 | 667 | 0.00 | 200 | 667 | 0.00 |
| After Calibration | 1.0x | 132 | 430 | 0.72 | 123 | 434 | 0.76 | 175 | 398 | 0.49 |
| Free Fly #1 (91s) | 1.0x | 92 | 444 | 0.64 | 97 | 446 | 0.72 | 169 | 404 | 0.46 |
| Free Fly #2 (81s) | 1.0x | 53 | 444 | 0.55 | 103 | 446 | 0.76 | 146 | 411 | 0.53 |
| Free Fly #3 (72s) | 1.0x | 62 | 465 | 0.66 | 122 | 460 | 0.69 | 147 | 418 | 0.64 |
| Free Fly #4 (76s) | 1.0x | 62 | 458 | 0.64 | 128 | 460 | 0.66 | 151 | 417 | 0.51 |

**What happened:**

1. **Calibration** immediately dropped max rate from 667 to ~430 and introduced expo (0.49-0.76). The BF defaults were way too aggressive for this pilot's freestyle style.
2. **Free Fly #1** dropped roll center sensitivity from 131 to 92. The pilot's natural arcs and orbits showed they needed a smoother center feel than the exercises alone captured.
3. **Free Fly #2** pushed roll center even lower (53) as more mid-range data came in. Max rates held steady — the pilot's snap authority was already well-calibrated.
4. **Free Fly #3 and #4** saw roll center stabilize around 62 and max rates settle around 458-460. The rates converged.

**The final freestyle signature:** Low center sensitivity (~60 roll, ~128 pitch), moderate max rate (~458), moderate expo (~0.65). This is the "smooth center, snappy edges" profile — buttery mid-range arcs with full authority when committing to flicks.

Notice that **yaw was the most stable axis** throughout — it barely moved from the calibration values. Yaw behavior is consistent regardless of which freestyle tricks you do, which is why yaw rates tend to converge fastest.

### Racing convergence example

Known rates anchor: **Betaflight defaults** (RC Rate 1.0, Super Rate 0.70, Expo 0) = Center Sensitivity 200, Max Rate 667, Expo 0.00. The algorithm computes all values relative to this baseline.

The **Mult** column shows the multiplier applied on top of the algorithm's base recommendation. At 1.0x you are flying the pure algorithm output. Bumping to 1.2x scales max rate and center sensitivity up while expo scales down proportionally.

| Stage | Mult | Roll CS | Roll MR | Roll Expo | Pitch CS | Pitch MR | Pitch Expo | Yaw CS | Yaw MR | Yaw Expo |
|-------|------|---------|---------|-----------|----------|----------|------------|--------|--------|----------|
| BF Defaults | 1.0x | 200 | 667 | 0.00 | 200 | 667 | 0.00 | 200 | 667 | 0.00 |
| After Calibration | 1.0x | 50 | 503 | 0.53 | 125 | 445 | 0.69 | 172 | 408 | 0.22 |
| Free Fly #1 (95s) | 1.0x | 50 | 553 | 0.37 | 75 | 450 | 0.78 | 156 | 416 | 0.31 |
| Free Fly #2 (84s) | 1.0x | 50 | 540 | 0.40 | 57 | 450 | 0.66 | 158 | 409 | 0.31 |
| Free Fly #3 (76s) | 1.0x | 50 | 540 | 0.34 | 63 | 444 | 0.67 | 157 | 409 | 0.30 |
| Pilot applied 1.2x roll | 1.2x | 60 | 648 | 0.28 | 63 | 444 | 0.67 | 157 | 409 | 0.30 |
| Free Fly #4 (87s) | 1.2x | 60 | 663 | 0.38 | 58 | 450 | 0.66 | 157 | 416 | 0.35 |
| Free Fly #5 (77s) | 1.2x | 60 | 679 | 0.33 | 59 | 450 | 0.67 | 158 | 422 | 0.33 |
| Free Fly #6 (71s) | 1.2x | 60 | 679 | 0.37 | 58 | 463 | 0.66 | 159 | 423 | 0.32 |
| Free Fly #7 (72s) | 1.2x | 60 | 695 | 0.35 | 57 | 463 | 0.65 | 160 | 422 | 0.30 |

**What happened:**

1. **Calibration** immediately dropped roll center sensitivity to 50 — the Hard 180s and Splits exercises showed this pilot commits to full-deflection snaps with extreme authority. Max rate dropped from 667 to 503, and expo appeared (0.22-0.69) to shape the curve.
2. **Free Fly #1** pushed roll max rate up (503 to 553) as real racing laps demanded more rotation authority than the exercises alone captured. Pitch center sensitivity dropped dramatically (125 to 75) — real gate tracking requires tighter center precision.
3. **Free Fly #2** drove pitch center even lower (75 to 57) as more tracking data accumulated. The pilot's natural gate-following instincts need very low center sensitivity for precise line corrections.
4. **After FF #3** the pilot applied a 1.2x roll multiplier — at 1.0x the base roll max rate (540) felt too slow for committed racing snaps. The "Pilot applied 1.2x roll" row shows the rates immediately after the slider moved, before any new free fly data. This is a multiplier adjustment, not an algorithm update.
5. **Free Fly #4 through #7** continued refining the base recommendation with 1.2x active. The algorithm's base roll max rate kept climbing (553 to 579) underneath the multiplier, while pitch stabilized around 57-59 and yaw held remarkably stable (~157 CS, ~422 MR).

**The final racing signature:** Very low center sensitivity (60 roll at 1.2x, 57 pitch), high max rate (695 roll at 1.2x, 463 pitch), moderate expo (0.35 roll, 0.65 pitch). This is the "precision center, authority at the edges" profile — tight line corrections at center stick with committed snap authority at full deflection.

**Key differences from freestyle:**
- Roll center sensitivity hit the **floor (50)** in racing but stabilized at 62 in freestyle — racing pilots use more extreme full-deflection, which pushes center lower
- Roll max rate **kept climbing** through racing free fly passes (503 to 579) while freestyle stabilized early (430 to 458) — racing demands more rotation authority
- Pitch expo was **lower in racing** (0.65) than freestyle (0.66) despite similar center sensitivity — the flatter mid-range gives racing pilots more linear feel through turns
- Yaw was the **most stable axis in both styles** — yaw behavior is consistent regardless of flying style

### Cinematic convergence example

Known rates anchor: **Betaflight defaults** (RC Rate 1.0, Super Rate 0.70, Expo 0) = Center Sensitivity 200, Max Rate 667, Expo 0.00. The algorithm computes all values relative to this baseline.

All cinematic sessions ran at 1.0x — the algorithm's base recommendation produced flyable cinematic rates without pilot override.

| Stage | Mult | Roll CS | Roll MR | Roll Expo | Pitch CS | Pitch MR | Pitch Expo | Yaw CS | Yaw MR | Yaw Expo |
|-------|------|---------|---------|-----------|----------|----------|------------|--------|--------|----------|
| BF Defaults | 1.0x | 200 | 667 | 0.00 | 200 | 667 | 0.00 | 200 | 667 | 0.00 |
| After Calibration | 1.0x | 171 | 367 | 0.20 | 174 | 370 | 0.28 | 170 | 362 | 0.05 |
| Free Fly #1 (76s) | 1.0x | 164 | 368 | 0.24 | 175 | 382 | 0.12 | 172 | 366 | 0.07 |
| Free Fly #2 (102s) | 1.0x | 159 | 368 | 0.43 | 167 | 382 | 0.20 | 172 | 366 | 0.20 |

**What happened:**

1. **Calibration** immediately dropped max rate from 667 to ~367 — less than half the BF defaults. Center sensitivity stayed high (~171) because cinematic flying uses tiny corrections, not big deflections. Expo was very low (0.05-0.28) — cinematic curves are nearly linear since you never leave the center stick range.
2. **Free Fly #1** barely changed the rates — center sensitivity dipped slightly (171 to 164 roll) and max rates held almost constant. The calibration exercises captured the cinematic stick patterns accurately on the first pass.
3. **Free Fly #2** saw roll expo increase (0.24 to 0.43) as more mid-range data from proximity passes and orbits came in. Pitch center dropped slightly (175 to 167). Overall the rates were already converged after calibration — cinematic is the most stable profile.

**The cinematic signature:** High center sensitivity (~160-175), low max rate (~366-382), low expo (0.05-0.43). Every axis is nearly identical — cinematic pilots use all axes equally at low deflection, unlike racing (roll-dominant) or freestyle (pitch-dominant mid-range).

**Key differences from racing and freestyle:**
- Center sensitivity is **3x higher** than racing (160 vs 50) — cinematic pilots need immediate response to tiny corrections, not big deflections
- Max rate is **40% lower** than freestyle (368 vs 458) — cinematic never uses full deflection
- All three axes converge to **nearly identical values** — cinematic flying uses all axes equally at low deflection
- Converged in **2 free fly passes** vs 4+ for freestyle and 7+ for racing — cinematic stick patterns are the most consistent

### Reading the convergence table

Two things can change your rates between sessions:

**Algorithm updates** (Free Fly refinement) — the base recommendation changes based on new stick data. These appear as new Free Fly rows in the table. The change is driven by your flying patterns, not your input.

**Multiplier adjustments** (pilot override) — you moved a slider. The base recommendation hasn't changed — only your scaling of it has.

This distinction matters: if the algorithm keeps pushing a value in one direction across multiple free fly passes, that's a signal your rates genuinely need to change. If you keep overriding with the multiplier in the same direction, consider whether the algorithm's base recommendation is actually correct for you.

### Exporting your convergence data

Use **Export JSON** on the Results screen to save your full session data including all metrics. Each saved profile captures the complete analysis and the final rate recommendation. Save after each refinement pass to track your progression over time.

## Understanding your results

### The rate curve chart

Shows rotation speed (deg/s) vs stick position for Roll, Pitch, and Yaw. The shape of this curve varies by flying style — racing curves are steep, freestyle curves are progressive, and cinematic curves are gentle.

**Rate curves by flying style (roll axis comparison):**

![Rate curves by flying style](docs/images/rate_curves_by_style.png)

The dashed line is the BF default rate curve. Notice how each style reshapes it differently — racing stays low at center and ramps steeply, freestyle creates a progressive S-curve, and cinematic is nearly linear at lower output.

**Per-profile all axes:**

| Racing | Freestyle | Cinematic |
|--------|-----------|-----------|
| ![Racing](docs/images/rate_curve_racing_1.2x_roll.png) | ![Freestyle](docs/images/rate_curve_freestyle.png) | ![Cinematic](docs/images/rate_curve_cinematic.png) |

**Convergence — how the rate curve evolves from BF defaults to final rates:**

![Rate convergence comparison](docs/images/rate_convergence_comparison.png)

Each line shows the roll axis rate curve at a different stage. The dashed line is BF defaults, and curves progressively shift toward the final rates through calibration and free fly passes.

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

**Example:** A racer wants "snappier center + linear edges":
- Set Center Sensitivity to 0.7x (snappier center response)
- Set Expo to 1.5x (flatten the curve, reduce expo)
- Leave Max Rate at 1.0x (keep snap authority unchanged)
- Then use Roll/Pitch/Yaw multipliers to dial in absolute speed per axis

### Throttle settings

RateFinder recommends Throttle Mid (your hover point) and Throttle Expo (softness around hover), computed from your actual throttle patterns during the exercises. Both values are **editable on the Rates tab** via slider + numeric input — adjust them before copying CLI output. Changes are included in the exported CLI and saved with your profile.

## Detailed workflows

### Racing workflow (VelociDrone)

This is a tested, step-by-step workflow. Total time: ~45 minutes for calibration + 6 free fly passes.

**Setup:**
1. Open VelociDrone
2. Load the **WT Racing RateFinder** map (or any map with gates for exercises 2-5)
3. Set your VelociDrone rates to **Betaflight defaults**: RC Rate 1.0, Super Rate 0.70, Expo 0
4. Open RateFinder alongside VelociDrone
5. Click **"Find My Rates"**, fill in your profile, complete axis calibration

**Calibration (exercises 1-6):**
6. **Exercise 1 (Center Precision):** Lower your camera tilt to ~25 degrees for hover stability. Hover and make small corrections.
7. **Exercise 2-5:** Raise camera tilt back to your racing angle (typically 45-60 degrees). Execute Hard 180s, Splits, Corkscrews, and Ladders on the practice map.
8. **Exercise 6 (Combo):** Load your **favorite race track** — one you know well. Fly 3 laps at race pace using the BF default rates.
9. Review results on the Rates tab

**Free Fly refinement (6 passes):**
10. **Copy your new rates** from RateFinder into VelociDrone (Copy Actual CLI or Copy BF CLI)
11. Click **"Refine in Free Fly"** in RateFinder. If you assigned a trigger switch, flip it to start recording and flip again to stop — no need to alt-tab back to RateFinder.
12. Fly 3 laps on your favorite track. Don't chase lap times — focus on **flow and smoothness**. The algorithm needs to see your natural stick patterns, not your fastest possible inputs.
13. Stop the free fly session. Review the updated rates.
14. **Repeat steps 10-13** two more times (3 free fly passes total, 9 laps). Each time, copy the updated rates into VelociDrone before flying.
15. After 3 passes, check if any axis still feels slow. If so, **move the multiplier slider** — typically roll to 1.2x for racing.
16. **Repeat steps 10-13** three more times with the multiplier applied (3 more passes, 9 more laps). Copy updated rates into VelociDrone each time.
17. After 6 total free fly passes (18 laps), evaluate your rates.

**How to know you're done:**
- Your **lap times should be decreasing** across the session — this is the most objective measure
- You should feel less like you're **fighting the quad** and more like you're **flowing through gates**
- The Diagnostics tab should show **jerk decreasing** between calibration and free fly (green arrows)
- The rates should be **stabilizing** — if the algorithm keeps changing values significantly between passes, keep going

**Save and iterate:**
18. Click **"Save Profile"** with your final multiplier settings
19. Next session: use **"Refine My Rates"** to continue from where you left off
20. Over 3-5 sessions your rates will converge to your ideal profile

### Freestyle workflow (VelociDrone)

**Setup:**
1. Open VelociDrone
2. Load the **WT Freestyle RateFinder** map
3. Set your VelociDrone rates to **Betaflight defaults**: RC Rate 1.0, Super Rate 0.70, Expo 0
4. Open RateFinder alongside VelociDrone
5. Click **"Find My Rates"**, fill in your profile (select Freestyle), complete axis calibration

**Calibration (exercises 1-6):**
6. **Exercise 1 (Hover Precision):** Lower camera tilt if needed for hover stability. Hover and make small corrections.
7. **Exercise 2-5:** Use your normal freestyle camera angle. Execute Powerloops, Matty Flips, Flicks/Snaps, and Orbits around structures on the map.
8. **Exercise 6 (Flow Combo):** Chain tricks naturally. Fly your own style — powerloops into matty flips, stall rewinds, whatever flows.
9. Review results on the Rates tab

**Free Fly refinement (3-4 passes):**
10. **Copy your new rates** into VelociDrone
11. Click **"Refine in Free Fly"** in RateFinder
12. Fly for 60-90 seconds doing your normal freestyle flow. Don't try to be aggressive — fly naturally.
13. Stop, review, copy updated rates into VelociDrone. Repeat 2-3 more times.
14. Freestyle rates typically converge at 1.0x without needing multiplier adjustments — if arcs feel smooth and flicks feel snappy, you're done.

**How to know you're done:**
- Mid-range arcs feel **buttery**, not jerky
- Full-stick flicks feel **sharp and committed**, not sluggish
- You're not oscillating at center stick after completing tricks
- The Diagnostics tab shows **correction frequency decreasing** between calibration and free fly

### Cinematic workflow (VelociDrone)

**Setup:**
1. Open VelociDrone
2. Load the **Freestyle Map — Drift Track**
3. Click the **car icon in the bottom right** of VelociDrone to configure traffic. Set it to **3 cars** on the map — you will need them for the Subject Tracking exercise (Exercise 4).
4. Set your VelociDrone rates to **Betaflight defaults**: RC Rate 1.0, Super Rate 0.70, Expo 0
5. Open RateFinder alongside VelociDrone
6. Click **"Find My Rates"**, fill in your profile (select Cinematic), complete axis calibration

**Calibration (exercises 1-6):**

Follow the exercise prompts explicitly — the parked car and tree line on the Drift Track are your reference objects for hover, orbit, and dive exercises.

7. **Exercise 1 (Extended Hover, 45s):** Use the parked car as your point of interest. Set camera tilt to 25 degrees. Frame the car and hold position — zero visible camera movement for the full 45 seconds.
8. **Exercise 2 (Orbit POI, 45s):** Orbit the car in the parking lot. One direction first, then reverse. Constant radius, camera locked on the car the entire time.
9. **Exercise 3 (Dive and Pull-Out):** Dive toward the tree line at 30-45 degrees. Smooth pull-out to level before reaching the trees. Repeat multiple times — consistent smooth arcs, no jerky inputs.
10. **Exercise 4 (Subject Tracking, 45s):** Wait for cars to come into view on the track, then click Go and follow them. Smooth continuous yaw adjustments to keep the car framed. Let the subject lead — you follow.
11. **Exercise 5 (Indoor Flow):** Navigate the bridge and signs on the Drift Track as if doing a real estate shoot. Slow, deliberate movement through tight spaces. Treat every structural element like a room — glide through gaps, reveal architecture, keep all axes at low deflection. No snaps.
12. **Exercise 6 (Cinematic Combo, 45s):** Chain a reveal shot over an obstacle, orbit the parking lot car, proximity pass along the track, and pull-back reveal. Fly the Drift Track at cinematic pace.
13. Review results on the Rates tab

**Free Fly refinement (2-3 passes):**
14. **Copy your new rates** into VelociDrone
15. Click **"Refine in Free Fly"** in RateFinder
16. Fly the Drift Track cinematically for 60-90 seconds. Orbits, tracking shots, reveals, proximity passes. Fly as if you're delivering footage to a client.
17. Stop, review, copy updated rates into VelociDrone. Repeat 1-2 more times.
18. Cinematic rates converge fast — typically 2 passes is enough.

**How to know you're done:**
- Camera movement feels **invisible** — no jerky corrections visible in the footage
- Orbits hold a **consistent radius** without drift
- Reveal shots are **smooth and well-paced**
- You don't feel like you're **fighting the quad at center stick**
- The Diagnostics tab shows **very low jerk** across all axes

### General workflow (any style)

If you don't want to follow the detailed steps above:

1. Run Path A with BF defaults
2. Complete all 6 exercises for your flying style
3. Copy rates into your simulator
4. Click "Refine in Free Fly", fly 3 laps or 60+ seconds, stop
5. Copy updated rates, repeat 3-6 times
6. Adjust multiplier if any axis feels slow
7. Save your profile when rates feel right

## How RateFinder reads your flying

RateFinder doesn't care which tricks you do — it analyzes the **stick distribution patterns** underneath every maneuver. These patterns are consistent per pilot regardless of what they're flying.

### What your stick data reveals

| Metric | What it measures | What it means for rates |
|--------|-----------------|----------------------|
| **Center Precision Radius (CPR)** | How far from center your stick drifts during hover/corrections | Higher CPR = you naturally use more stick travel = lower center sensitivity needed |
| **Comfortable Max Velocity (CMV)** | How fast you move the stick during snaps and flips (95th percentile) | Higher CMV = you snap harder = higher max rate appropriate |
| **Mid-range Distribution Index (MDI)** | % of active stick time spent between 30-70% deflection | Higher MDI = more time in mid-range = more expo needed to smooth the transition |
| **Correction Frequency** | How often you make small corrective inputs (oscillations/sec) | High correction frequency = fighting your rates — they don't match your instincts |
| **Mean Jerk** | Rate of change of stick velocity (how abrupt your inputs are) | High jerk = compensating for wrong rates. Smooth pilots on good rates have low jerk |
| **Full Deflection Hold** | Average time spent at full stick per snap | Long holds = max rate may be too low (holding full stick waiting for rotation to complete) |

### How the algorithm uses your known rates as an anchor

RateFinder doesn't generate rates from scratch — it starts from your **known rates** (the rates you entered on the Known Rates screen) and adjusts them based on your measured stick patterns. This is why entering accurate known rates matters.

The three core metrics adjust your known rates as follows:

**Center Sensitivity** — Based on your Center Precision Radius (CPR). If you make wide corrections during hover, center sensitivity drops. If your corrections are tiny and precise, it stays close to your known value.

**Max Rate** — Based on your Comfortable Max Velocity (CMV). If you snap the sticks hard and fast, max rate increases above your known value. Slow, deliberate movements bring it down.

**Expo** — Based on your Mid-range Distribution Index (MDI). If you spend a lot of time in the mid-range (30-70% deflection), expo increases to smooth that zone. If you mostly use center and full stick with little in between, expo decreases for a more linear feel.

If you skip the Known Rates screen, RateFinder uses Betaflight defaults as the anchor (Center Sensitivity 200 deg/s, Max Rate 667 deg/s, Expo 0.0).

### Why these patterns work across all flying styles

- A **racing pilot** doing gate laps will show high CPR (wide corrections at speed), high CMV (fast snaps), and low MDI (center or full stick, not much mid-range) — resulting in low center sensitivity, high max rate, and moderate expo
- A **freestyle pilot** doing powerloops and matty flips will show moderate CPR, moderate CMV, and high MDI (lots of sustained mid-stick arcs) — resulting in moderate center sensitivity, moderate max rate, and high expo
- A **cinematic pilot** doing orbits and tracking shots will show very low CPR (tiny corrections), low CMV (no snaps), and low MDI (everything near center) — resulting in high center sensitivity, low max rate, and low expo

The algorithm uses these signatures — not the specific maneuvers — to calculate your ideal rate curve relative to your starting baseline.

### Rate fit indicators

After a Free Fly session, the Diagnostics tab shows **Rate Fit Indicators** — before/after comparisons of jerk and correction frequency between calibration and free fly:

- **Jerk decreased** (green arrow down) = your rates are working. You're flowing, not fighting.
- **Jerk increased** (orange arrow up) = rates may need adjustment. You're compensating.
- **Correction frequency decreased** = fewer micro-corrections needed. Rates match your instincts.
- **Correction frequency increased** = more corrections than during calibration. Something's off.

These indicators work for all flying styles — a freestyle pilot fighting their expo curve shows the same elevated jerk pattern as a racing pilot with the wrong center sensitivity.

## Tips

- **Always fly at full pace during exercises** — conservative flying produces conservative rates
- **Commit to full stick on snap exercises** — the algorithm needs to see your true max deflection speed
- If center stick feels **twitchy**, lower center sensitivity (not expo)
- If full stick feels **sluggish**, increase max rate (not the multiplier)
- **Yaw rates are usually fine at 1.0x** — most pilots only need to adjust roll and pitch
- The **Refine tab** lets you manually edit any value and save iterations with notes
- The **Diagnostics tab** shows all the raw analysis data, rate fit indicators, correction frequency trending, session suggestions log, and per-exercise breakdowns

## Exporting to your simulator or flight controller

**Copy BF CLI** — paste directly into Betaflight Configurator CLI tab:

```
set rates_type = BETAFLIGHT
set roll_rc_rate = 0.89
set roll_super_rate = 0.72
set roll_expo = 0.15
...
save
```

**Copy Actual CLI** — paste into VelociDrone or Betaflight 4.3+ (Actual rates mode):

```
set rates_type = ACTUAL
set roll_rc_rate = 18
set roll_srate = 80
set roll_expo = 45
...
save
```

**Save Profile** — stores your rates, multipliers, and all session data so you can reload them next time without re-running calibration.

**Export JSON** — copies the full recommendation as JSON for sharing or backup.

## The Results screen tabs

| Tab | What's there |
|-----|-------------|
| **Rates** | Rate curve chart, values table, multiplier sliders, throttle mid/expo sliders, copy/export buttons |
| **Compare** | Side-by-side rate curve comparison — pick any two sources (current recommendation, any free fly pass, known rates, cal aggregate) and see the curves overlaid with per-parameter delta cards |
| **Diagnostics** | Session quality rubric, correction frequency table, per-exercise breakdown, per-axis analysis, session suggestions log |
| **Profiles** | Current profile, session history, all saved profiles on this machine |
| **Refine** | Manual rate editor with iteration history — edit values directly and save versions with notes |

### Compare tab

The Compare tab lets you visually compare rate curves between any two sources side by side.

**Sources you can compare:**
- **Current recommendation** — your active rates including all multiplier and curve shape adjustments
- **FF Pass 1, 2, 3...** — the recommendation snapshot from each free fly pass
- **Known rates (baseline)** — the rates you entered manually on the Known Rates screen
- **Cal aggregate** — estimated rates from calibration exercise data alone

**How to use it:**
1. Select an axis mode: Roll, Pitch, Yaw, or All 3 (overlays all axes on both charts)
2. Card A defaults to your current recommendation, Card B defaults to your known rates baseline (or the first free fly pass if no manual rates were entered)
3. Each chart shows a solid line for its own source and a dashed overlay of the other source for direct visual comparison
4. The delta section below shows parameter-by-parameter comparison: center sensitivity, max rate, expo (actual), RC rate, super rate, expo (BF) — with percentage change and color coding

**Reading the delta cards:**
- Green = the direction most pilots want (lower center sensitivity, higher expo)
- Red = the opposite direction
- Gray = neutral (max rate, RC rate, super rate — direction depends on your goals)

A throttle comparison row below the graphs always shows Throttle Mid and Throttle Expo for both sources.

### Diagnostics tab

**Correction Frequency table** — A unified table showing correction frequency (direction reversals per second) across your entire session:
- **Cal Aggregate** row at the top — your baseline correction frequency from calibration
- **Per-exercise rows** — breakdown by calibration exercise (Center Precision, Hard 180s, etc.)
- **Free Fly Pass rows** — one per free fly pass, with two delta columns:
  - **Delta vs Cal** — percentage change from the calibration baseline (green = improving, red = worsening)
  - **Delta vs Prev** — percentage change from the immediately preceding free fly pass

Correction frequency trending downward across passes is the primary signal that your rates are matching your instincts. If it trends upward, the rates may need adjustment.

**Session Suggestions Log** — Every suggestion shown during free fly recording is logged with:
- Pass label (e.g., "Free Fly Pass 2")
- Timestamp
- The metric that triggered it and its value at that moment
- An expandable metrics snapshot showing all analysis values at the moment the suggestion fired

Entries accumulate across all passes and are grouped by pass with independent collapse controls. The log is saved with your profile.

## Profile storage and backup

Your pilot profiles and session data are stored locally on your computer and are **separate from the app installation** — profiles survive uninstalls and reinstalls. The only way to lose them is manually deleting the RateFinder data folder.

### Backing up profiles

During beta testing, the app may be updated frequently. Your profiles will persist automatically, but for extra safety:

1. Use **Export JSON** on the Results screen to save a full backup of your profile, session data, and recommended rates
2. After updating, use **Load Profile** or reimport the JSON to restore everything
