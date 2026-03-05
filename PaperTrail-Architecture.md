# PaperTrail Architecture


## 1. Team Topology & Ownership Model

Here is the high-level map of our team interactions. The system's architecture should be a reflection of this structure.

```mermaid
graph TD
    subgraph "Value Stream Teams"
        Team_A["Team A<br/>Stream-Aligned<br/>(Editor Experience)"]
        Team_B["Team B<br/>Stream-Aligned<br/>(Reviewer & Audit UI)"]
    end

    subgraph "Platform Team"
        Team_C["Team C<br/>Platform/Enabling<br/>(Trust & Infra)"]
    end

    Team_A -- Document for Review --> Team_B
    Team_C -- "Trust Platform as-a-Service" --> Team_A
    Team_C -- "Trust Platform as-a-Service" --> Team_B
```

### Team Inventory

| Team Name | Type | Responsibilities | Current Headcount | Key Skills |
|-----------|------|-----------------|-------------------|------------|
|           |      |                 |                   |            |

### Team Interaction Modes

| Team A | Team B | Interaction Mode | Notes |
|--------|--------|-----------------|-------|
|        |        |                 |       |

*Interaction modes: Collaboration, X-as-a-Service, Facilitating*

### Cognitive Load Assessment

| Team | Services Owned | Cognitive Load (Low/Med/High) | Risk |
|------|---------------|-------------------------------|------|
|      |               |                               |      |


## 2. System Context

As Conway's Law suggests, our system architecture will directly mirror our team structure. Therefore, our primary System Context diagram shows three systems, each corresponding to one of our teams. The services owned by these teams will live within these system boundaries.

```mermaid
C4Context
    title System Context Diagram reflecting Team Ownership

    Person(creator, "Content Creator", "A user who creates and edits documents. (Internal Consultant or Client)")
    Person(auditor, "Reviewer / Auditor", "A user who reviews, verifies, and audits documents. (Internal Consultant or Client)")

    System_Boundary(c1, "PaperTrail") {
        System(editor_ui, "Editor Experience System", "Owned by Team A. The user-facing application for content creation.")
        System(reviewer_ui, "Reviewer & Audit System", "Owned by Team B. The user-facing application for auditing and verification.")
        System(trust_platform, "Trust Platform", "Owned by Team C. The backend platform providing tamper-proof storage and CI/CD.")
    }

    System_Ext(sharepoint, "SharePoint", "Legacy system for document migration.")
    System_Ext(ad, "Client Active Directory", "External identity provider for client users.")

    Rel(creator, editor_ui, "Creates and edits documents using")
    Rel(auditor, reviewer_ui, "Reviews and verifies documents using")

    Rel(editor_ui, trust_platform, "Stores/versions documents via")
    Rel(reviewer_ui, trust_platform, "Reads documents/audit trails via")

    Rel(editor_ui, sharepoint, "Reads documents from for migration")
    Rel(creator, ad, "Authenticates with")
    Rel(auditor, ad, "Authenticates with")
```

### Users & Actors
- Internal consultants (500)
- Client users (2,000 across 30 organisations)
- Peak usage: end of fiscal quarters

### External Systems & Integrations
- Existing SharePoint (migration source)
- Client Active Directory instances
- *(others TBD)*

### Client Isolation Boundaries
*(To be defined based on team ownership model)*

---

## 3. Service Boundaries (Mapped to Teams)

| Service | Owning Team | Responsibility | Interaction Mode with Other Services |
|---------|-------------|---------------|--------------------------------------|
| | | | |

*Principle: No service exists without a named owning team that can carry its cognitive load.*

---

## 4. Key Architectural Decisions (ADRs)

### ADR-001: *TBD*
- **Context (team/org):**
- **Decision:**
- **Consequences:**

*(Additional ADRs to follow)*

---

## 5. Data Residency & Compliance

### Regulatory Requirements
- FDA 21 CFR Part 11 (electronic signatures)
- SOX compliance
- EU data residency (documents must never leave the EU)

### Tamper-Proof Audit Trail Design
*(TBD)*

### Electronic Signature Approach
*(TBD)*

---

## 6. Migration Strategy

### Principles
- Incremental migration from SharePoint (no big bang)
- Each phase owned by a named team

### Migration Phases

| Phase | Scope | Owning Team | Dependencies |
|-------|-------|-------------|-------------|
| | | | |

---

## 7. Risks & Blind Spots

### Organisational Risks

| Risk | Impact | Mitigation |
|------|--------|------------|
| | | |

### Technical Risks

| Risk | Impact | Mitigation |
|------|--------|------------|
| | | |