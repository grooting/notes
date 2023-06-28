# Designing Data-Intensive Applications

## Reliable, scalable, and maintainable applications
  - Reliability
    - prevent fault from causing failures
        - Fault: one component of system deviate from its spec
        - Failure:  stop providing required service
  - Scalability： keep good performance when load increases
    - distribution of response time
      - median response time: how long users typically have to wait
      - other percentiles
    - horizontal/vertical scaling
    - no magic scaling sauce, depends on access pattern
  - Maintainability: operability, simplicity, and evolvability

  ## Data Models and Query Languages
  - SQL, NoSQL
  - The Object-Relational Mismatch:
    - one-to-many relationship, how to store multi-valued data:
      - put it in separate tables in SQL
      - use databases that support structured datatypes and XML data
      - encode it as JSON/XML document
  - JSON
    - suitable for self-contained document like resume
    - better locality than the multi-table scheme - one query is sufficient
    - one-to-many tree structures
  - why store ID but not text string?
    - consistent
    - ease of updating (the name is stored in only one place, prevent duplicating human-meaningful info &rarr normalization)
    - localization support
  - Document Databases
    - Limitations:
      - difficult to have many-to-many relationships
      - didn't support joins
    - Solutions:
      - the network model: generalization of hierarchical models (one parent, tree structure), could have multiple parents
        - access a record by following access path
        - query is like navigating n-dimensional data space
        - con: querying and updating are complicated and inflexible
      - the relational model
        - a relation(table) is simply a bunch of rows
        - "access paths" are made automatically by query optimizer, not appplication developer

