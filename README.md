# Othello (Reversi) — Demo & OOP Design Notes (CSC207, University of Toronto)

> **Academic Integrity** — This is a **demo-only case study**. Per UofT CSC207 policy the source code is private. I’m happy to discuss implementation details in interviews.

## Demo
- **Video (≈90–120s):** https://github.com/HaseebSarfraz/Othello-Reversi/releases/download/v1.0.0/Othello.Demo.mp4  
  _(replace with your actual Release link)_

## Overview
A complete **console Othello** game focused on **OOP practice in Java**. Implements full rules (legal moves, flips, pass/terminal states, scoring), Human/computer play, and a small simulator for batch runs and statistics.

## Highlights
- Modes: **Human vs Human**, **Human vs Random**, **Human vs Greedy**, **Random vs Random**, **Random vs Greedy**.
- Programmed opponents: **Random** and **Greedy** (maximize immediate flips).
- **Performance:** runs **10,000** random games in **< 7 seconds** on a laptop-class CPU (RNG not seeded).

## Design notes
- **Model & rules:** `OthelloBoard` and `Move` encapsulate state updates and flipping logic.
- **Interfaces & strategies:** `Player` interface with `PlayerHuman`, `PlayerRandom`, `PlayerGreedy` for pluggable opponents.
- **Controllers:** one class per matchup keeps the game loop minimal and easy to reason about.

## Random vs Random statistics (10,000 games)
- **P1 win rate:** `0.4506`  
- **P2 win rate:** `0.5102`  
- **Ties:** `≈ 0.0392`  
**Conclusion:** Results do **not** support H₀ (no advantage); Player 2 shows a small but consistent edge. See `randomVsRandomReport.txt` for the write-up and reasoning.

## Testing
- Unit tests for move legality, flips, pass/terminal states, and scoring.
- Light property checks (e.g., parity of legal moves across turns).

## What I learned
- **OOP in Java:** interfaces, classes, packages, and the Strategy pattern.
- **Thorough testing** of stateful/edge-case-heavy functions.
- **Collecting statistics** via simple simulations (without seeded RNG) and writing a brief report.
- **Separation of concerns:** keeping board/rules independent from controllers and I/O for clarity and future extensions.
