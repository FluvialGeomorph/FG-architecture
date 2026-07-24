# Authority model

## Boundaries

- Humans authorize scope, consequential choices, scientific acceptance, engineering approval, releases, deployments, and cross-repository changes.
- `FG-architecture` is authoritative for maintained organization roles, declared relationships, and the FluvialGeomorph context standard.
- Each member repository is authoritative for its implementation, tests, local architecture, release state, and deployment configuration.
- Accepted ADRs are authoritative for the decisions they record until superseded.
- Schemas are authoritative for documented structural contracts.
- Workflows govern repeatable procedure, not system behavior.
- Checkpoints describe current resumable state and never override durable design.
- Conversations and session history are non-authoritative.

## Precedence

For intent and documentation:

1. Current human direction and applicable policy
2. Latest accepted ADR for its decision
3. Maintained goals and current architecture for their domains
4. Exact schema or interface contract
5. Maintained workflow
6. Cross-repository feature design
7. Current checkpoint
8. Historical records and conversation

Apply this ordering within each artifact's stated domain: for example, architecture cannot redefine an exact schema field, and a workflow cannot redefine a capability boundary. A higher item supplies constraints rather than silently taking over another artifact's role.

Code, tests, and configuration provide evidence of actual behavior. When they conflict with maintained intent, do not silently choose one: classify the discrepancy as drift, determine whether implementation or documentation should change, and obtain human approval when the resolution is consequential.

## Cross-repository changes

Organization records can describe a member repository but cannot mutate it or replace its local authority. Follow the [cross-repository workflow](../workflows/cross-repository-change.md) and secure explicit scope for every repository to be changed.
