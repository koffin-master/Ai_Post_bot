# Ai_Post_bot

Ai_Post_bot is an automated bot that uses the GitHub REST API to create, update, and manage repository posts. The bot leverages **LangGraph** for orchestrating complex conversational flows and decision logic, enabling intelligent content handling and streamlined workflow automation.

---

## Table of Contents
- [Overview](#overview)
- [Key Features](#key-features)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Configuration](#configuration)
- [Usage](#usage)
- [License](#license)

---

## Overview
Ai_Post_bot automates interactions with GitHub repositories through the REST API. It can:
- Create new issue or pull request posts.
- Edit existing posts based on predefined triggers.
- Delete or close posts when conditions are met.
- Log actions and responses for audit purposes.

LangGraph powers the decision-making engine, allowing the bot to adapt its behavior based on contextual information and user input.

---

## Key Features
- **GitHub REST API Automation** – Direct integration with GitHub for full CRUD operations on posts.
- **LangGraph Integration** – Structured workflow management and conversational logic.
- **Configurable Triggers** – Set conditions for automated actions via a simple YAML file.
- **Logging & Auditing** – Detailed logs of every API call and decision taken by the bot.
- **Extensible Architecture** – Easily add new handlers or modify existing ones.

---

## Prerequisites
- Python 3.10 or newer
- A GitHub personal access token with `repo` scope
- `pip` package manager

---

## Installation
```bash
# Clone the repository
git clone https://github.com/your-username/Ai_Post_bot.git
cd Ai_Post_bot

# Create and activate a virtual environment
python -m venv venv
source venv/bin/activate   # On Windows use: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

---

## Configuration
Create a `.env` file in the project root with the following content:

```
GITHUB_TOKEN=your_github_token
REPO_OWNER=repo_owner_username
REPO_NAME=repo_name
```

Optionally, customize the trigger rules in `config.yaml`:

```yaml
triggers:
  - type: new_issue
    action: close
    conditions:
      - label: "wontfix"
```

---

## Usage
```bash
# Run the bot
python ai_post_bot.py
```

The bot will start listening for events defined in `config.yaml` and perform actions automatically. Logs are written to `logs/ai_post_bot.log`.

---

## License
This project is licensed under the MIT License – see the [LICENSE](LICENSE) file for details.