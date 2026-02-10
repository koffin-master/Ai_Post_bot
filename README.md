# Ai_Post_bot

**Ai_Post_bot** is an AI‑powered automation tool that uses LangGraph to orchestrate conversational logic and the GitHub REST API to automatically create, update, and manage posts (issues, comments, or releases) in GitHub repositories.

---

## Features

- **LangGraph integration** – Define complex AI workflows and state transitions with ease.
- **GitHub REST API automation** – Programmatically create, edit, and close GitHub posts.
- **Configurable prompts** – Tailor the AI output to match your repository’s style and guidelines.
- **Secure authentication** – Uses a personal access token (PAT) stored in environment variables.
- **Extensible architecture** – Add new actions or modify existing ones without touching core logic.

---

## Installation

```bash
# Clone the repository
git clone https://github.com/<your-username>/Ai_Post_bot.git
cd Ai_Post_bot

# Create a virtual environment (recommended)
python -m venv .venv
source .venv/bin/activate   # On Windows use `.venv\Scripts\activate`

# Install dependencies
pip install -r requirements.txt
```

---

## Configuration

Create a `.env` file at the project root:

```
GITHUB_TOKEN=ghp_XXXXXXXXXXXXXXXXXXXX
REPO_OWNER=your-username
REPO_NAME=your-repo
```

`GITHUB_TOKEN` must have `repo` scope for full access.

---

## Usage

```bash
# Run the bot with a predefined prompt
python ai_post_bot.py --prompt "Draft a release note for version 2.0"
```

The script will:

1. Use LangGraph to process the prompt and generate content.
2. Call the GitHub REST API to create a new issue or comment with the generated text.
3. Log the result to the console.

For advanced usage, edit the `config.yaml` file to customize the workflow or add new actions.

---

## Contributing

Pull requests are welcome. Please open an issue first to discuss major changes. Follow the existing coding style and include tests for new features.

---

## License

MIT © 2026

---