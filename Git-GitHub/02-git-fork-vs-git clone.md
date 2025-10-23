# Difference Between `git fork` and `git clone`

## 🧩 Core Difference

| Command | What It Does | Where It Happens | Relationship to Original Repo |
|----------|---------------|------------------|-------------------------------|
| **`git fork`** | Creates a **copy of someone else’s repository** under **your own GitHub (or GitLab, etc.) account**. | On the **remote server** (e.g., GitHub). | Keeps a **remote link** to the original (you can later sync or make pull requests). |
| **`git clone`** | Creates a **local copy of a repository** (either yours or someone else’s). | On your **local machine**. | Works directly with the repository you cloned; doesn’t create a new one online. |

---

## 🔍 Example

Imagine there’s a public repo:  
`https://github.com/original-author/cool-project`

1. **`Fork`**
   - You click **“Fork”** on GitHub.  
   - GitHub makes a copy:  
     → `https://github.com/your-username/cool-project`
   - This is now **your own version** of the repo on GitHub.

2. **`Clone`**
   - You then run:
     ```bash
     git clone https://github.com/your-username/cool-project
     ```
   - This downloads the forked repo to your **local machine**, allowing you to modify files, commit changes, and push them back.

---

## 🧠 When to Use Each

| Use Case | Recommended Command | Why |
|-----------|--------------------|-----|
| You want to **contribute** to someone else’s public project | `git fork` (then `git clone` your fork) | Forking gives you your own remote copy to work safely and later submit a pull request. |
| You just want to **use or explore** a project locally (no intention to contribute) | `git clone` | No need for a fork; clone directly from the original repo. |
| You’re working on your **own private repo** | `git clone` | You already own it — no need to fork. |
| You want to **experiment** with another repo but keep changes online | `git fork` | Fork keeps a separate copy on GitHub for your experiments. |

---

## ⚙️ Typical Workflow (Contributing to Open Source)

1. Fork the project on GitHub → creates a copy under your account.  
2. Clone your fork:
   ```bash
   git clone https://github.com/your-username/project-name
3. Make changes → commit → push to your fork.
4. Open a Pull Request to the original repo.
   ```bash
   git clone https://github.com/your-username/project-name
