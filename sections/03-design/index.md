---
title: Design
has_children: false
nav_order: 4
---

# Design

This chapter explains the strategies used to meet the requirements identified in the analysis. 

Ideally, the design should be the same, regardless of the technological choices made during the implementation phase.

> You can re-order the sections as you prefer, but all the sections must be present in the end

## Architecture 

- Which architectural style (e.g. layered, object-based, event-based, shared dataspace)? Why? Why not the others?
- Provide details about the actual architecture (e.g. N-tier, hexagonal, etc.) you are going to adopt. Motivate your choice.
- Provide a high-level overview of the architecture, possibly with a diagram
- Describe the responsibilities of each architectural component

> UML Components diagrams are welcome here

## Modelling

### Domain driven design (DDD) modelling

- Which are the bounded contexts of your domain? 
- Which are domain concepts (entities, value objects, aggregates, etc.) for each context?
- Are there repositories, services, or factories for each/any domain concept?
- What are the relavant domain events in each context?

> Context map diagrams are welcome here

### Object-oriented modelling

- What are the main data types (e.g. classes) of the system?
- What are the main attributes and methods of each data type?
- How do data types relate to each other?

> UML class diagrams are welcome here

## Interaction

- How do components *communicate*? *When*? *What*?

- Which **interaction patterns** do they enact?

> UML sequence diagrams are welcome here

## Behaviour

- How does **each** component *behave* individually (e.g., in *response* to *events* or messages)?
    + Some components may be *stateful*, others *stateless*

- Which components are in charge of updating the **state** of the system? *When*? *How*?

> UML state diagrams or activity diagrams are welcome here
