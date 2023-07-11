Some plugins connect an LLM to an external resource. It's a vulnerability when the plugin accepts free-form text as input. Instead, the plugin should limit what it accepts to parameterized and type-checked inputs.

Potential attackers have significant latitude to construct a malicious request to the plugin. The result could be a wide range of undesired behaviors, including remote code execution.


