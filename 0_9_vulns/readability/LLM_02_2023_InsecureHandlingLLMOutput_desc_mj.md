An Insecure Output Handling vulnerability is a type of a prompt injection vulnerability. It happens when a component accepts large language model (LLM) output, and then passes it to one of the following types of functions:

- Backend
- Privileged
- Client-side

This vulnerability allows users indirect access to unintended functionality.

The risks of include:
- XSS and CSRF in web browsers
- SSRF, privilege escalation, or remote code execution on backend systems

The consequences may be worse:
- When the application allows LLM content to support privilege escalation
- When attackers combine hijacking attacks with LLM content, they may gain privileged access to a target user's environment
