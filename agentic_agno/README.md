# Agentic AI with Agno

Autonomous AI agents, tool-calling workflows, and multi-agent coordination built with the **Agno** framework (formerly Phidata).

---

## 📂 Directory Contents

| Script | Purpose | LLM / Tools Used |
| :--- | :--- | :--- |
| `agent.py` | Travel Assistant Agent capable of live web research | **Groq (`qwen/qwen3-32b`)** + `DuckDuckGoTools` |
| `finance.py` | Investment & Financial Analyst Agent inspecting stock prices and analyst ratings | **Groq (`qwen/qwen3-32b`)** + `YFinanceTools`, `DuckDuckGoTools` |
| `youtube_analyzer.py` | Comprehensive video analyst generating detailed summaries & timestamps | **OpenAI (`gpt-5.2` / GPT-4o)** + `YouTubeTools` |
| `memory.py` | Agent equipped with persistent conversational memory across turns | Session state / Memory stores |
| `team.py` | Multi-agent coordination with specialized sub-agents collaborating on tasks | Multi-agent team orchestration |
| `ui.py` | Interactive web UI / playground interface for testing agents | Agno UI integration |

---

## 🌟 Key Capabilities Demonstrated

1. **Tool Augmented Generation**:
   - Equipping LLMs with external tools (web search, financial data, video metadata) to eliminate hallucinations and retrieve real-time data.
2. **Multi-Model Flexibility**:
   - Seamlessly alternating between **Groq** (ultra-fast inference on open models like Qwen / Llama) and **OpenAI**.
3. **Structured & Tabular Outputs**:
   - Instructing agents to return clean Markdown tables for financial balance sheets, ratios, and comparisons.
4. **Autonomous Video Breakdown**:
   - Ingesting YouTube video URLs, fetching transcript tracks, generating timestamped navigation points, and categorizing content types.

---

## 🚀 Setup & Execution

### 1. Requirements & Environment
Install the Agno framework and tools:
```bash
pip install agno openai groq python-dotenv yfinance duckduckgo-search youtube-transcript-api
```

Create a `.env` file in this directory or in the workspace root with your API keys:
```env
OPENAI_API_KEY=your_openai_api_key_here
GROQ_API_KEY=your_groq_api_key_here
```

### 2. Running the Agents

- **Run Web Search Travel Agent**:
  ```bash
  python agent.py
  ```

- **Run Financial Market Analyst**:
  ```bash
  python finance.py
  ```

- **Run YouTube Video Analyzer**:
  ```bash
  python youtube_analyzer.py
  ```

- **Launch Multi-Agent Team**:
  ```bash
  python team.py
  ```

---

## 💡 Agent Construction Blueprint

```python
from agno.agent import Agent
from agno.models.groq import Groq
from agno.tools.duckduckgo import DuckDuckGoTools
from agno.tools.yfinance import YFinanceTools

agent = Agent(
    model=Groq(id="qwen/qwen3-32b"),
    tools=[YFinanceTools(), DuckDuckGoTools()],
    markdown=True,
    add_datetime_to_context=True,
    description="You are an investment analyst that researches stock fundamentals.",
    instructions=["Use tools whenever possible. Format responses using markdown tables."]
)

agent.print_response("Share MSFT stock price and latest analyst recommendations")
```
