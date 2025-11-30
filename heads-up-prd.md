# Heads Up Web App - Product Requirements

## Overview

A mobile-first web application that replicates the "Heads Up" party game experience. Players hold their phone to their forehead displaying a word or phrase, while others give clues. The player tilts the phone forward (correct) or backward (skip) to advance through cards within a timed round.

## Core Features

### Game Modes

**Solo Mode**: Practice mode where the player sees the word and self-scores, useful for memorizing categories or warming up.

**Party Mode**: Standard gameplay where the phone-holder cannot see the screen while others give clues.

### Deck Management

**Pre-loaded Decks**: Ship with several default categories (e.g., Movies, Animals, Famous People, Actions).

**Custom Decks**: Users can create their own decks via simple text input (one card per line or comma-separated). Custom decks are stored in browser local storage.

**Deck Selection**: Before starting a round, players choose which deck to play from a list showing both default and custom decks.

### Gameplay Mechanics

**Timer**: Default 60-second rounds. Configurable in settings (30, 45, 60, 90, 120 seconds).

**Card Display**: Large, readable text centered on screen. Screen orientation locks to landscape when game is active.

**Tilt Controls**:
- Tilt phone forward (screen faces down): Card marked correct, next card appears
- Tilt phone backward (screen faces up): Card skipped, next card appears
- Visual and audio feedback on each action

**Round Flow**:
1. Select deck
2. "Ready" screen with instructions (hold phone to forehead)
3. 3-2-1 countdown with voice audio
4. Cards cycle based on tilt input until timer expires
5. End-of-round summary shows: correct count, skipped count, list of cards with results

### Audio

**Voice Countdown**: Spoken "3, 2, 1, Go!" before round starts.

**Sound Effects**:
- Correct: Positive chime/ding
- Skip: Neutral buzz/swoosh
- Timer warning: Audio cue at 10 seconds remaining
- Round end: Distinct completion sound

**Mute Option**: Toggle all audio on/off in settings.

### Settings

- Round duration (30/45/60/90/120 seconds)
- Audio on/off
- Tilt sensitivity adjustment (if needed for different devices)

## Technical Requirements

**Platform**: Progressive Web App (PWA), mobile-first design optimized for phones held in landscape orientation.

**Device Motion**: Uses DeviceOrientation API for tilt detection. Must handle permission prompts gracefully (especially iOS 13+ which requires explicit permission).

**Browser Support**: Safari (iOS), Chrome (Android) as primary targets. Desktop browsers should display a "best on mobile" notice but remain functional with on-screen buttons as fallback.

**Storage**: Local storage only for v1. Stores custom decks and settings.

**Offline Capability**: App should work offline once loaded (service worker caching).

## User Flow

```
Home Screen
    ├── Play → Deck Selection → Ready Screen → Gameplay → Round Summary → [Play Again / Home]
    ├── Create Deck → Text Input → Save → Return to Home
    ├── Manage Decks → View/Edit/Delete Custom Decks
    └── Settings → Timer Duration, Audio Toggle, Tilt Sensitivity
```

## UI/UX Notes

- Large touch targets, minimal UI during gameplay
- High contrast text for readability when phone is at arm's length
- Landscape orientation enforced during active gameplay
- Forehead-holding position means UI is "upside down" from player's perspective but right-side up for clue-givers

## Out of Scope (v1)

- User accounts and cloud sync
- Multiplayer/multi-device gameplay
- Deck sharing between users
- Score persistence across sessions
- AI-generated cards

## Success Criteria

- Tilt detection works reliably on iOS Safari and Android Chrome
- Round can be completed without accidental triggers or missed inputs
- Custom deck creation takes under 30 seconds for a 20-card deck
- App loads and functions offline after initial visit
