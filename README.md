# Mole-Whacking
It is a game developed based on Pygame to train children's reaction speed.
# Game Rules
### 1)Objective: 
 Whack as many moles as you can in 60 seconds to score high!
### 2)Controls:
 Move the mouse to aim the hammer.                                                                                                                                               
 Left-click to strike. +10 points per accurate hit on a mole's head.
### 3)Difficulty:
 Moles change holes every 0.8s initially.                                                                                                                                        
 At 40s left → Speed increases to 0.65s/hole.                                                                                                                                    
 At 20s left → Further speeds up to 0.5s/hole.                                                                                                                                  
### 4)Victory:
 Game ends when time runs out. Total score vs. historical best is displayed.

# Frontend Implementation
## 1)User Interface (UI)

###  Start Interface: 

Displays the game title and a "Start" button.

###  Main Game Interface:

Background image showing a grassland and holes.

Real-time countdown (top) and current score (bottom).

Moles randomly pop up from holes; the hammer follows mouse movement, and clicking triggers a hitting animation.

###  End Interface: 

Shows the final score, best historical record, and a "Play Again" button.

## 2)Interaction Design

###  Mouse Operations:

Move the mouse to control the hammer's position.

Left-click to strike moles, triggering sound effects and animations.

###  Dynamic Feedback:

Moles display a "hit" state when struck; the hammer switches to an action animation during strikes.

A countdown sound effect plays during the last 10 seconds.

# Backend Logic

## 1)Core Mechanics

###  Mole Spawning:

Randomly selects predefined positions (cfg.HOLE_POSITIONS).

Shortens spawn intervals over time (800ms → 650ms → 500ms).

###  Collision Detection:

Uses PyGame’s pygame.sprite.collide_mask for pixel-perfect collision checks.

###  Scoring: 

+10 points per successful hit.

## 2)State Management

###  Time Control: 

60-second countdown; game ends when time expires.

###  Record Saving: 

Persists the best score to a local file (.rec).

## 3)Modular Design

###  Hammer Class (Hammer): 

Manages position, strike animations, and collision masks.

###  Mole Class (Mole): 

Handles state transitions (normal/hit) and position resets.

###  Interface Modules: 

Independently handle rendering and interaction logic for start/end interfaces.

