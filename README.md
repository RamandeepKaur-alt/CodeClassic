# CodeClassic – AI-Powered Engineering Project Generator

CodeClassic is an **agentic AI system** that converts a natural-language idea into a structured engineering plan and actionable file-level implementation steps.  
It demonstrates how to orchestrate multiple LLM-powered agents with **LangGraph**, typed state models, and tool-enabled execution.

---

## 📌 Project Category

- AI Agent Engineering Project
- LLM Orchestration System
- AI-Powered Software Planner
- Agentic Workflow System

---

## 🎯 Problem Statement

When developers start a new project, they often have to manually:

- decide project structure,
- break down files and responsibilities,
- define implementation order,
- choose dependencies and architecture.

CodeClassic automates this by generating:

- planning artifacts,
- file breakdowns,
- structured engineering tasks,
- an agent-driven execution pipeline.

---

## 🧠 Core Idea

Given a user prompt, CodeClassic runs an agent workflow that:

1. builds a structured project plan,
2. converts it into implementation tasks,
3. executes tasks in sequence at file level.

This is more than a single LLM call—it is a graph-orchestrated, typed, tool-augmented system.

---

## 🏗 System Architecture

CodeClassic uses a **LangGraph-based multi-agent flow**.

```text
User Prompt
    ↓
Planner Agent
    ↓
Structured Plan
    ↓
Architect Agent
    ↓
Task Plan (file-level implementation steps)
    ↓
Coder Agent (iterative)
    ↓
Generated Project Output
```

### Agent Responsibilities

- **Planner Agent**: Converts natural-language prompt into a typed `Plan`.
- **Architect Agent**: Expands `Plan` into a typed `TaskPlan` with ordered implementation steps.
- **Coder Agent**: Executes each step using file tools (`read_file`, `write_file`, etc.) until completion.

---

## 🧩 Repository Structure

```text
CodeClassic/
│
├── agent/
│   ├── graph.py      # LangGraph nodes, edges, orchestration
│   ├── states.py     # Pydantic data models for plan/task/state
│   ├── prompt.py     # Planner/architect/coder prompts
│   └── tools.py      # File + utility tools for agent execution
│
├── main.py           # CLI entrypoint
├── pyproject.toml    # Project dependencies and metadata
├── uv.lock           # Locked dependency graph
├── .gitignore
└── README.md
```

---

## ⚙️ Tech Stack

### Core

- Python 3.11+
- LangChain
- LangGraph
- Groq LLM
- Pydantic
- python-dotenv

### Model Provider

- **Provider**: Groq Cloud
- **Model**: `openai/gpt-oss-120b`
- **Integration**: `langchain-groq`

### Dependency Management

- `uv`
- `pyproject.toml`
- `uv.lock`

---

## 📦 Dependencies

The project uses (from `pyproject.toml`):

- `groq`
- `langchain`
- `langchain-core`
- `langchain-groq`
- `langgraph`
- `pydantic`
- `python-dotenv`

---

## 🔐 Environment Configuration

Create a `.env` file in the project root:

```env
GROQ_API_KEY=your_api_key_here
```

---

## 🚀 Getting Started

### 1) Install dependencies

```bash
uv sync
```

### 2) Run the application

```bash
uv run python main.py
```

Optional: control LangGraph recursion limit

```bash
uv run python main.py --recursion-limit 100
```

### 3) Provide your prompt

Example prompt:

```text
Build a colorful modern todo app in HTML, CSS, and JS with local storage support.
```

The system prints the final structured state after graph execution.

---

## 🔄 Execution Flow

1. User runs `main.py`.
2. User enters a project prompt.
3. Planner agent returns structured `Plan`.
4. Architect agent builds ordered `TaskPlan`.
5. Coder agent processes each implementation step.
6. Files are generated/updated under a project output directory.
7. Final state is printed to the console.

---

## 🧠 Design Principles Demonstrated

- Agent-based architecture
- Separation of planning and execution
- Structured output enforcement
- Typed state management with Pydantic
- Graph-based workflow orchestration
- Modular code organization
- Tool-augmented LLM execution

---

## 🏗 Engineering Concepts Demonstrated

- Multi-step reasoning workflows
- AI agent orchestration
- Prompt engineering for role-specific agents
- Structured data modeling
- File-level task planning
- LLM + tool integration
- Recursive graph execution control

---

## ✨ Why CodeClassic Is Not "Just a GPT Script"

CodeClassic provides production-style architectural patterns:

- explicit orchestration graph,
- typed intermediate artifacts,
- deterministic phase separation,
- tool-based file operations,
- iterative execution state tracking.

This makes it suitable as a learning project for real-world agent system design.

---

## 🔮 Future Improvements

- Web UI for prompt and output visualization
- Project ZIP export
- Multi-agent collaboration beyond planner/architect/coder
- Automatic full codebase generation with tests
- Deployment-ready scaffolding
- Template selection mode
- Persistent project memory

---

## 📄 License

Add your preferred license (MIT/Apache-2.0/etc.) to formalize usage terms.
