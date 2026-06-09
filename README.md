# Bridge Racer 

Link: https://augus-tj.github.io/bridge_racer/

## Overview
Bridge Racer V3 is a browser-based 3D endless highway racing game built with Three.js. Players drive across a suspension bridge, avoid hazards, perform stunt jumps, build score multipliers, and survive increasingly strange game states including Limbo Mode and Glitch Mode.

---

# Features

## 3D Endless Runner Gameplay
- Fully rendered 3D environment using Three.js.
- Procedural bridge highway environment.
- Infinite-style progression through world wrapping.
- Dynamic speed scaling as gameplay progresses.

## Player Vehicle System
- 3D vehicle model with:
  - Body
  - Cabin
  - Four animated wheels
- Lane-based movement system.
- Smooth lane interpolation.
- Suspension-like squash and stretch effects.
- Wheel rotation animation based on speed.

## Jump Mechanics
### Standard Jump
- Triggered manually.
- Uses gravity and velocity-based physics.
- Allows players to avoid obstacles.

### Fast Descent
- Can be activated while airborne.
- Forces the vehicle downward faster.
- Produces a hard landing deformation effect.

### Ramp Stunt Jump
- Triggered by driving over ramps.
- Launches the player significantly higher.
- Enables aerial stunts.
- Required for accessing some advanced game states.

---

# Scoring System

## Cone Scoring
Successfully passing traffic cones grants:
- Points
- Combo multiplier increases

## Multiplier System
- Starts at x1.0
- Increases through successful obstacle avoidance.
- Resets after mistakes.
- Directly affects score gain.

## High Score Tracking
- Stored using browser Local Storage.
- Persists between sessions.

---

# Obstacle Types

## Traffic Cones
Primary obstacle type.

### Avoiding
- Awards points.
- Increases combo multiplier.

### Hitting
- Immediate game over.

---

## Cats

### Hitting Cats
- Deducts score.
- Resets combo multiplier.
- Activates blocker mechanic.
- Can push player into negative-score states.

### Dodging Cats
- Required during Limbo Mode.
- Important for survival and progression.

---

## Demons
Special bonus entities.

### Hitting
- Awards bonus points.

### Animation
- Wing flapping.
- Hovering movement.

---

## Humans
Unlocked after reaching higher scores.

### Hitting
- Large score penalty.

### Avoiding
- No reward or penalty.

---

## Collapse Traps
Road collapse hazards.

### Survival
- Must jump over them.

### Failure
- Causes immediate game over.

---

## Ramp & Hoop Challenge

### Ramp
- Appears periodically.
- Launches the player into the air.

### Hoop
- Spawned after ramps.
- Awards 1000 points when successfully passed through.

### Missing Hoop
- Applies major score penalty.

---

# Special Gameplay Systems

## Blocker System
Activated after hitting cats.

Effects:
- Displays remaining blocker count.
- Forces player to clear 20 cones.
- Prevents normal combo progression until cleared.

---

## Milestone System

### Positive Milestones
| Score  |           Event            |
|--------|----------------------------|
| 100    | Multiplier increased to x3 |
| 1,000  | Milestone banner           |
| 10,000 | Civilization milestone     |
| 99,999 | Game completion milestone  |

### Negative Milestones
| Score  |           Event            |
|--------|----------------------------|
|  -100  | Increased cat punishment   |
|  -200  | Warning event              |
|  -300  | Severe punishment          |
|  -400  | Limbo Mode                 |
|  -500  | Glitch Mode                |

---

# Limbo Mode

A secret alternative game state.

## Trigger Conditions
- Score reaches -400.
- Player must have jumped or used a ramp at least once.

## Environment Changes
- White void environment.
- Bridge disappears.
- Ocean disappears.
- Special Limbo UI appears.

## Objective
Dodge 10 cats.

## Reward
Successful completion:
- Returns player to normal world.
- Sets score to positive value.
- Grants multiplier bonus.

---

# Glitch Mode

Triggered when score drops below -500.

Features:
- Screen distortion.
- Random camera shake.
- Purple glitch overlay.
- Alternate progression path.

---

# Environment Systems

## Bridge Environment
Includes:
- Suspension bridge pylons.
- Animated cable structures.
- Ocean rendering.
- Road markings.
- Guard rails.

## Dynamic Sky
Procedurally generated:
- Sky dome
- Cloud formations
- Atmospheric fog

---

# Visual Effects

## Particle System
Used for:
- Cat impacts
- Demon collection
- Human impacts
- Hoop completion
- Crash feedback

## Milestone Banners
Large animated announcements for:
- Progress milestones
- Negative milestones
- Completion states

## World Skins
The game can dynamically switch:
- Normal world
- Limbo world

---

# Input Systems

## Keyboard Controls

|       Key       |    Action    |
|-----------------|--------------|
| A / Left Arrow  | Move Left    |
| D / Right Arrow | Move Right   |
| W / Up Arrow    | Jump         |
| S / Down Arrow  | Fast Descent |
| P / ESC         | Pause        |
| Space           | Restart      |

---

## Mobile Controls

### Touch Buttons
- Left
- Right
- Jump
- Fast Descent

### Swipe Controls
- Swipe Left
- Swipe Right
- Swipe Up
- Swipe Down

---

# User Interface

## HUD
Displays:
- Score
- Combo multiplier
- Speed
- Blocker progress

## Pause Menu
- Resume game
- Keyboard support
- Touch support

## Game Over Screen
Displays:
- Final score
- Best score
- Restart option

---

# Technical Features

## Rendering
- Three.js r128
- Perspective camera
- Fog effects
- Directional lighting
- Ambient lighting

## Performance Optimizations
- Delta-time based movement.
- Spawn accumulator system.
- Object cleanup.
- Mobile detection.
- Device pixel ratio limiting.

## Persistence
- High score saved using Local Storage.

---

# Game Loop Architecture

Main systems updated every frame:

1. Physics
2. Vehicle movement
3. Obstacle spawning
4. Collision detection
5. Score calculation
6. Milestone handling
7. Particle updates
8. UI updates
9. Rendering

---

# Win and Lose Conditions

## Win Condition
Reach:
- 99,999 points

## Lose Conditions
- Hit a traffic cone.
- Fall into a collapse trap without jumping.

---

# Technologies Used

- HTML5
- CSS3
- JavaScript (ES6)
- Three.js
- Browser Local Storage

---

# Author Notes

This project combines:
- Endless runner mechanics
- Score-combo systems
- Physics-based jumping
- Secret alternate game modes
- Dynamic difficulty progression
- Mobile and desktop support

into a single lightweight browser game requiring no external backend services.
