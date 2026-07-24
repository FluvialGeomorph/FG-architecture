# Agentic context model

```text
task prompt
    -> applicable AGENTS.md
        -> conditional context routes
            -> current repository and Git evidence
                -> implementation
                    -> verification
                        -> documentation promotion
                            -> checkpoint only when resumable state remains
```

`AGENTS.md` contains concise standing rules and conditional routes. `/dev` contains durable knowledge, governance, and operational state. The conversation contains temporary task reasoning. Important outcomes must move from the conversation into the correct durable artifact before completion.

New tasks do not automatically inherit prior conversation reasoning. A checkpoint retains only useful resumable state: objective, completed and remaining work, verification, risks, and the next action. It is not a transcript.

`FG-architecture/AGENTS.md` does not automatically govern sibling repositories because Git repositories and instruction scopes remain independent. A cross-repository task must explicitly begin with organization context, then load the applicable instructions and evidence from every repository in scope. Participating repositories should gradually adopt their own root `AGENTS.md` files that route to their local durable context and reference this standard where appropriate.
