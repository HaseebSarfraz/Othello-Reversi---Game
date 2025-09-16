# Othello (Reversi) — Demo & OOP Design Notes (CSC207, University of Toronto)

> **Academic Integrity** — This is a **demo-only case study**. Per UofT CSC207 policy, the source code and implementation details are private. I’m happy to discuss the project in interviews.

## Demo
- **Video (≈90–120s):** https://github.com/HaseebSarfraz/Othello-Reversi---Game/releases/download/v1.0.0/Othello.Demo.mp4
- (Optional) Thumbnail:  
  [![Watch the demo](media/thumbnail.png)](https://github.com/HaseebSarfraz/Othello-Reversi---Game/releases/download/v1.0.0/Othello.Demo.mp4)

## Overview
A complete **console Othello** game focused on **OOP practice in Java**. Implements full rules (legal moves, flips, pass/terminal states, scoring), Human/computer play, and a small simulator for batch runs and statistics.

## Highlights
- Modes: **Human vs Human**, **Human vs Random**, **Human vs Greedy**, **Random vs Random**, **Random vs Greedy**.
- Programmed opponents: **Random** and **Greedy** (maximize immediate flips).
- Clean separation of **board/rules logic** from **match orchestration**, using core OOP principles—**abstraction**, **encapsulation**, **inheritance/polymorphism**, and **interfaces**—so behavior modules can be swapped without touching core rules.

## Random vs Random statistics (10,000 games)
- **P1 win rate:** `0.4506`  
- **P2 win rate:** `0.5102`  
- **Ties:** `≈ 0.0392`  
**Conclusion:** Results do **not** support H₀ (no advantage); Player 2 shows a small, consistent edge.

## Testing
- Unit tests cover move legality, flipping behavior, pass/terminal states, and scoring edge cases.
- Light property checks for invariants (e.g., basic parity/validity conditions across turns).

## What I learned
- **Java OOP fundamentals**: abstraction, encapsulation, interfaces, and inheritance/polymorphism.
- **Thorough testing** of stateful, edge-case-heavy functions.
- **Collecting and summarizing statistics** from simple simulations.
- **Separation of concerns** to keep the project easy to extend (e.g., adding stronger heuristics later).
