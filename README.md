# Othello (Reversi) — Demo & OOP Design Notes (CSC207, University of Toronto)

> **Academic Integrity** — This is a **demo-only case study**. Per UofT CSC207 policy, the source code and implementation details are private. I’m happy to discuss the project in interviews.

## Demo
- **Video (≈90–120s):** https://github.com/HaseebSarfraz/Othello-Reversi/releases/download/v1.0.0/Othello.Demo.mp4
  _(replace with your actual Release link if different)_

## Overview
A complete **console Othello** game focused on **OOP practice in Java**. Implements full rules (legal moves, flips, pass/terminal states, scoring), Human/computer play, and a small simulator for batch runs and statistics.

## Highlights
- Modes: **Human vs Human**, **Human vs Random**, **Human vs Greedy**, **Random vs Random**, **Random vs Greedy**.
- Programmed opponents: **Random** and **Greedy** (maximize immediate flips).
- Clean separation between the **game rules/board logic** and the **match orchestration**, so behavior modules can be swapped without touching the core rules.

## Random vs Random statistics (10,000 games)
- **P1 win rate:** `0.4506`  
- **P2 win rate:** `0.5102`  
- **Ties:** `≈ 0.0392`  
**Conclusion:** Results do **not** support H₀ (no advantage); Player 2 shows a small, consistent edge. See the included short write-up for reasoning based on simple probability comparisons.

## Testing
- Unit tests cover move legality, flipping behavior, pass/terminal states, and scoring edge cases.
- Light property checks for invariants (e.g., basic parity/validity conditions across turns).

## What I learned
- **Java OOP skills**: organizing code into clear components with encapsulated responsibilities.
- **Thorough testing** of stateful, edge-case-heavy functions.
- **Collecting and summarizing statistics** from simple simulations (without seeded RNG).
- **Separation of concerns** so the project is easy to extend later (e.g., adding stronger heuristics).
