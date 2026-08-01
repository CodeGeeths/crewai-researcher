# crewai-researcher

A simple [CrewAI](https://crewai.com) project with **one agent** that researches any topic you give it.

Pass in a topic, and the agent gathers relevant, up-to-date information and writes the results to `report.md`.

## What it does

- Takes a **topic** as input (anything you want researched)
- Uses a single **Senior Data Researcher** agent powered by OpenAI
- Produces a markdown research report in the project root

## Setup

Requires Python 3.10–3.13 and [uv](https://docs.astral.sh/uv/).

```bash
git clone https://github.com/CodeGeeths/crewai-researcher.git
cd crewai-researcher
uv sync
```

Create a `.env` file with your OpenAI API key:

```bash
OPENAI_API_KEY=sk-your-key-here
```

## Usage

Run with the default topic:

```bash
uv run researcher
```

Or pass your own topic:

```bash
uv run researcher "Best cities for remote workers in 2026"
```

You can also use the CrewAI CLI:

```bash
crewai run
```

The output is saved to `report.md`.

## Project structure

```
crewai-researcher/
├── src/researcher/
│   ├── config/
│   │   ├── agents.yaml    # Agent role, goal, and LLM
│   │   └── tasks.yaml     # Research task definition
│   ├── crew.py            # Crew setup
│   └── main.py            # Entry point and inputs
├── pyproject.toml
└── .env                   # Your API keys (not committed)
```

## Customizing

- **Change the topic** — pass it on the command line, or edit the default in `src/researcher/main.py`
- **Change the agent** — edit `src/researcher/config/agents.yaml`
- **Change the task** — edit `src/researcher/config/tasks.yaml`
