# llm-output

A personal study of **[Pydantic](https://docs.pydantic.dev/)** for getting structured, validated output from LLMs, based on the lessons of the [DeepLearning.AI](https://www.deeplearning.ai/short-courses/) short course *Pydantic for LLM Workflows*.

The course examples were adapted to use **Anthropic's Claude** models through the official `anthropic` SDK, [Instructor](https://python.useinstructor.com/) and [Pydantic AI](https://ai.pydantic.dev/).

## Notebooks

All notebooks live in [src/llm_output/](src/llm_output/):

| Notebook | Topic |
| --- | --- |
| [model_basics.ipynb](src/llm_output/model_basics.ipynb) | Pydantic basics: defining models, validating user input, handling `ValidationError` |
| [validating_responses.ipynb](src/llm_output/validating_responses.ipynb) | Validating LLM responses against a Pydantic model and retrying on failure |
| [pydantic_api_call.ipynb](src/llm_output/pydantic_api_call.ipynb) | Passing Pydantic models directly to the API (Instructor, Pydantic AI, structured outputs) |
| [tool_calling.ipynb](src/llm_output/tool_calling.ipynb) | Using Pydantic models to define and validate tool calls |

## Requirements

- [Python 3.14+](https://www.python.org/downloads/)
- [uv](https://docs.astral.sh/uv/getting-started/installation/)
- An [Anthropic API key](https://console.anthropic.com/)

## Getting started

### 1. Get your own copy of the project

**Option A — Fork (easiest):** click **Fork** at the top of this repository's GitHub page, then clone your fork:

```bash
git clone https://github.com/<your-username>/llm-output.git
cd llm-output
```

**Option B — Clone and push to a new repository of your own:**

1. Create a new, empty repository on GitHub (no README, `.gitignore` or license), e.g. `llm-output`.
2. Clone this project and point it to your repository:

   ```bash
   git clone <this-repository-url> llm-output
   cd llm-output
   git remote rename origin upstream
   git remote add origin https://github.com/<your-username>/llm-output.git
   git push -u origin main
   ```

   `upstream` keeps a link to the original project, so you can pull future updates with `git pull upstream main`.

### 2. Install the dependencies

```bash
uv sync
```

This creates a `.venv` folder with all the dependencies, including `ipykernel` for running the notebooks.

### 3. Configure your API key

Create a `.env` file in the project root:

```env
ANTHROPIC_API_KEY=your-api-key-here
```

The notebooks load it with `python-dotenv`. The `.env` file is already in `.gitignore`, so your key won't be committed.

### 4. Run the notebooks

Open the project in VS Code (or Jupyter), open any notebook in `src/llm_output/` and select the `.venv` interpreter as the kernel. Or run Jupyter Lab through uv:

```bash
uv run --with jupyter jupyter lab
```

## Credits

The lesson content and exercises come from DeepLearning.AI's *Pydantic for LLM Workflows* course. This repository holds my notes and adaptations for study purposes only.
