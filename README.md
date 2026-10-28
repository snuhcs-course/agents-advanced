# Deep Agents Practice Lab

English Jupyter notebook that walks through the [Deep Agents overview Core capabilities](https://docs.langchain.com/oss/python/deepagents/overview#core-capabilities) using the self-hosted SDK.

**Model:** `openrouter:openai/gpt-6-sol`  
**Secret:** `OPENROUTER_API_KEY` only (no Tavily)

## Requirements

- **Python 3.11+** on Mac or Windows (`deepagents` does not support 3.10 or older)
- OpenRouter API key
- Jupyter / VS Code / Cursor notebook support

## Setup

### macOS / Linux

```bash
cd deep-agents-lab
python3.13 -m venv .venv   # or python3.11 / python3.12
source .venv/bin/activate
pip install -r requirements.txt
cp .env.example .env
# Edit .env and paste OPENROUTER_API_KEY=...

jupyter notebook deep_agents_practice.ipynb
# or: jupyter lab deep_agents_practice.ipynb
```

### Windows (PowerShell)

```powershell
cd deep-agents-lab
py -3.13 -m venv .venv    # or: py -3.11 -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
copy .env.example .env
# Edit .env in Notepad and paste OPENROUTER_API_KEY=...
# Prefer UTF-8 (Notepad: Save with encoding UTF-8)

jupyter notebook deep_agents_practice.ipynb
```

### Windows (cmd.exe)

```bat
cd deep-agents-lab
py -3.13 -m venv .venv
.venv\Scripts\activate.bat
python -m pip install -r requirements.txt
copy .env.example .env
jupyter notebook deep_agents_practice.ipynb
```

In VS Code / Cursor: select the `.venv` interpreter as the notebook kernel before running cells.

## Cross-platform notes

| Topic | Guidance |
|-------|----------|
| Working directory | Setup cells locate `deep-agents-lab` via `AGENTS.md` + `skills/` and `chdir` there. Still best to open the notebook from that folder. |
| Virtual paths | Agent paths like `/workspace/hello.md` are **POSIX-style virtual paths** (`FilesystemBackend(virtual_mode=True)`). Do not rewrite them as `C:\...`. |
| `.env` | Use UTF-8. Avoid a UTF-8 BOM if the key fails to load on Windows. |
| Console Unicode | Setup sets `PYTHONUTF8=1` when possible so printed answers don’t garble on older Windows consoles. |
| Interpreter (Part 2.4) | Optional; the cell already `try/except`s if QuickJS bits are unavailable. Core lab does not require sandboxes/Docker. |
| Line endings | LF or CRLF both fine for `.py` / `.env` / notebook JSON. |

## Notebook map

| Part | Topic |
|------|--------|
| 0 | Setup |
| 1 | Harness overview + quickstart |
| 2 | Execution environment (tools, filesystem, permissions, interpreter, streaming) |
| 3 | Context management (skills, memory, offloading, prompt caching note) |
| 4 | Delegation (todos, subagents) |
| 5 | Steering (human-in-the-loop) |
| 6 | **Assignment** — build a small agent; submit notebook output + `workspace/submission.md` |

## Docs

- [Overview](https://docs.langchain.com/oss/python/deepagents/overview)
- [Customization](https://docs.langchain.com/oss/python/deepagents/customization)
- [Quickstart](https://docs.langchain.com/oss/python/deepagents/quickstart)
