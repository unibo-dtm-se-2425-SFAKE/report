---
title: Developer guide
has_children: false
nav_order: 11
---

## Developer Guide

The development of Sfake follows professional but accessible practices, designed so that new contributors can quickly set up the project and start contributing. The environment requires only Python 3.9 or later and git. Once the repository is cloned, developers are expected to create a virtual environment, install the dependencies, and verify that the test suite runs successfully. This setup guarantees consistency across different systems and ensures that all contributors share the same foundation for development.

The repository organization reflects a simple but effective workflow. The main branch contains stable the latest release. This approach ensures that the code base remains clean, stable, and completely reviewed. From the latest commits and pushes we activated GitHub Actions, this solution help for eventual future implementations, simplifying the process of development and deployment. Creating branches for developing, testing and adding features will be feasible and strongly adviced.

Testing plays a central role in the project. The test suite is structured around the three main components of the MVC architecture: the model, which covers the snake movement and game mechanics; the view, which verifies that the graphical elements are rendered correctly through Pygame; and the controller, which ensures that user inputs and game flow are handled as expected. Tests are written with Python’s unittest framework and can be executed as a complete suite or run selectively to target specific modules. This structure supports both efficient debugging during development and reliable regression testing before releases.

Code quality is preserved through adherence to PEP 8 conventions, with four-space indentation, limited line length, and consistent formatting throughout the code base. Developers are also expected to follow semantic commit message conventions, such as feat:, fix:, test:, docs:, or refactor:, which makes the history of the project easier to navigate and maintain. Automated workflows provided by GitHub Actions further support this by performing checks and tests on every change.

Releases should now be fully automated through semantic versioning. Whenever a new tag is created, GitHub Actions triggers the release pipeline, executes the entire test suite, and, if successful, packages the new version and publishes it as an official release. This process guarantees that each version of the software is tested, stable, and traceable. Collaboration within the project takes place directly on GitHub. This workflow not only upholds professional software engineering standards but also provides an educational environment where contributors can experience modern development practices in a concrete and practical way.

The instructions to download the application and to properly run it are the same as the user:

```sh
git clone https://github.com/unibo-dtm-se-2425-SFAKE/artifact.git
cd artifact
pip install -r requirements.txt
python -m sfake
```

To complete the dev work we can use multiple other commands to possibly clean code errors, test thoroughly the newly added code and control syntax errors.

```sh
python -m pip install -r requirements-dev.txt
python -m unittest discover -s test -t .
python -m prospector sfake           
python -m mypy sfake
```
