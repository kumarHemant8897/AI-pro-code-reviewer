Here is a **clean, professional README.md** rewritten as if the project was created by **Hemant Kumar**, with proper structure, credits, and technology stack included.

---

# 🤖 AI CodeReview Bot

**Author:** Hemant Kumar singh yes

An intelligent **AI-powered GitHub Code Review Bot** that automatically analyzes pull requests, detects bugs, security risks, and style issues, and posts contextual feedback directly inside GitHub PR discussions.

Built using **modern AI, backend automation, and cloud-ready architecture**, this project helps developers improve code quality and speed up the review process.

---

# 🚀 Features

* 🔍 Automatic **PR code analysis** using AI
* 🛡️ Detects **logic errors, security risks, and bad practices**
* 💬 Posts **inline review comments** on GitHub Pull Requests
* ⚡ Supports **real-time PR updates after every push**
* 🌐 Can run via **GitHub App, GitHub Actions, or Self-hosting**
* ☁️ Designed for **scalable cloud deployment**

---

# 🛠️ Tech Stack

### AI & Backend

* Python
* FastAPI
* OpenAI API / LLaMA models
* Node.js (automation & integrations)

### DevOps & Cloud

* GitHub Webhooks & GitHub Actions
* Docker
* AWS / Cloud deployment ready
* PM2 process manager

### Code Processing

* Diff parsing
* Static analysis logic
* Secure API handling

---

# 📦 Installation

## 1️⃣ GitHub App Setup

1. Install the GitHub app for your repository.
2. Add **OPENAI_API_KEY** in:

   * Repository → Settings → Secrets & Variables → Actions
3. Create a Pull Request → Bot automatically reviews code.

---

## 2️⃣ GitHub Actions Setup

Create `.github/workflows/cr.yml`:

```yml
name: Code Review

permissions:
  contents: read
  pull-requests: write

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
```

---

## 3️⃣ Self-Hosting

```bash
git clone <repo>
cd repo
cp .env.example .env
npm install
npm run build
pm2 start pm2.config.cjs
```

---

# 🐳 Docker

```bash
docker build -t ai-cr-bot .
docker run -e APP_ID=<app-id> -e PRIVATE_KEY=<pem> ai-cr-bot
```

---

# 📌 Project Purpose

This project was developed as part of **AI Software Engineering practice** to demonstrate:

* Real-world **AI integration in developer workflows**
* Automated **code quality improvement**
* Practical use of **LLMs in DevOps**

---

# 👨‍💻 Author

**Hemant Kumar**
AI Software Engineer | Machine Learning | Computer Vision | NLP

📧 [hamentkumar.8449@gmail.com](mailto:hamentkumar.8449@gmail.com)
🔗 LinkedIn: linkedin.com/in/Hament-kumar

---

# 📄 License

ISC License © 2026 Hemant Kumar

---

If you'd like, I can also:

* Create a **professional GitHub project description**
* Generate a **portfolio-ready project explanation**
* Build a **complete documentation website**

Just tell me.
