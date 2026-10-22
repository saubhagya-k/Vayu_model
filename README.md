# Project VAYU · CNG/LPG + Electric Hybrid Concept

**Design portfolio of Saubhagya, SRM Institute of Science and Technology**

Project VAYU is a futuristic compact SUV concept for Suzuki: a **plug-in hybrid that runs on electricity in the city and on CNG or LPG on the highway**. Drivers get EV running costs without range anxiety. *Vayu* is Sanskrit for "air".

This repository holds an interactive portfolio page where you can explore the car as a real-time 3D model and see how its powertrain works.

> **Live site:** _add your Netlify link here_

---

## Features

- **Interactive 3D car.** Rotate, zoom and change between 5 paint colours. It's built in Three.js (WebGL) and runs in any modern browser.
- **Powertrain X-ray.** The body becomes see-through to show the battery, the twin CNG tanks, the gas-flex engine, the e-motor and the high-voltage cabling. Clickable hotspots explain each component.
- **Four animated drive modes.** EV, CNG, Hybrid and Regen each show energy flowing through the car. A light strip along the side changes colour with the active mode.
- **Driver display (HMI concept).** A live dashboard shows speed, battery, CNG level, range, cost per km and an energy-flow diagram, all synced with the 3D model.
- **Case study.** Problem, insight, solution, specs, design decisions and process.
- **Responsive.** Works on desktop and mobile.

## The idea

| | |
|---|---|
| **Problem** | Full EVs bring range anxiety, patchy charging outside cities and expensive batteries. CNG is cheap per km, but CNG cars lose boot space and performance. |
| **Insight** | Most daily trips are short and only a few are long. One car should handle both without compromise. |
| **Solution** | Electric first, with gas as a safety net. The car drives on its battery by default, and a small gas-flex engine takes over on long trips and recharges the battery on the move. |

### Drive modes

| Mode | When | Energy flow |
|---|---|---|
| **EV** | City, 0–60 km/h | Battery → e-motor → wheels |
| **CNG** | Highway cruise | Engine drives the wheels and also recharges the battery |
| **Hybrid** | Overtakes, ghat roads | Engine + e-motor together (~110 kW) |
| **Regen** | Braking, downhill | Wheels → e-motor (as generator) → battery |

### Concept specifications

| | |
|---|---|
| Powertrain | Plug-in series-parallel hybrid (CNG/LPG + electric) |
| Battery | 18 kWh LFP, under the floor |
| E-motor | 85 kW / 200 Nm, front axle |
| Engine | 1.2 L 3-cyl gas-flex (CNG or LPG), ~60 kW |
| Gas storage | 12 kg CNG in 2 slim under-floor tanks |
| EV range | ~110 km (city) |
| Combined range | ~550 km |
| Running cost | ~₹1/km on EV · ~₹2.3/km on CNG |
| Charging | 7.4 kW AC (~3 h) · 50 kW DC (~30 min to 80%) |
| Dimensions | 4.3 m L · 1.8 m W · 1.6 m H · 2.6 m wheelbase |

*These are concept targets and estimates for design exploration, not tested figures.*

## Tech stack

- **Three.js r160** for the 3D model, X-ray view and particle energy flow. It loads from the jsDelivr CDN.
- **HTML, CSS, JavaScript** in a single static file with no build step.
- **AI-assisted** ideation and coding.

## Project structure

```
vayu_portfolio/
├── README.md
└── portfolio/
    └── index.html   ← the whole site (3D model, HMI and case study)
```

## Run locally

Open `portfolio/index.html` in a browser. Some browsers block 3D module loading from local files; if the model doesn't appear, serve the folder with a local web server instead:

```bash
python3 -m http.server 8000 --directory portfolio
```

Then visit `http://localhost:8000`.

## Deploy on Netlify

1. On Netlify, go to **Add new site → Import an existing project → GitHub** and pick this repo.
2. **Branch to deploy:** `dev-branch`, or `main` if you merge it there.
3. **Build command:** leave empty.
4. **Publish directory:** `portfolio`
5. Click **Deploy**.

---

*Project VAYU is a student design concept and is not affiliated with Suzuki Motor Corporation.*
