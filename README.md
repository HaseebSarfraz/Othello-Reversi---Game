# Othello (Reversi) — Demo & Design Notes (CSC207, University of Toronto)

> **Academic Integrity** — This is a **demo-only case study**. Per UofT **CSC207** policy the source code is private. I’m happy to discuss implementation details in interviews.

## Demo
- **Video (≈90–120s):** https://youtu.be/OTHELLO_DEMO_LINK  ← replace with your unlisted link
- Optional local copy: `media/demo.mp4` (and `media/thumbnail.png`)

## Overview
A complete **console Othello** game with legal move generation, flips, passes, and scoring. Includes CPU play and a small simulator for benchmarking.

## Highlights
- Play modes: Human vs CPU and CPU vs CPU.
- **CPU agents:** Random and **Greedy** (maximize flips).
- **Performance:** runs **10,000** random games in **< 7 seconds** on a laptop-class CPU (deterministic seeds for reproducibility).

## Design
- **Board model:** 8×8 bit-backed representation; efficient move generation & flips.
- **Strategy pattern** selects the active CPU agent.
- Clean separation of rules/engine from I/O for easier testing.

## Testing
- Unit tests for move legality, flips, pass/terminal states, and scoring.
- Property tests for invariants (e.g., legal move parity, undo/apply behavior).

## What I learned
Implementing fast, correct move generation; structuring a small engine so strategy changes (Random→Greedy→Minimax) are drop-in.
