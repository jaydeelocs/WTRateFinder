<p align="center">
  <img src="docs/wildtype-logo.png" alt="WILDTYPE" width="180">
</p>

<h1 align="center">RateFinder</h1>

<p align="center">
  <strong>Stop guessing your rates. RateFinder watches how you actually fly and builds a rate curve that matches your hands.</strong>
</p>

<p align="center">
  <a href="https://github.com/jaydeelocs/RateFinder/releases/latest">
    <img src="https://img.shields.io/github/v/release/jaydeelocs/RateFinder?label=download&style=for-the-badge&color=FF6B2B" alt="Download">
  </a>
  &nbsp;
  <img src="https://img.shields.io/badge/Windows-10%2F11-0078D6?style=for-the-badge&logo=windows" alt="Windows">
  &nbsp;
  <img src="https://img.shields.io/badge/License-Freeware-green?style=for-the-badge" alt="Freeware">
</p>

---

## Download

**[→ Download the latest installer (.msi)](https://github.com/jaydeelocs/RateFinder/releases/latest)**

Windows 10/11 only. No account required. 

> **Official download sources only:**
> This repository and [wildtypedrones.com/ratefinder](https://wildtypedrones.com/ratefinder)
> are the only authorized distribution points for RateFinder.

---

## What is RateFinder?

Every FPV pilot hits the same wall. You copy rates from a YouTube video, spend three sessions tweaking expo, and the quad never quite feels like yours. Every rate calculator starts from the curve and asks you to fill in numbers. None of them watch your hands.

RateFinder does.

1. **Connect your radio** via USB in joystick mode
2. **Fly 6 calibration exercises** in VelociDrone — tailored to your style (racing, freestyle, or cinematic)
3. **Get personalized rates** anchored to your actual stick patterns, not someone else's preset
4. **Refine in free fly** — each pass tightens the recommendation closer to your natural feel

Racing pilots converge in ~18 laps. Freestyle in 3–4 passes. Cinematic in 2.

---

## What makes it different

- Measures three proprietary metrics from your stick data: **CPR** (center precision), **CMV** (max snap velocity), **MDI** (mid-range distribution)
- Style-specific exercises — racing pilots do gate runs and 180s, freestyle pilots do powerloops and matty flips
- Anchored to your known rates — adjusts from where you are, not from zero
- Detects whether you're fighting your rates via jerk and correction frequency analysis
- Multi-session refinement — save, close, reopen, and continue refining from where you left off
- Outputs both Betaflight CLI and Actual rates format — one click to paste

---

## Getting started

See **[GETTING_STARTED.md](GETTING_STARTED.md)** for:
- Full setup instructions
- Exercise guides for Racing, Freestyle, and Cinematic profiles
- Step-by-step workflows with real convergence data
- How the algorithm works

---

## Requirements

- Windows 10 or 11
- USB radio or simulator dongle in **joystick mode**
  - EdgeTX: System → Hardware → USB Mode → Joystick
- VelociDrone (free trial available — required for calibration exercises)
- Betaflight Configurator (for pasting rates to your quad)

---

## Community & support

- **Discord:** [Join the WILDTYPE server](https://discord.gg/9KjPTCECXN) — rate tuning help, map downloads, community data
- **YouTube:** [@wildtypefpv](https://www.youtube.com/@joshualocsin) — demo video, tutorials
- **Instagram:** [@wildtypefpv](https://instagram.com/wildtypefpv)
- **Facebook:** [@wildtypefpv](https://www.facebook.com/wildtypefpv)
- **Website:** [wildtypedrones.com](https://wildtypedrones.com)

---

## Get Dialed — expert tuning sessions

Want hands-on help dialing in your rates? Book a **Get Dialed** session — a 1-on-1 remote tuning session with Josh (3x MLDR Grand Prix Champion, Top 50 globally).

**$75–150 per session · Team packages available**

→ [wildtypedrones.com/getdialed](https://wildtypedrones.com/getdialed)

---

## Built by

**Joshua Locsin — WILDTYPE Drones**
3x MLDR Grand Prix Champion · Top 50 FPV pilot globally · 54+ podiums · MultiGP ranked · FAA Part 107

Built because no existing tool accounted for how individual pilots actually fly.

---

## License

RateFinder is **free to use** but is **not open source.**

The compiled installer is distributed as freeware. The source code, algorithm, and methodology are proprietary and remain the exclusive intellectual property of Joshua Locsin / WILDTYPE Drones LLC.

See [LICENSE.txt](LICENSE.txt) for full terms.

> Redistribution, reverse engineering, and commercial use without written permission are prohibited.
> The only authorized download sources are this repository and wildtypedrones.com/ratefinder.

---

## Version history

### v1.0.0 — March 2026
- Initial public release
- Racing, Freestyle, and Cinematic profiles
- 6 style-specific calibration exercises per profile
- Free fly refinement with decay-weighted merge against calibration anchor
- Multi-session profile save/load with persistent calibration baseline
- Betaflight CLI and Actual rates export
- Per-axis multipliers and Global Curve Shape controls
- Diagnostics tab with session quality rubric and rate fit indicators
- Windows MSI installer
