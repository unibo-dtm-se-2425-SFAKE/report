---
title: Design
has_children: false
nav_order: 4
---

### Design
The design of Sfake has been guided by the need to create a system that is modular, maintainable, and extensible, while at the same time remaining simple enough to be fully understood and tested in an academic context. The strategies described in this chapter are meant to show how the requirements identified during the analysis phase were translated into a coherent set of architectural, infrastructural, and modeling decisions. Importantly, the design has been conceived in a way that does not depend on specific technological choices, so that the same structure could be implemented even with different frameworks or programming languages.

### Architecture
The architectural style adopted in Sfake is the Model-View-Controller (MVC) pattern. This choice was made because the separation of concerns offered by MVC aligns well with the structure of a video game like Snake, where the logic that governs gameplay must remain independent from both the rendering layer and the way users interact with the system. Other architectural styles, such as layered architectures or event-driven designs, were considered but ultimately rejected. A layered approach would have introduced unnecessary complexity for a project of this scope, while a purely event-driven design would have made the logic harder to trace and test in a deterministic way. MVC offered the right balance between simplicity, testability, and extensibility.
At a high level, the architecture consists of three main components: the Model, responsible for maintaining the state of the game and implementing the business logic; the View, which manages the rendering of the game elements and user interface; and the Controller, which mediates user inputs and delegates updates to the Model. Their responsibilities are clearly defined and non-overlapping. The Model is the only component allowed to update the state, the View only reads from the state to display it, and the Controller is responsible for capturing external events and mapping them into model updates.
The architecture can be represented through a UML component diagram.
METTERE DIAGRAMMA

### Infrastructure
Although Sfake is not a distributed system, certain infrastructural considerations were still taken into account. The game runs as a standalone client on a user’s machine, and all components (the controller), the rendering logic, and the state management. No networked infrastructure, load balancers, or external services are necessary for this version of the project, since persistence and communication requirements are minimal.
Despite its simplicity, the infrastructural design ensures that the system can be executed in a clean and reproducible way. This is facilitated by GitHub Actions, which provide an automated and isolated environment to execute tests on every commit. In this sense, the CI/CD pipeline acts as an infrastructural layer that guarantees the system behaves consistently across different operating systems and setups.
The deployment can be represented through a UML deployment diagram. 
METTERE DIAGRAMMA

### Modelling
The modelling of the system was approached using Domain-Driven Design (DDD) principles. The bounded context of the application corresponds to the domain of the Snake game. Within this domain, several core concepts were identified. The Snake entity represents the player’s avatar, with attributes such as its body segments and direction of movement. The Apple is another entity, functioning as a consumable object that triggers growth and score updates. The Bomb is modeled as a timed entity with its own lifecycle, expiring after a fixed duration. The Score is treated as a value object, updated upon interactions with apples and displayed to the player.
Supporting these entities, repositories and services have been defined implicitly within the model. For example, the spawn logic for apples and bombs can be considered as domain services, since they encapsulate domain rules that do not belong to a single entity. Domain events such as apple consumed, bomb exploded, or game over provide a conceptual map of how the system evolves over time.
This domain model can be represented with a context map diagram and class diagrams to illustrate the relationship between entities. 
METTERE DIAGRAMMA

### Object-Oriented Modelling
From an object-oriented perspective, the system is composed of a number of classes that reflect the domain concepts. The Snake class includes attributes such as body segments (stored as coordinates on the grid) and methods to move, grow, and detect collisions. The Apple and Bomb classes are relatively lightweight, mainly holding position data and exposing lifecycle-related methods. The Game Model class aggregates these elements, coordinating their interactions and enforcing game rules.
The View classes are responsible for drawing the snake, apples, bombs, and UI components like the score and the game-over screen. Meanwhile, the Controller class handles input events, such as arrow key presses, and translates them into commands that alter the model’s state. The relationships between these classes are cleanly separated: the Model is independent from the View and Controller, while the latter two depend on it to operate.
METTERE DIAGRAMMA

### Interaction
The communication between components follows the MVC interaction pattern. User input, such as pressing an arrow key, is first captured by the Controller. The Controller then invokes the appropriate method on the Model to change the snake’s direction. After the Model has updated its state (for instance, moving the snake forward and checking for collisions) the View queries the Model and refreshes the screen accordingly.
This cycle of input–update–render continues until a terminal condition is reached, such as the snake colliding with a bomb or with itself. At that point, the Model updates its state to reflect the “game over” condition, and the View is responsible for rendering the corresponding screen. The Controller remains active, listening for restart commands.
These interactions can be represented in a UML sequence diagram. 
METTERE DIAGRAMMA

### Behaviour
Each component exhibits well-defined behavior in response to events. The Model is stateful and is the only component that can update the state of the game. Its state evolves deterministically in response to external inputs or internal events, such as the expiration of a bomb. The View, on the other hand, is stateless: it reacts to model updates by redrawing the corresponding elements but does not retain information about the game state itself. The Controller is event-driven and mediates between external input and model updates.
The lifecycle of the Snake entity, for example, can be described using a state diagram: it starts in an initial state with a fixed length, grows upon apple consumption, and transitions into a terminal state upon collision. Similarly, the Bomb entity follows a timed lifecycle, appearing on the screen, counting down, and either disappearing harmlessly or causing the end of the game if touched.
These behaviors can be summarized through UML state diagrams and activity diagrams.
METTERE DIAGRAMMA

### Data-related aspects
Persistent storage is not strictly required in Sfake, since all data (such as snake position, score, and bomb timers) exist only for the duration of a single gameplay session. However, the design leaves open the possibility of adding persistent features, such as saving high scores or maintaining leaderboards across sessions. If implemented, these features would likely rely on lightweight storage solutions such as JSON files or key-value stores, given the relatively small scale of the data.
Currently, all queries on the data are performed directly by the Model, which provides the canonical source of truth for the game state. Since no concurrent reads or writes are needed (there is only one active game state at a time) the consistency model is simple and no synchronization mechanisms are required. Shared data between components is minimized: only the Model maintains mutable state, and the View and Controller rely on it as the single source of truth.
