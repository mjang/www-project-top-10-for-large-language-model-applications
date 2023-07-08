Improper permission handling happens when authorization is not tracked between plugins. This can allow a malicious actor to use a LLM to set up:
- Indirect prompt injection
- Malicious plugins
- Similar malicious methods

Depending on available plugins, the consequences may include:
- Improper privilege escalation
- Loss of confidentiality
- Remote code execution
