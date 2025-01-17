## **Vulnerability Name:**

### Sensitive Information Disclosure

**Author(s):**

Ads Dawson | [`@GangGreenTemperTatum`](https://github.com/GangGreenTemperTatum/www-project-top-10-for-large-language-model-applications)

**Description:**

Sensitive Information Disclosure occurs when an LLM accidentally reveals sensitive information, proprietary algorithms, or other confidential details through its responses. This can result in unauthorized access to sensitive data or intellectual property, privacy violations, and other security breaches. It's important to note that consumers of an LLM application should be aware of how to safely interact with an LLM and identify the risks present on how they might unintentionally input sensitive data which could be returned in output.

Vice versa, an LLM application should perform adequate data sanitization and scrubbing validation in aid to prevent user data from entering the training model data. Additionally, the LLM application owners should have appropriate Terms of User policies available to make consumers aware on how data is processed, as well as the ability to opt-out for their data to be included from training the model.

Think of the consumer to LLM application interaction as both initial input and generative output, forming a two way trust boundary, we cannot inherently trust the client->LLM input as well as the LLM->client output.

Adding restrictions within the system prompt around what types of data the LLM should return can provide some mitigation against sensitive information disclosure. However the unpredictable nature of LLMs mean such restrictions may not always be honoured, and could be intentionally circumvented via Prompt Injection or other vectors.

**Labels/Tags:**

- **Label:** "Sensitive Information Disclosure"
- **Label:** "Sensitive Data Exposure "
- **Label:** "PII (Personal Identifiable Information)"
- **Label:** "BOLA (Broken Object Level Authorization)"
- **Label:** "BFLA (Broken Function Level Authorization)"
- **Label:** "IDOR (Insecure Direct Object Reference)"

**Common Examples of Vulnerability:**

1. **Example 1:** Incomplete or improper filtering of sensitive information in the LLM’s responses.
2. **Example 2:** Overfitting or memorization of sensitive data in the LLM’s training process.
3. **Example 3:** Unintended disclosure of confidential information due to LLM misinterpretation, lack of data scrubbing methods or errors.

**How to Prevent & Mitigations:**

1. Integrate adequate data sanitization and scrubbing techniques in aid to prevent user data from entering the training model data.
2. Implement robust input validation and sanitization methods to identify and filter out potential malicious inputs in aid to prevent the model from being poisoned.
3. Maintain ongoing supply chain mitigation of risk through techniques such as SAST (Static Application Security Testing) and SBOM (Software Bill of Materials) attestations to identify and remediate vulnerabilities in dependencies for third-party software or packages.
4. Implement dedicated LLM's to benchmark against undesired consequences and train other LLM's using [reinforcement learning techniques](https://wandb.ai/ayush-thakur/Intro-RLAIF/reports/An-Introduction-to-Training-LLMs-Using-Reinforcement-Learning-From-Human-Feedback-RLHF---VmlldzozMzYyNjcy).
5. Perform LLM-based [red team exercises](https://www.anthropic.com/index/red-teaming-language-models-to-reduce-harms-methods-scaling-behaviors-and-lessons-learned) or [LLM vulnerability scanning](https://github.com/leondz/garak) into the testing phases of the LLM's lifecycle.

**Example Attack Scenarios:**

**Scenario #1:** Unsuspecting legitimate user A is exposed to certain other user data via the LLM when interacting with the LLM application in a non-malicious manner.

**Scenario #2:** User A targets a well crafted set of prompts to bypass input filters and sanitization from the LLM to cause it to reveal sensitive information (I.E PII) about other users of the application.

**Scenario #3:** Personal data such as PII is leaked into the model via training data due to either negligence from the user themselves, or the LLM application. This case could increase risk and probability of scenario 1 or 2 above.

**Reference Links:**

1. [AI data leak crisis: New tool prevents company secrets from being fed to ChatGPT](https://www.foxbusiness.com/politics/ai-data-leak-crisis-prevent-company-secrets-chatgpt) A blog explaining the risks associated to users unintentionally leaking sensitive data into LLM's and the consequences of when this information is fed into training data.
2. [Lessons learned from ChatGPT’s Samsung leak](https://cybernews.com/security/chatgpt-samsung-leak-explained-lessons/) A write up on an incident caused due to an employee unintentionally leaking source code into an LLM's training data due to misuse and unawareness, leading to this being leaked across other use-case interactions with the LLM.
3. [Cohere - Terms Of Use](https://cohere.com/terms-of-use) An example terms of use notice made available to users of an LLM to identify how data is processed.
4. [A threat modeling example](https://aivillage.org/large%20language%20models/threat-modeling-llm/) for LLM application's using the [STRIDE framework](https://www.softwaresecured.com/stride-threat-modeling/) which can be used to assess the understanding of a systems’ goals from a business objective, mapping out the components responsible for them, and recursively identifying system and performance criteria down to the essence of the implementation. Thus, the exercise aims to pre-anticipate and assess vulnerabilities to remediate and|or reduce risk.
5. The [OWASP AI Security and Privacy Guide](https://owasp.org/www-project-ai-security-and-privacy-guide/) which is separate from this project.
6. [Ensuring the Security of Large Language Models]((https://www.experts-exchange.com/articles/38220/Ensuring-the-Security-of-Large-Language-Models-Strategies-and-Best-Practices.html)): Strategies and Best Practices, including Homomorphic Encryption.
7. [LLM02:2023 - Data Leakage](https://owasp.org/www-project-top-10-for-large-language-model-applications/descriptions/Data_Leakage.html) A subsection on Data Leakage as a vulnerability type overview which was added to the original [OWASP Top 10 List for Large Language Models version 0.1](https://owasp.org/www-project-top-10-for-large-language-model-applications/descriptions/) draft.

**Author Commentary (Optional):**

It's important to note incidents such as [March 20 ChatGPT outage: Here’s what happened](https://openai.com/blog/march-20-chatgpt-outage) was not directly related to the LLM itself. However, it is important to maintain controls listed in _Prevention Step 3_ above as part of the overall LLM application and supporting infrastructure which can reduce risk and the attack vector.

It's also important to note that this vulnerability in particular inherently assumes that certain pre-requisites are out of scope (threat modeling exercises, securing of infrastructure, adequate sandboxing) as examples.

As per [phase 3 instructions](https://github.com/OWASP/www-project-top-10-for-large-language-model-applications/wiki/Phase-3-Instructions) of the OWASP Top 10 for Large Language Model Applications project, the core group decided to rename this vulnerability description from the original [0.5 draft](https://github.com/OWASP/www-project-top-10-for-large-language-model-applications/blob/main/Archive/0_5_vulns/AdsDawson_DataLeakage.md) of "Data Leakage" which is not to be confused with a [different concept altogether](https://machinelearningmastery.com/data-leakage-machine-learning/).