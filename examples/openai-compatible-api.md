# OpenAI-Compatible API Example

Many LLM providers expose APIs compatible with the OpenAI API format.

A typical configuration contains:

```text
Base URL
API Key
Model ID
```

Example structure:

```python
from openai import OpenAI
import os

client = OpenAI(
    api_key=os.environ["LLM_API_KEY"],
    base_url=os.environ["LLM_BASE_URL"]
)

response = client.chat.completions.create(
    model=os.environ["LLM_MODEL"],
    messages=[
        {
            "role": "user",
            "content": "Hello"
        }
    ]
)

print(response.choices[0].message.content)
```

## Security

Never hard-code API credentials.

Use environment variables such as:

```text
LLM_API_KEY
LLM_BASE_URL
LLM_MODEL
```
