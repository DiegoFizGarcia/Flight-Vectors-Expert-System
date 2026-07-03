# Flight Vectors – Rule-Based Expert System

A custom-designed 2-player strategy board game powered by a rule-based expert system, built for the Fundamentos de la Inteligencia Artificial course.

## Overview

Flight Vectors is a turn-based, perfect-information game played on a 6x6 grid, where two players each control an Experimental Aircraft. The goal is to reach the opponent's side of the board before they reach yours. Players can move manually, place storm clouds to block the opponent, or place catapults that trigger an automatic "flight" sequence controlled entirely by the inference engine.

The project is split into three phases: game design, expert system design (Fact Base, Rule Base, Inference Engine), and a playable JavaScript/HTML implementation of the full rule set.

## Game Rules

- 6x6 grid board, two aircraft starting at fixed coordinates
- Each turn allows exactly one action: move, place a storm, or place a catapult
- Landing on a catapult triggers automatic flight in a straight line until the aircraft finds a free landing cell
- Flying aircraft can pass over storms and the opponent's aircraft without colliding
- Landing on another catapult chains into another automatic flight ("combo")
- Player 1 wins by reaching row Y=6; Player 2 wins by reaching row Y=1

## Expert System Design

The game logic is implemented as a classic rule-based expert system with three components:

- **Fact Base (BH):** stores aircraft positions, storm and catapult locations, active turn, and a temporary "active flight" fact used during automatic movement
- **Rule Base (BR):** 9 production rules covering manual movement, catapult takeoff, automatic flight resolution (fly over obstacles, land on catapult, land on empty cell), storm/catapult placement, and win conditions
- **Inference Engine (MI):** uses forward chaining, with control strategy based on rule priority and recency, ensuring win-condition rules and automatic flight resolution are always evaluated before returning control to the next player

## Implementation

The Phase 3 deliverable translates the full rule set into a working JavaScript and HTML application, where the Fact Base is represented as a state object and each production rule is implemented as a function, executed inside a `while` loop that mimics the inference engine's automatic flight resolution.

## Repository Structure
'''
├── code/
│ └── flight-vectors.html
├── docs/
│ ├── Proyecto-Fundamentos-IA-Final.pdf
│ └── presentation.pdf
└── README.md
'''

## Tech Stack

JavaScript, HTML, CSS (rule-based expert system architecture)

## Author

Diego Fiz Garcia
