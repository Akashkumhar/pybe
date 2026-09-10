# PyBe MERN App

PyBe is a scenario-driven Python learning prototype built from the supplied PRD and breakdown document. It has no login flow for now.

📚 View the project wiki: [WIKI.md](WIKI.md)

## Features

- **Scenario Browser & AI Mentor**: Difficulty, concept, and search filters with learner reasoning, abstraction mapping, conversational prompts, Python construct generation, prompt scoring, and reflection capture.
- **🎭 Interactive OOP Story Lab**:
  - **Buddy's Magic Pet Shop (Encapsulation Adventure)**: 4-part animated storyline teaching Python OOP encapsulation (private variables `__health`, `@property`, validated setters, defensive methods) with interactive pet care, tamper defense, and graduation ceremony.
  - **Hero Academy (Inheritance Adventure)**: Multi-character superhero training ground explaining OOP inheritance, parent classes, overriding, and custom hero builders.
  - **Pyodide WebAssembly Python Engine**: Live in-browser Python execution with real-time output and instant feedback.
  - **Companion Python Test Suite**: Standalone terminal-runnable reference scripts and unit tests verifying encapsulation domain invariants.
- **Learner Dashboard**: Progress analytics, prompt maturity, concept mastery, misconceptions, and recent sessions.
- **Roadmap View**: Covering V0 through V3 staged product evolution.
- **JSON-file backed API** with seedable scenarios.

## Tech Stack

- **Storage**: JSON file store (`server/src/data/db.json`)
- **Backend**: Express + Node.js
- **Frontend**: React + Vite + Lucide icons + Canvas Confetti
- **In-Browser Python**: Pyodide (WebAssembly)
- **Styling**: Vanilla CSS (Rich cartoon rigs + sleek learning dashboard)

## Prerequisites

- Node.js 18+

## Setup

1. Install dependencies:

```bash
npm run installAll
```

2. Configure the server environment:

```bash
cp server/.env.example server/.env
```

The default values work for local development.

3. Seed sample data:

```bash
npm run seed
```

4. Run the app:

```bash
npm run dev
```

5. Run the companion Python reference & unit tests:

```bash
python -m unittest python_reference/test_pet_shop.py
python python_reference/pet_shop_puppy.py
```

## Notes

The AI behavior in this prototype is deterministic and local. The abstraction mapper, prompt evaluator, and Python construct generator use rule-based logic so you can run everything without external AI keys. Later phases can replace those services with OpenAI, RAG, or TinyLLM components.

Learning data is stored in `server/src/data/db.json`. This keeps the prototype simple and fully local, without MongoDB, Docker, Atlas, or any external database.
