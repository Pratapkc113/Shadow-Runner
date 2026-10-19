# Shadow-Runner
Shadow Runner is a game based on a concept where your death will actually help you clear the game. Its a solo project for my university and also a new start in my journey. This game still has a lot of things to improve and will try and continue to make it a fully functional proper game in days to come. 
## Overview

Shadow Runner is a puzzle-platformer focused on time manipulation and cooperative ghost mechanics.

Instead of solving challenges alone, the player records previous attempts and then works together with ghost replays of those attempts to overcome obstacles.

Every run creates a timeline.

Every failure becomes a solution.

The core gameplay loop revolves around:

- Recording player actions
- Replaying previous runs as ghosts
- Activating mechanisms with ghost clones
- Solving environmental puzzles
- Completing increasingly complex levels

The project was developed in Unreal Engine 5 using Blueprint scripting.

---

# Gameplay

The player must navigate a level containing:

- Platforms
- Spike traps
- Pressure plates
- Doors
- Exit zones

Some obstacles cannot be overcome alone.

To progress, the player must use previous attempts to create ghost replays.

These ghosts repeat recorded movements from earlier runs and can activate puzzle objects while the player advances through the level.

---

## Core Features

### Player Movement

The player can:

- Move left and right
- Jump
- Interact with the environment
- Trigger pressure plates
- Die and respawn

Movement uses Unreal Engine's Character Movement Component.

---

### Death & Respawn

Hazards such as spikes cause instant death.

Upon death:

- Current run data is saved
- Player is returned to the spawn point
- Previous run becomes available for replay

This creates the foundation for the ghost mechanic.

---

### Ghost Replay System

The ghost system is the central mechanic of the game.

Every frame records:

- Position
- Rotation
- Time
- Movement state

After death:

- Recorded data is stored
- A ghost actor is spawned
- Ghost reproduces recorded movement

This allows players to effectively cooperate with their past selves.

---

### Pressure Plates

Pressure plates can be activated by:

- The player
- Ghost clones

Activated plates can:

- Open doors
- Trigger events
- Modify level state

This enables puzzle creation through timeline cooperation.

---

### Doors

Doors act as progression barriers.

They:

- Remain closed by default
- Open when linked pressure plates are activated
- Can be used as puzzle objectives

---

### Exit System

The exit marks level completion.

Once reached:

- The level is completed
- Completion logic is executed
- Future versions will support level progression

---

# Game Loop

The gameplay loop follows the pattern:

1. Start Run
2. Explore Level
3. Activate Objects
4. Die or Restart
5. Save Run Data
6. Spawn Ghost
7. Ghost Replays Previous Actions
8. Complete Puzzle
9. Reach Exit

---

# Example Puzzle

Example level structure:

Start

↓

Pressure Plate

↓

Spike Pit

↓

Locked Door

↓

Exit

### First Attempt

Player:

- Activates pressure plate
- Opens the door
- Falls into spikes
- Death recorded

### Second Attempt

Ghost:

- Replays path
- Activates pressure plate
- Keeps door open

Player:

- Runs through the level
- Passes the door
- Reaches exit

Puzzle solved.

---

# Technical Architecture

The project consists of six major gameplay systems.

## BP_ThirdPersonCharacter

Responsible for:

- Player movement
- Jumping
- Run recording
- Death handling

---

## BP_Ghost

Responsible for:

- Playback of recorded data
- Ghost movement
- Replay synchronization

---

## ST_Frame

Stores replay data.

Contains:

text
Location (Vector)
Rotation (Rotator)
Time (Float)
IsJumping (Boolean)

---

## BP_PressurePlate

Responsible for:

- Overlap detection
- Trigger activation
- Door communication

---

## BP_Door

Responsible for:

- Opening
- Closing
- Puzzle progression

---

## BP_GameManager

Responsible for:

- State management
- Ghost spawning
- Respawning
- Run history

---

# Technologies Used

- Unreal Engine 5
- Blueprint Visual Scripting
- Unreal Character Movement Component
- Actor Components
- Struct-Based Data Recording
- Collision and Trigger Systems

---

# Current Features

✅ Character movement

✅ Jumping

✅ Platforms

✅ Spike hazards

✅ Death and respawn

✅ Pressure plates

✅ Doors

✅ Exit system

✅ Ghost replay prototype

✅ Playable puzzle loop

---

# Future Development

Planned features include:

## Short-Term

- Multiple levels
- Improved ghost visuals
- Restart system
- Better user interface
- Sound effects
- Win screen

## Mid-Term

- Multiple simultaneous ghosts
- Checkpoints
- Moving platforms
- Time-based switches
- Puzzle chains

## Long-Term

- Steam release
- Save system
- Level selection
- Achievements
- Advanced timeline puzzles
- Narrative elements

---

# Project Goals

The goal of Shadow Runner is to explore a unique puzzle mechanic built around cooperation with previous versions of the player.

By turning failed attempts into useful gameplay assets, the game transforms death from punishment into progress.

Every run matters.

Every mistake becomes part of the solution.

---

# Installation

## Requirements

- Windows 10/11
- Unreal Engine 5 (for source project)
- Packaged build for standalone play

## Running the Project

1. Clone the repository

git clone https://github.com/yourusername/ShadowRunner.git

2. Open the project in Unreal Engine 5

text
ShadowRunner.uproject

3. Press Play inside Unreal Editor

or

4. Package the project

text
Platforms → Package Project → Windows

---

# Author

Developed by Prajwol K C
Id 1171321
An experimental Unreal Engine project exploring time-manipulation puzzle mechanics through Blueprint gameplay systems.

---

# License

This project is licensed under the MIT License.
