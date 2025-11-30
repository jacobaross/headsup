# Heads Up! Web App

A mobile-first Progressive Web App (PWA) that replicates the "Heads Up" party game experience.

## Features

- 25 pre-loaded deck categories with 20 cards each
- Custom deck creation and management
- Tilt controls for mobile devices
- Desktop fallback controls
- Configurable timer (30/45/60/90/120 seconds)
- Audio countdown and sound effects
- Round summary with detailed results
- Offline support via service worker
- Installable as a PWA on mobile devices

## Play Now

Visit: https://[your-username].github.io/headsup

## How to Play

1. Choose a deck category
2. Hold your phone to your forehead
3. Tilt forward when you guess correctly
4. Tilt backward to skip
5. Try to get as many correct as possible before time runs out!

## Local Development

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000

## Technologies

- Vanilla JavaScript
- CSS3 with CSS Variables
- DeviceOrientation API
- Web Audio API
- Service Worker API
- Local Storage API
