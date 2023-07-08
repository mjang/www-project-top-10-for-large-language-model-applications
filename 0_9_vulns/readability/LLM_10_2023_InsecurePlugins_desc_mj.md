Some plugins connect an LLM to an external resource. It's a vulnerability when it accepts free-form text as input. Instead, it should accept parameterized and type-checked inputs.

Potential attackers have significant latitude to construct a malicious request to the plugin. The result could be a wide range of undesired behaviors, including remote code execution.


