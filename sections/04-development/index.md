---
title: Development
has_children: false
nav_order: 5
---

## Development

### Implementation details

The implementation and development process was partially based on Pair Programming, a software engineering practice commonly associated with agile methodologies. In this approach, two developers collaborate at the same workstation: while one writes the code (driver), the other simultaneously reviews it (observer), identifying potential issues or suggesting corrections. The roles are interchangeable and, in this project, their application was facilitated by the compatibility of the participants’ schedules during lessons.

The continuous review inherent in this practice enabled the early detection of errors and inconsistencies, thereby reducing the need for extensive rework in later stages. Its adoption contributed to improved code quality and enhanced knowledge sharing within the group. Nevertheless, pair programming was not always feasible due to practical constraints. For this reason, it was necessary to establish clear commit conventions and a structured division of responsibilities in order to ensure consistency and effective collaboration throughout the development process.

### DVCS

The project employed a Distributed Version Control System (DVCS), specifically Git, to manage the source code throughout the development process. Git was chosen for its efficiency in handling commits, merging, and collaborative workflows, enabling team members to work in parallel while maintaining a consistent and traceable code history, even though parallel work was not particularly prominent in this project, due to the limited dimension of it.

The repository was hosted on GitHub, which provided additional functionalities for collaboration, such as issue tracking, pull requests, and workflows. This platform facilitated transparent communication, simplified code reviews, and supported effective coordination among contributors. Such functionalities are usable for the future of the project, there was no need for most of them during the implementation, but it is the best platform of hosting for its simplicity and eventually the future maintainability of the project.

To ensure a coherent and readable commit history, the project adopted the Conventional Commits specification. This practice standardized commit messages through a predefined format (e.g., feat, fix, docs), allowing for a clear understanding of changes, automated changelog generation, and easier project maintenance over time. The use of conventional commits also improved traceability by linking code changes to specific features or bug fixes.

Together, these tools and practices enhanced the reliability of the development process, ensured codebase integrity, and supported both collaboration and long-term maintainability of the project.

### Technological details

#### Core Functionalities

The project was developed in Python, a high-level programming language widely adopted in both academic and professional contexts for its readability, flexibility, and extensive ecosystem of libraries, such as Pygame. Python’s simplicity of syntax and community support made it particularly effective for the rapid testing and development required in this project.

The core functionalities rely on Pygame, a library built on top of the SDL framework, which provides essential modules for handling graphics, audio, and user input. This choice enabled the creation of an interactive game while remaining entirely within the Python ecosystem. To facilitate packaging and distribution, pygame-build (≥0.6.0) was adopted, Twine was added to deploy the application on PyPi, but we found some difficulties in making it work and so the game is currently not deployed on PyPi, even though passing all the correct tests and release clauses.

#### Code Correction

The project also integrates several tools aimed at ensuring code quality and reliability.

- Mypy supports static type checking, reducing the likelihood of type-related errors. 
- Prospector aggregates multiple linting and style analysis tools, enforcing consistency and maintainability of the source code. 
- Coverage was used to measure the extent of test verification, providing an indicator of the robustness of the test suite.

Finally, additional dependencies are managed through the requirements.txt file and the dev-version of it, ensuring reproducibility of the development environment and simplifying collaboration and deployment.
