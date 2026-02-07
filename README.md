# Ai_Post_bot

Ai_Post_bot is an automated tool that uses the GitHub REST API to create and manage posts on GitHub repositories. It leverages LangGraph for orchestrating complex workflows and ensures reliable, repeatable automation.

---

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Configuration](#configuration)
- [Contributing](#contributing)
- [License](#license)

---

## Overview

Ai_Post_bot automates the creation of issues, pull requests, and comments on GitHub using the official REST API. Built with LangGraph, the bot can execute multi-step processes, handle retries, and maintain state across executions.

---

## Features

- **GitHub REST API integration** – Create, update, and delete issues, pull requests, and comments.
- **LangGraph workflow** – Declarative orchestration of tasks with built‑in retry and state management.
- **Configurable triggers** – Run on a schedule, webhook, or manually.
- **Secure authentication** – Uses GitHub Personal Access Tokens (PAT) with fine‑grained permissions.

---

## Installation

```bash
# Clone the repository
git clone https://github.com/your-username/Ai_Post_bot.git
cd Ai_Post_bot

# Create a virtual environment
python -m venv .venv
source .venv/bin/activate   # On Windows use `.venv\Scripts\activate`

# Install dependencies
pip install -r requirements.txt
```

---

## Usage

```bash
# Set the required environment variables
export GITHUB_TOKEN="ghp_your_token_here"
export REPO_OWNER="your-username"
export REPO_NAME="your-repo"

# Run the bot
python main.py
```

The bot reads the configuration file (`config.yaml`) to determine which actions to perform. By default it creates an issue titled “Automated Post”.

---

## Configuration

`config.yaml` example:

```yaml
workflow:
  steps:
    - name: create_issue
      type: github_issue
      params:
        title: "Automated Post"
        body: "This issue was created by Ai_Post_bot."
    - name: add_label
      type: github_label
      params:
        issue_number: 1
        label: "automation"
```

Feel free to extend the workflow with additional LangGraph nodes.

---

## Contributing

1. Fork the repository.
2. Create a feature branch (`git checkout -b feature/your-feature`).
3. Commit your changes (`git commit -m "Add your message"`).
4. Push to your fork (`git push origin feature/your-feature`).
5. Open a pull request.

All contributions should follow the project's coding style and include tests.

---

## License

This project is licensed under the MIT License – see the [LICENSE](LICENSE) file for details.