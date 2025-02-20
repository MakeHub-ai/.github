# MakeHub - Fast LLM API with Multi-Provider Arbitrage

Welcome to MakeHub, where we run a production-ready LLM API that’s hosted, very fast, and uses real-time speed and price arbitrage across multiple providers like Together, Fireworks, DeepInfra, Azure, and more. You set your performance needs—minimum throughput and maximum latency—and our API picks the most cost-effective provider for you. We also share open-source examples and state-of-the-art agent research on GitHub.

## What Is This?
Our high-speed API platform:
- Hosts a low-latency LLM API solution that arbitrages between providers (e.g., Together, Fireworks, DeepInfra, Azure).
- Lets you define speed and latency; we select the cheapest provider that delivers - and we create multiple fallbacks in case something goes wrong.
- Offers open-source examples for quick integration.
- Includes free SOTA agent research from our team.

Great for fast chatbot APIs, real-time text generation, cost-efficient AI tasks and any agentic task.

---

## Getting Started
To use our fast LLM API endpoints:
1. Get an API Key: Sign up at [https://makehub.ai](https://makehub.ai).
2. Clone Open-Source Examples:
   ```bash
   git clone https://github.com/MakeHub/llm-api-examples.git
   ```
3. Run It: See the Quickstart below.
4. Read Docs: Visit [https://makehub.ai/docs](https://makehub.ai/docs).

## Quickstart
A very simple OpenAI like endpoint, with and optional addition: you can specify performance with `min_throughput` and `max_latency`. Our API arbitrages across providers like Together, Fireworks, DeepInfra, and Azure to meet your requirements at the lowest cost.

### Python
```python
from openai import OpenAI

client = OpenAI(
    api_key="your_api_key",
    base_url="https://api.makehub.ai/v1"
)

# Set performance requirements
extra_query_params = {
    "min_throughput": "50",  # 50 tokens/sec minimum
    "max_latency": "1000"    # 1000ms maximum
}

response = client.chat.completions.create(
    model="meta/Llama-3.3-70B-Instruct-fp16",
    messages=[{"role": "user", "content": "Hello!"}],
    extra_query=extra_query_params  # Arbitrages providers
)

print(response.choices[0].message.content)
```

### TypeScript
```typescript
import OpenAI from "openai";

const client = new OpenAI({
    apiKey: "your_api_key",
    baseURL: "https://api.makehub.ai/v1"
});

// Set performance requirements
const extraQueryParams = {
    min_throughput: "50",  // 50 tokens/sec minimum
    max_latency: "1000"    // 1000ms maximum
};

const response = await client.chat.completions.create({
    model: "meta/Llama-3.3-70B-Instruct-fp16",
    messages: [{ role: "user", content: "Hello!" }],
    extra_query: extraQueryParams  // Arbitrages providers
});

console.log(response.choices[0].message.content);
```

### cURL
```bash
curl -X POST "https://api.makehub.ai/v1/chat/completions" \
  -H "Authorization: Bearer your_api_key" \
  -H "Content-Type: application/json" \
  -d '{
    "model": "meta/Llama-3.3-70B-Instruct-fp16",
    "messages": [{"role": "user", "content": "Hello!"}],
    "extra_query": {
      "min_throughput": "50",
      "max_latency": "1000"
    }
  }'
```

### Output
A fast, cost-optimized response from our very fast LLM API endpoints, routed via the best provider.

## Use Cases
- Chatbots: Build a fast chatbot API for LLMs with provider arbitrage.
- Text Generation: Use our real-time text generation API solution.
- Sequencial agent workflows: Remove friction with users by having faster completion and high completion rate with multiple fallbacks

## Open-Source Resources
Our API is hosted, but we share:
- LLM API Examples: Starter code in Python, TypeScript, etc.
- SOTA Agents: Research agents to experiment with.

## Documentation
See [https://makehub.ai/docs](https://makehub.ai/docs) for:
- API endpoint details
- Performance parameter options
- Provider arbitrage info

## Why Use It?
- No biding to any provider: Arbitrage across Together, Fireworks, DeepInfra, Azure, and more.
- Control: A real-time speed and price arbitrage API you tune.
- Efficiency: A best API for LLM cost optimization.

## Get Involved
- **API Access**: Start at [https://makehub.ai](https://makehub.ai).
- **Feedback**: Open issues on our example repos.

## Contact
- **Website**: [https://makehub.ai](https://makehub.ai)
- **Docs**: [https://makehub.ai/docs](https://makehub.ai/docs)
- **Support**: Email [support@makehub.ai](mailto:support@makehub.ai)
