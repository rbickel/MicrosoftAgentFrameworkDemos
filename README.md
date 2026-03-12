# Microsoft Agent Framework — Demos & Notebooks

A hands-on collection of Jupyter notebooks showcasing the **Microsoft Agent Framework** for Python.
Each demo is self-contained — install the dependencies, set a few environment variables, and run the cells to see agents in action.

> **New here?** Pick a notebook from the table below, open it in VS Code or JupyterLab, and follow the step-by-step cells.
> More demos will be added over time — contributions and suggestions are welcome!

---

## Table of Contents

| # | Notebook | Topic | Key Concepts |
|---|----------|-------|--------------|
| 1 | [Sequential Workflow Demo](#1-sequential-workflow-demo) | Multi-agent sequential orchestration | `SequentialBuilder`, local agents, event streaming |

---

## Demos

### 1. Sequential Workflow Demo

| | |
|---|---|
| **Notebook** | [`sequential_workflow_demo.ipynb`](sequential_workflow_demo.ipynb) |
| **Difficulty** | Intermediate |
| **Estimated time** | 15–20 min |

**What it does:** Chains two local agents in sequence to plan a trip and produce a structured todo list from the results.

- **Agent 1 — Itinerary Planner** receives a travel prompt and produces a structured day-by-day itinerary.
- **Agent 2 — Todo List Creator** reads the itinerary and converts each stop into a formatted todo-list output.

The notebook walks through installing dependencies, configuring Azure credentials, defining both agents, wiring them with `SequentialBuilder`, and streaming execution events in real time.

**Concepts covered:**

- Defining agents with `Agent` + `AzureOpenAIResponsesClient`
- Sequential orchestration with `SequentialBuilder`
- Real-time workflow event streaming
- Multi-agent conversation context passing

**Prerequisites:**

- Python 3.10+
- An Azure AI Foundry project endpoint
- Azure CLI login (`az login`) or another credential supported by `DefaultAzureCredential`
- A `.env` file with `AZURE_AI_PROJECT_ENDPOINT` (see notebook for details)

---

## Prerequisites (all demos)

| Requirement | Details |
|-------------|---------|
| **Python** | 3.10 or later |
| **Azure subscription** | Required for Azure AI Foundry and Azure OpenAI resources |
| **Azure CLI** | Logged in (`az login`) — used by `DefaultAzureCredential` |
| **VS Code** | Recommended, with the Jupyter and Python extensions installed |

Each notebook lists its own pip dependencies in an early cell and installs them automatically.

---

## Getting Started

```bash
# 1. Clone the repo
git clone https://github.com/<your-org>/MicrosoftAgentFrameworkDemos.git
cd MicrosoftAgentFrameworkDemos

# 2. Create a virtual environment (recommended)
python -m venv .venv
.venv\Scripts\activate   # Windows
# source .venv/bin/activate  # macOS / Linux

# 3. Create a .env file with your Azure configuration
echo AZURE_AI_PROJECT_ENDPOINT=https://<resource>.services.ai.azure.com/api/projects/<project> > .env

# 4. Open any notebook and run the cells
code sequential_workflow_demo.ipynb
```

---

## Repository Structure

```
MicrosoftAgentFrameworkDemos/
├── README.md                          ← You are here
├── sequential_workflow_demo.ipynb     ← Demo 1: Sequential multi-agent workflow
├── .env                               ← Your Azure config (not committed)
└── LICENSE
```

---

## Adding a New Demo

1. Create a new `.ipynb` notebook in the repo root.
2. Include a markdown cell at the top with an overview, architecture diagram, and key concepts.
3. Add a dependency-install cell so the notebook is self-contained.
4. Update this README — add a row to the [Table of Contents](#table-of-contents) and a new section under [Demos](#demos).

---

## License

See [LICENSE](LICENSE) for details.
