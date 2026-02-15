# 🤖 AI CodeReview Bot

An intelligent **AI-powered code review assistant** that automatically analyzes GitHub Pull Requests and provides contextual, human-like feedback using modern Large Language Models (LLMs).

> Built for **learning, experimentation, and real-world automation** in modern software development workflows.

---

## 👨‍💻 Author

**Hemant Kumar**
AI Software Engineer • Machine Learning • NLP • Computer Vision

---

## ✨ Features

* 🔍 Automatic **Pull Request code analysis**
* 💬 Context-aware **review comments on files & PR timeline**
* 🔄 **Re-review on new commits**
* ⚙️ Easy **GitHub Actions integration**
* 🏠 Fully **self-hostable for production**
* 🧪 Designed for **learning, testing, and experimentation**

---

## 🚀 Quick Start

### 1️⃣ Install GitHub App

Install the bot from GitHub:

**[https://github.com/apps/cr-gpt](https://github.com/apps/cr-gpt)**

---

### 2️⃣ Configure Environment

Inside your target repository:

1. Go to **Settings → Secrets and Variables → Actions**
2. Create a new secret:

```
OPENAI_API_KEY = your_openai_api_key
```

> Store the key in **Secrets** when using GitHub Actions.

---

## ▶️ Usage

1. Create a **new Pull Request**
   → The bot automatically reviews code and posts comments in:

   * PR timeline
   * File changes section

2. Push additional commits
   → The bot **re-reviews updated code automatically**.

---

## 🤖 GitHub Actions Integration

Marketplace Action:

**[https://github.com/marketplace/actions/chatgpt-codereviewer](https://github.com/marketplace/actions/chatgpt-codereviewer)**

### Setup Steps

1. Add `OPENAI_API_KEY` to **GitHub Secrets**
2. Create workflow file:

```
.github/workflows/cr.yml
```

### Example Workflow

```yml
name: Code Review

permissions:
  contents: read
  pull-requests: write
  models: true

on:
  pull_request:
    types: [opened, reopened, synchronize]

jobs:
  review:
    runs-on: ubuntu-latest
    steps:
      - uses: anc95/ChatGPT-CodeReview@main
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}

          OPENAI_API_KEY: ${{ secrets.OPENAI_API_KEY }}
          OPENAI_API_ENDPOINT: https://api.openai.com/v1
          MODEL: gpt-3.5-turbo

          LANGUAGE: English
          temperature: 0.7
          top_p: 1
          max_tokens: 4000
          IGNORE_PATTERNS: /node_modules/**/*,*.md
          INCLUDE_PATTERNS: *.js,*.ts,*.py
```

---

## 🏠 Self-Hosting

```bash
git clone <your-repository>
cd <repository>
cp .env.example .env

npm install
npm install -g pm2
npm run build
pm2 start pm2.config.cjs
```

More details:
[https://probot.github.io/docs/development/](https://probot.github.io/docs/development/)

---

## 🛠️ Development Setup

```bash
npm install        # Install dependencies
npm run build      # Build project
npm run start      # Start bot locally
```

---

## 🐳 Docker Support

```bash
# Build container
docker build -t ai-cr-bot .

# Run container
docker run -e APP_ID=<app-id> -e PRIVATE_KEY=<pem-value> ai-cr-bot
```

---

## 🤝 Contributing

Contributions, suggestions, and bug reports are welcome.

* Open an **issue** for discussion
* Submit a **pull request** for improvements

---

## 📄 License

**ISC License © 2026 Hemant Kumar**

---

## ⭐ Support

If you find this project useful, consider **starring the repository** to support future de
