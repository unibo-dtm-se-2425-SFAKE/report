---
title: User guide
has_children: false
nav_order: 10
---

## User Guide

Sfake offers an accessible gaming experience designed to be both intuitive and technically lightweight. Once launched, the application opens in a dedicated game window where players are welcomed by the main menu. From here, users can choose to start a new session, consult the rules, or quit the application. The design emphasizes simplicity, making the system accessible to casual players while serving as a robust case study in software engineering practices.

Gameplay centers around guiding a snake across a grid-based environment using the keyboard arrow keys. The objective is to collect apples, which appear randomly on the screen and increment both the player’s score and the length of the snake. Every few apples, a timed bomb appears; if the snake collides with it, the game ends, while avoiding it allows play to continue. The player must also prevent the snake from colliding with the walls or itself. A dedicated score bar at the top of the screen provides continuous feedback during the session, while the interface remains clear and distraction-free.

The game concludes when a collision occurs, displaying a Game Over screen with the final score and options to restart or return to the main menu. Restarting restores the game state instantly, allowing players to quickly try again and improve their performance.

Sfake is compatible with Windows, macOS, and Linux systems, supporting Python 3.9 to 3.12, and requires minimal computational resources. The game has been tested to run smoothly at 60 FPS with modest memory and disk space requirements, ensuring a stable experience across environments. In case of issues, such as dependency conflicts or input unresponsiveness, reinstalling requirements via pip typically resolves the problem. Further support, troubleshooting, and updates are available through the GitHub repository, where users can also submit issues, specifying their Python version and operating system for more effective assistance
