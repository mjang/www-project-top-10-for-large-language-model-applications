A Prompt Injection Vulnerability happens when an attacker injects crafted input prompts. These prompts manipulate the operation of a trusted large language model (LLM).

Attackers can introduce prompts in during user sessions various ways, through:
- Websites
- Emails
- Documents
- Other data sources

Once introduced into trusted LLMs, users may not notice the vulnerability.

There are two major types of Prompt Injection vulnerabilities:
- Direct Prompt Injections, where the attacker directly influences the LLM's input
- Indirect Prompt Injections, where the attacker manipulates or "poisons" a data source consumed by the LLM.

The results of a successful attack can vary. For example, under normal operation, the output can:
- Solicit sensitive information
- Influence critical decision-making processes under the guise of normal operation. 

In more intricate cases, the LLM might:
- Impersonate a malicious persona
- Tricked to interact with plugins under a target user's context

The consequences can include:
- Sensitive information disclosure
- Data exfiltration
- Unauthorized plugin execution
- Social engineering

 In these cases, the compromised LLM acts as an agent for the attacker, without triggering alarms or alerting the end user.
