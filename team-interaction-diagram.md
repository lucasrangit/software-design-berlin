# Team Interaction Diagram

This diagram illustrates the communication and dependency structure between the teams, following the principles of Team Topologies. The architecture of the system should reflect these communication paths.

```mermaid
graph TD
    subgraph "Value Stream Teams"
        Team_A[Team A<br/>Stream-Aligned<br/>(Editor Experience)]
        Team_B[Team B<br/>Stream-Aligned<br/>(Reviewer & Audit UI)]
    end

    subgraph "Platform Team"
        Team_C[Team C<br/>Platform/Enabling<br/>(Trust & Infra)]
    end

    Team_A -- Document for Review --> Team_B
    Team_C -- "Trust Platform as-a-Service" --> Team_A
    Team_C -- "Trust Platform as-a-Service" --> Team_B
```

## Key Interaction Modes

*   **Platform as-a-Service:** Team C provides the "Trust Platform" as a service to both stream-aligned teams. This reduces the cognitive load on Teams A and B, allowing them to focus on their specific parts of the user journey.
*   **Handoff / Collaboration:** Team A's work flows to Team B. The precise mechanism for this (e.g., a shared database schema, a well-defined API, an event stream) will define the coupling point between their respective systems.
