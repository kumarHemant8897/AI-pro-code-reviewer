

# 🤖 AI CodeReview Bot

> An intelligent **AI-powered code review robot** built using modern LLM technology to automatically analyze GitHub Pull Requests and provide contextual feedback.

**Made by:** **Hemant Kumar**

---



---

# 🚀 Bot Usage

❗️⚠️
Due to cost considerations, this bot is mainly intended for **testing and learning purposes**.
The demo deployment may have **rate limits or instability**, so **self-hosting is recommended** for production usage.

---

# 📦 Installation

Install the GitHub App:

**[https://github.com/apps/cr-gpt](https://github.com/apps/cr-gpt)**

---

# ⚙️ Configuration

1. Open the **target GitHub repository**
2. Go to **Settings**
3. Click **Secrets and Variables → Actions**
4. Create a new variable:

```
OPENAI_API_KEY = your_openai_api_key
```

For **GitHub Actions integration**, store it inside **Secrets**.

---

# ▶️ Start Using

1. Create a **new Pull Request** →
   The bot will **automatically review the code** and post comments in:

   * PR timeline
   * File changes section

2. Push new commits →
   The bot will **re-review updated files automatically**.

---

# 🤖 Using GitHub Actions

GitHub Marketplace Action:

**[https://github.com/marketplace/actions/chatgpt-codereviewer](https://github.com/marketplace/actions/chatgpt-codereviewer)**

### Steps

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

          # OpenAI usage
          OPENAI_API_KEY: ${{ secrets.OPENAI_API_KEY }}
          OPENAI_API_ENDPOINT: https://api.openai.com/v1
          MODEL: gpt-3.5-turbo

          # Common settings
          LANGUAGE: English
          temperature: 1
          top_p: 1
          max_tokens: 10000
          IGNORE_PATTERNS: /node_modules/**/*,*.md
          INCLUDE_PATTERNS: *.js,*.ts,*.py
```

---

# 🏠 Self-Hosting

```bash
git clone <your-repo>
cd <repo>
cp .env.example .env

npm install
npm install -g pm2
npm run build
pm2 start pm2.config.cjs
```

More details:
[https://probot.github.io/docs/development/](https://probot.github.io/docs/development/)

---

# 🛠️ Development Setup

```bash
# Install dependencies
npm install

# Build project
npm run build

# Run bot
npm run start
```

---

# 🐳 Docker

```bash
# Build container
docker build -t ai-cr-bot .

# Run container
docker run -e APP_ID=<app-id> -e PRIVATE_KEY=<pem-value> ai-cr-bot
```

---

# 🤝 Contributing

Suggestions, improvements, and bug reports are **welcome**.
Feel free to **open an issue or submit a pull request**.

---

# 👨‍💻 Author & Credit

### **Hemant Kumar**

AI Software Engineer | Machine Learning | NLP | Computer Vision

This project is **developed, customized, and maintained by Hemant Kumar**
and inspired by earlier open-source research in AI code review systems.

---

# 📄 License

**ISC License © 2026 Hemant Kumar**

---



