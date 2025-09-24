---
title: Requirements
has_children: false
nav_order: 3
---

## Requirements

### User stories

- As a player, I want to control the snake using keyboard arrows, so that I can move it in different directions.

- As a player, I want to see my score updated in real-time, so that I can track my progress.

- As a player, I want the game to end when the snake collides with itself, the walls, or a bomb, so that the challenge is maintained.

- As a player, I want to have a clear game over screen with my final score, so that I can evaluate my performance.

- As a player, I want to restart the game easily from the menu, so that I can play multiple sessions without restarting the application.

- As a player, I want to see bombs occasionally appear and disappear after a short time, so that the gameplay is more dynamic and engaging.

- As a player, I want a menu with “Start”, “Rules”, and “Quit” options, so that I can navigate and configure the game easily.

### Requirements analysis

#### Functional Requirements

- FR1: The system shall allow the player to control the snake via arrow keys.
Acceptance criteria: the snake reacts immediately to input and changes direction without delay, except from opposite directions inputs.

- FR2: The system shall display the current score during the game.
Acceptance criteria: the score increases by 1 unit when a fruit is collected.

- FR3: The system shall end the game when the snake collides with itself, the borders, or a bomb.
Acceptance criteria: collision detection works consistently in all cases.

- FR4: The system shall show a game over screen with the final score and a “Restart” option.
Acceptance criteria: after a game ends, the player sees the score and can restart from the menu.

- FR5: The system shall occasionally spawn temporary bombs after every 3–4 fruits collected.
Acceptance criteria: bombs appear at random positions, last 5 seconds, and disappear if not touched.

- FR6: The system shall include a main menu with “Start”, “Rules”, and “Quit”.
Acceptance criteria: each menu option works as expected, popup for the “Rules” button included.

#### Non-Functional Requirements

- NFR1: The game shall run on common desktop environments (Windows, macOS, Linux).

- NFR2 : The application shall maintain a responsive frame rate (≥ 30 FPS).

- NFR3: The project shall include automated unit tests for core components (model, view, controller).

- NFR4: The source code shall be version-controlled via Git and hosted on GitHub.

#### Implementation Constraints

- IC1: The system must be implemented in Python, with Pygame for graphics.

- IC2: The project must follow an MVC architecture.

- IC3: Continuous Integration and Deployment must be managed via GitHub Action or using semantic versioning to have clear cut commits.
