


### Data Transfer Object (DTO)

A **DTO** is a flat structure of data used to move information around efficiently, stripped of business logic and internal complexities.

- Entities mostly contain simple members (properties).
- A DTO is a plain object that is used to transfer data between different layers or components of an application, often across network boundaries.
- DTOs are usually lightweight, containing only the necessary fields to transfer data, without any additional logic or behavior.

**Purpose**
Transfer data between layers or services, optimizing for performance (reducing calls) and security (hiding sensitive data).

**Behavior**
Generally **anemic** (no business logic), containing only properties (getters and setters).

**Persistence**
Not typically persisted directly; mapped to/from Entities or Aggregates.

**Context** 
Application, API, or presentation layers.

### Entity

An **Entity** is a core business object that has a unique identifier and encapsulates both data and behavior, representing a real-world concept within your application's domain.

- Entities may have its own simple members (properties). An entity can have complex members and a Data Transfer Object (DTO) maybe the type of one of the properties. 
- Entities may include additional methods or behaviors for performing domain-specific operations and business rules.
- Entities may have relationships with other entities, such as one-to-one, one-to-many, or many-to-many relationships, which can be expressed through fields or associations.

**Purpose**
Represents a distinct object in the business domain with a unique identity (ID) that persists over time.

**Behavior**
Rich behavior; contains business logic and methods related to its data and functionality.

**Persistence**
Often maps directly to a database table or collection, managed by an ORM (Object-Relational Mapper).

**Context**
Domain or data access layers.

### Aggregates

- Aggregates may have its own simple members (properties). An aggregate can have complex members.  They data type on those members could be a Data Transfer Object (DTO) or an Entity. 

**Purpose**
A cluster of related entities and value objects treated as a single, cohesive unit to enforce business invariants (consistency rules).

**Behavior**
The **Aggregate Root** (which is an Entity itself) is responsible for all actions and logic within the boundary, ensuring all changes are consistent.

**Persistence**
Persisted as a whole unit, usually through a single repository. External objects reference the Aggregate Root by ID only, not by object reference.

**Context**
Domain layer (a core building block of Domain-Driven Design).