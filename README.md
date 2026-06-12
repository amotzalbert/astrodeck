# AstroDeck — Night Sky Station

**Live app: [amotzalbert.github.io/astrodeck](https://amotzalbert.github.io/astrodeck/)**

A single-file, real-time 3D night-sky app. No build, no install, no account — one HTML file, Three.js, and real astronomy. Works on desktop and mobile.

---

## Feature Index

### 🪐 Solar System (3D orrery)
- All 8 planets + the Moon on **real Keplerian orbits** (Schlyter algorithm) — today's view is today's actual configuration
- **Realistic textures** for the Sun (rotating, ~25-day period), all planets, the Moon, and Saturn's rings
- **12 major moons with real ephemeris** — Phobos, Deimos, Io, Europa, Ganymede, Callisto, Enceladus, Rhea, Titan, Titania, Oberon, Triton — Kepler-propagated from JPL Horizons osculating elements (true directions and phases; Triton correctly retrograde, Uranus' moons correctly sideways)
- **ISS in real time** — low-poly 3D model with sun-tracking solar arrays, riding its true 51.6°-inclined orbit, SGP4-propagated from today's TLE (verified against live tracking to within seconds of motion)
- **Space telescopes layer** — Hubble, Chandra, XMM-Newton and JWST as 3D models with their real orbits: LEO circle, wild multi-day X-ray ellipses, and JWST flying its real halo orbit at Sun–Earth L2 (baked JPL Horizons ephemeris, 2026–2030)
- **Known-satellites layer** — the ~150 brightest catalogued objects (Hubble, Tiangong, rocket bodies) live around Earth from fresh Celestrak TLEs, toggleable
- **Earth with your home marked** — red dot at your saved lat/lon on a globe oriented by true sidereal rotation + 23.4° axial tilt, so day/night vs the Sun is real
- **Click any body** → camera glides over and *rides along* as it orbits; info card with live distances, physical facts; selected orbit highlights in the body's color
- **🧲 Mag fields toggle** — dipole field lines for the six planets with global fields, at their real tilts (Earth 11.5°, Uranus 59°, Neptune 47°); Venus & Mars correctly show none
- **🌀 Gravity grid toggle** — a spacetime rubber-sheet under the ecliptic: the Sun digs a deep funnel, every planet dents it, and the wells ride along as the planets orbit
- Sun **light dimmer** (0–200%), orbit-path & label toggles
- **✦ Light ping** — fire a pulse from the Sun at real light-speed; planets light up with their light-times as it passes (8 min to Earth, 4 hours to Neptune)
- **True scale toggle** — morph to honest sizes and distances and watch the solar system vanish into the void
- **Halley's Comet** on its real retrograde orbit, ion tail inside 4 AU — time-machine to July 2061 for the show
- Time machine: pause, ±speeds from −1 day/s to +1 week/s, jump to any date

### 🌌 Sky View (planetarium)
- The sky **exactly as seen from your location** — geolocation or manual entry, saved locally, with a default **facing direction** (N/NE/…/NW)
- ~3,500 real stars (d3-celestial catalog, color-coded by temperature), all 88 constellations with lines & names, named bright stars
- **The Milky Way** arcs across the sky in its true position — procedurally generated along the real galactic plane, brightest toward the Sagittarius core, Great Rift included; fades out first in twilight (toggleable)
- Sun, Moon and planets plotted live; **Moon accurate to ~1 arcminute** (full perturbation series + topocentric parallax, verified vs JPL Horizons)
- **Moon rendered with its real phase** — textured sphere lit from the Sun's true sky direction: crescent, terminator and bright-limb orientation are physical, with faint earthshine (illuminated fraction verified vs Horizons to 0.2%)
- **ISS as a live sky object** — appears when above your horizon, trackable
- **✨ Tonight panel** — scans the coming night and lists each naked-eye planet + Moon (% illuminated): visible hours, peak altitude, compass direction; tap to track
- **🛰️ ISS pass alert** — a banner appears *only* on nights with a genuinely visible pass (station above 10°, sky dark, station sunlit — Earth-shadow modeled); "Show me" jumps to the pass and tracks it
- **🔭 Focus on…** dropdown with live ↑↓ altitude markers — glides to and tracks any body as the sky turns
- **Live compass** rose with heading readout (click to face north), **Reset view** button
- Atmosphere toggle (day/twilight/night sky tinting + star fading — off by default), ground & cardinal markers
- Star/constellation labels fade in daylight

### 🔭 Telescope Feeds
- **Earth from the ISS — live 4K** (Sen, 24/7 stream)
- **The Sun right now** — SDO corona (193 Å) & visible light, SOHO coronagraph — auto-refreshing public-domain imagery
- **NASA Astronomy Picture of the Day**
- Curated links: NASA+ live coverage, Virtual Telescope Project, Lowell Observatory, Mauna Kea night-sky cam, Webb/Hubble galleries

### 📱 Mobile
- **Point at sky (gyro/AR mode)** — hold your phone up; the view follows where you aim, compass-referenced (iOS & Android)
- GPS location, **pinch-to-zoom**, collapsible UI (☰ controls, ⏱ time chip) for a clean full-screen sky
- Bottom-sheet info cards with large tap targets

### 🎯 Data accuracy
- Planets: Schlyter Keplerian elements (arcminute-level)
- Moon: full perturbation series, ~0.02° vs JPL Horizons apparent position
- Planetary moons: JPL Horizons osculating elements (epoch 2026-06-11)
- ISS: daily TLE (wheretheiss.at / Celestrak) + SGP4 via satellite.js
- Time: local sidereal time, equinox-of-date frame

---

*Built with Claude Code. Star catalog: [d3-celestial](https://github.com/ofrohn/d3-celestial) (BSD). Textures: three.js examples & threex.planets. Ephemerides: NASA JPL Horizons. ISS TLE: wheretheiss.at / Celestrak.*
