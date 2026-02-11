# Ai_Post_bot

Ai_Post_bot is a lightweight automation tool that uses **LangGraph** to orchestrate conversational workflows for creating and publishing content on GitHub. It interacts with the GitHub REST API to create, update, and manage posts directly from the command line or within a CI/CD pipeline.

---

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Architecture](#architecture)
- [Installation](#installation)
- [Usage](#usage)
- [Configuration](#configuration)
- [Contributing](#contributing)
- [License](#license)

---

## Overview

Ai_Post_bot streamlines the process of generating and publishing GitHub posts. By combining LangGraph’s state‑machine workflow capabilities with the GitHub REST API, it enables:

- Automated generation of markdown content using an LLM.
- Seamless creation or update of GitHub issues, pull requests, or wiki pages.
- Customizable workflow steps via a simple configuration file.

---

## Features

- **LangGraph integration** – Define conversational flows with nodes, edges, and state management.
- **GitHub REST API automation** – Create, edit, and delete posts programmatically.
- **CLI interface** – Run workflows from the terminal or as part of CI pipelines.
- **Extensible** – Add new nodes or modify existing ones without changing core logic.

---

## Architecture

```
┌─────────────────────┐
│   User CLI/Trigger   │
└──────────┬───────────┘
           │
           ▼
┌─────────────────────┐
│   LangGraph Workflow │
│  (Node → Edge → Node)│
└──────────┬───────────┘
           │
           ▼
┌─────────────────────┐
│  GitHub REST API     │
│  (Create/Update)     │
└─────────────────────┘
```

Each workflow node can call an LLM, format markdown, or perform an API request. The graph ensures deterministic execution and easy debugging.

---

## Installation

```bash
# Clone the repository
git clone https://github.com/your-username/Ai_Post_bot.git
cd Ai_Post_bot

# Create a virtual environment (optional but recommended)
python -m venv .venv
source .venv/bin/activate   # On Windows use `.venv\Scripts\activate`

# Install dependencies
pip install -r requirements.txt
```

---

## Usage

```bash
# Basic command to run the default workflow
python ai_post_bot.py --config config.yaml

# Example: Generate a new issue
python ai_post_bot.py --config config.yaml --title "New Feature Request"
```

### Configuration

Create a `config.yaml` file with the following structure:

```yaml
github:
  token: "YOUR_GITHUB_TOKEN"
  repo: "owner/repo"
workflow:
  nodes:
    - id: generate_content
      type: llm
      model: gpt-4o
      prompt: "Write a concise markdown post about AI trends."
    - id: publish
      type: github_api
      action: create_issue
      params:
        title: "{{title}}"
        body: "{{generate_content.output}}"
  edges:
    - from: generate_content
      to: publish
```

The placeholders (e.g., `{{title}}`) are replaced with runtime values.

---

## Contributing

1. Fork the repository.
2. Create a feature branch (`git checkout -b feature/your-feature`).
3. Commit your changes and push (`git push origin feature/your-feature`).
4. Open a pull request with a clear description of the changes.

All contributions must pass the test suite and adhere to the project's coding style.

---

## License

This project is licensed under the MIT License – see the [LICENSE](LICENSE) file for details.