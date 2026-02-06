# Ai_Post_bot

Ai_Post_bot is a lightweight automation tool that posts content to GitHub repositories using the GitHub REST API.  
It leverages **LangGraph** to orchestrate workflow steps, making it easy to extend and maintain.

---

## Features

- **GitHub REST API automation** – Create, update, and delete repository content programmatically.
- **LangGraph integration** – Declarative graph-based workflow for clear task sequencing.
- **Configurable** – Simple YAML/JSON configuration to define target repositories, authentication, and post payloads.
- **Extensible** – Add new nodes to the LangGraph pipeline for custom logic.

---

## Getting Started

1. **Clone the repository**

   ```bash
   git clone https://github.com/your-username/Ai_Post_bot.git
   cd Ai_Post_bot
   ```

2. **Install dependencies**

   ```bash
   pip install -r requirements.txt
   ```

3. **Configure the bot**

   Edit `config.yaml` to set:

   - `github_token` – Personal access token with repo scope.
   - `target_repo` – Repository to post to.
   - `post_content` – Content to create or update.

4. **Run the bot**

   ```bash
   python main.py
   ```

---

## Usage

```bash
python main.py --config config.yaml
```

The script will:

1. Read the configuration.
2. Execute the LangGraph workflow.
3. Use the GitHub REST API to create or update the specified file.

---

## Development

- **LangGraph**: See the [LangGraph documentation](https://langgraph.org/) for adding new nodes.
- **Testing**: Run `pytest` to execute unit tests.
- **Linting**: `flake8 .` ensures code quality.

---

## License

MIT License – see [LICENSE](LICENSE) for details.