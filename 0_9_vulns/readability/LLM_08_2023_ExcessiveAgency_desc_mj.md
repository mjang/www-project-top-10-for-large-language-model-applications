Agency is how a prompt interfaces with other systems. Excessive Agency happens when an LLM runs risks without verification or confirmation. 

Developers may set up interfaces with external systems as:
- Hard-wired by the system developer as part of a chain
- Delegated to a LLM agent to determine the most appropriate action

Without limits, excessive agency could lead to undesirable results. This is independent of the root cause, including:

- Hallucinations
- Direct/indirect prompt injections
- Malicious plugins
- Poorly-engineered prompts
- A poorly-performing model

We should not trust LLMs to self-police or self-restrict, just as we do not trust client-side validation in webapps. To prevent excessive agency, We need to embed controls in relevant APIs and plugins called by the LLM.
