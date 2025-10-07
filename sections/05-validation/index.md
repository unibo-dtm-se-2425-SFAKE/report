---
title: Validation
has_children: false
nav_order: 7
---

## Validation

### Testing Approach

The validation of **Sfake** followed a structured approach that combined **Test-Driven Development (TDD)**, automated testing at multiple levels (unit, integration, system), and manual acceptance testing. Whenever possible, TDD was applied by writing tests before implementing the functionality, particularly for scoring logic and timed bomb mechanics, which benefited from having clear, verifiable acceptance criteria.

The project adopted Python’s built-in **unittest** framework because of its simplicity, portability, and native integration with Python development workflows. This choice ensured that no additional dependencies were required and allowed developers to run tests easily in any environment, including GitHub Actions.

### Unit Testing

Unit tests focused on verifying the behavior of individual components in isolation, such as:

- snake movement,
- apple spawning,  
- bomb countdown,  
- collision detection,  
- score updates.  

Each test was mapped to specific functional requirements (e.g., **FR2: Snake movement, FR3: Apple consumption, FR4: Bomb collision**).

The rationale was to ensure that each core mechanic operated correctly under normal and edge-case conditions (e.g., snake moving against borders, bomb timer expiration).  
The unit test suite achieved a **100% success rate** across all executed cases, covering all identified functional requirements.

### Integration Testing

Integration tests targeted the interactions between components, for example:

- verifying that input events captured by the controller correctly updated the game state in the model,  
- ensuring that apple consumption triggered both snake growth and score updates,  
- validating that bomb expiration restored normal apple spawning.  

The purpose was to confirm that independently correct modules also worked as expected when combined. These tests also passed consistently during CI runs.  

Where appropriate, **test doubles (mocks)** were used to isolate dependencies, such as mocking `pygame.event.get()` to simulate input events. This allowed input handling to be validated without requiring real user interaction.

### System Testing

System tests simulated entire gameplay flows: launching a session, moving the snake, consuming apples, avoiding bombs, colliding with obstacles, and verifying that the game correctly transitioned to the **Game Over** state.

These tests were designed to reflect the acceptance criteria of the functional requirements (**FR1–FR6**). For instance, **FR5** was validated by confirming that collisions led to termination of movement, score display, and restart options.

The test suite achieved a **100% pass rate** across all system-level tests, ensuring consistency and reliability of end-to-end behavior. Tests were run automatically through **GitHub Actions** on every push, ensuring validation in a clean environment across multiple operating systems.

### Acceptance Tests (Manual)

Manual acceptance testing was carried out by running the game in real conditions and verifying user interactions. Tests included:

- confirming that the snake responded immediately to arrow-key inputs,  
- checking that apples appeared in random valid positions and increased the score when consumed,  
- verifying that bombs appeared after a sequence of apples, lasted 5 seconds, and disappeared without penalty if avoided,  
- ensuring that the Game Over screen showed the score and allowed restarting via the Start button.  

All acceptance tests met their acceptance criteria successfully, confirming that the system matched user expectations and provided a smooth gameplay experience.
