# 🚀 LLM Gateway — Build With LiteLLM
## LiteLLM → the most popular open-source LLM gateway (supports 100+ providers)


# LLM Gateway Cost Example

A minimal Python example using [LiteLLM](https://github.com/BerriAI/litellm) to call `gpt-4o-mini`, display the response, and calculate the cost of the request in USD.

## Requirements

- Python 3.8 or later
- An OpenAI API key

## Setup

Install LiteLLM:

```bash
pip install litellm
```

Set your OpenAI API key as an environment variable.

**PowerShell:**

```powershell
$env:OPENAI_API_KEY = "your-api-key"
```

**macOS/Linux:**

```bash
export OPENAI_API_KEY="your-api-key"
```

## Run

Save the following as `llm_gateway.py` and run it:

```python
from litellm import completion, completion_cost

response = completion(
    model="gpt-4o-mini",
    messages=[{"role": "user", "content": "Write a haiku about AI."}]
)

cost = completion_cost(completion_response=response)

print("Response:    ", response.choices[0].message.content)
print("\nInput tokens: ", response.usage.prompt_tokens)
print("Output tokens:", response.usage.completion_tokens)
print(f"Cost:         ${cost:.8f}")
```

```bash
python llm_gateway.py
```

## Example output

The response, token counts, and cost depend on the model response and current pricing. One example:

```text
Response:     Silent thoughts arise,
Woven through electric dreams,
Mind of code and light.

Input tokens:  14
Output tokens: 19
Cost:         $0.00001350
```

## Notes

- Keep your API key private. Do not commit it to source control.
- The displayed cost is for the individual completion and may vary between runs.

