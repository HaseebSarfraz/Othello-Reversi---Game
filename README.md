# Othello (Reversi) — Demo & OOP Design Notes (CSC207, University of Toronto)

> **Academic Integrity** — This is a **demo-only case study**. Per UofT CSC207 policy the source code is private. I’m happy to discuss implementation details in interviews.

## Demo
- **Video (≈90–120s):** https://github.com/HaseebSarfraz/Othello-Reversi/releases/download/v1.0.0/Othello.Demo.mp4  ← replace with your actual Release link

## Overview
A complete **console Othello** game focused on **OOP design practice** in Java. It implements full rules (legal moves, flips, pass/terminal states, scoring), Human/CPU play, and a small simulator for batch runs.

## Highlights
- Play modes: **Human vs Human**, **Human vs Random**, **Human vs Greedy**, **Random vs Random**, **Random vs Greedy**.
- CPU agents: **Random** and **Greedy** (maximize immediate flips).
- Clean separation of **engine** (board/rules) from **controllers** (match types).

### Design notes
- **Model:** `OthelloBoard`, `Move` keep rules and state transitions self-contained.
- **Strategy pattern:** `Player` interface with `PlayerHuman`, `PlayerRandom`, `PlayerGreedy`.
- **Controllers:** one class per matchup keeps the game loop/UI orchestration minimal and testable.
- **Simulation:** headless runner to execute large numbers of games for statistics.

## Random vs Random statistics (10,000 games)
> RNG is **not seeded**; numbers vary run-to-run but the pattern is consistent.

- **P1 win rate:** `0.4506`  
- **P2 win rate:** `0.5102`  
- **Ties:** `≈ 0.0392` (from 1 − 0.4506 − 0.5102)

**Conclusion:** Results **do not support H₀** (no advantage). Player 2 shows a small but clear edge in Random vs Random play.  
See `randomVsRandomReport.txt` for the write-up and a simple coin-flip counter-example argument used to reason about chance vs effect size.

## Testing
- Unit tests on move legality, flips, passes, terminal states, and scoring.
- Light property checks (e.g., parity/validity of legal moves across turns).

## What I learned
Modeling game rules cleanly; using **interfaces and strategies** to swap AI behaviors; writing small simulations to gather **statistics** without seeded RNG; and separating engine/controller concerns so the program remains easy to extend (e.g., adding Minimax later).
