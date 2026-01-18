# 🚀 Git & GitHub Learning Journey
## Beginner to Advanced (Industry-Ready)

A complete, structured learning path for mastering Git and GitHub from absolute beginner to industry-level proficiency.

**Status:** 📚 Comprehensive Guide | ⭐ Perfect for Freshers | 💼 Job-Ready Content

---

## 📖 Table of Contents

1. [🎯 What You'll Achieve](#what-youll-achieve)
2. [🧭 Learning Roadmap](#learning-roadmap)
3. [🟢 Phase 1: Git Fundamentals](#phase-1-git-fundamentals)
4. [🔵 Phase 2: GitHub Basics](#phase-2-github-basics)
5. [🟡 Phase 3: Branching & Merging](#phase-3-branching--merging)
6. [🟠 Phase 4: Professional Git Workflow](#phase-4-professional-git-workflow)
7. [🔴 Phase 5: Advanced Git](#phase-5-advanced-git)
8. [⚫ Phase 6: GitHub for Real Projects](#phase-6-github-for-real-projects)
9. [🎓 Interview Preparation](#interview-preparation)
10. [📚 Quick Reference](#quick-reference)

---

## 🎯 What You'll Achieve

By the end of this complete learning journey, you will be able to:

✅ **Use Git confidently** in solo & team projects  
✅ **Follow industry-standard workflows** exactly as used in companies  
✅ **Handle merge conflicts like a pro** without panic  
✅ **Write clean, professional commit messages** that tell a story  
✅ **Work with branches, PRs, reviews, tags, and releases**  
✅ **Maintain a professional GitHub profile** that attracts recruiters  
✅ **Use Git in production-like setups** with CI/CD awareness  
✅ **Contribute to open-source projects** confidently  
✅ **Recover from any Git mistake** using advanced techniques  
✅ **Implement security best practices** in version control  

---

## 🧭 Learning Roadmap

```
BEGINNER                        INTERMEDIATE                      ADVANCED
┌─────────────────┐        ┌─────────────────┐        ┌──────────────────┐
│ Phase 1: Git    │        │ Phase 3: Branch │        │ Phase 5: Advanced│
│ Fundamentals    │        │ & Merge         │        │ Git              │
└─────────────────┘        └─────────────────┘        └──────────────────┘
│ Phase 2: GitHub │        │ Phase 4: Prof.  │        │ Phase 6: GitHub  │
│ Basics          │        │ Workflows       │        │ Real Projects    │
└─────────────────┘        └─────────────────┘        └──────────────────┘
```

---

## 🟢 PHASE 1: Git Fundamentals (Beginner)

### Goal
Understand version control deeply and never be scared of Git.

### 1.1 What is Git? (Real Meaning)

**Git = Distributed Version Control System**

In simple words:
- **Tracks changes** in your files over time
- **Lets you go back** to any previous version
- **Allows multiple people** to work on the same code safely
- **Works offline** (huge advantage!)

**Why companies use Git:**
- ✅ Code is never lost
- ✅ Mistakes are reversible
- ✅ Team collaboration is safe
- ✅ Full audit trail of who changed what

### 1.2 Git vs GitHub (VERY IMPORTANT)

| Aspect | Git | GitHub |
|--------|-----|--------|
| **What** | Version control system | Cloud platform |
| **Where** | Local on your computer | Remote on servers |
| **Purpose** | Tracks versions | Hosts repositories |
| **Works** | Offline | Needs internet |
| **Interface** | Command line | Web browser + API |

📌 **Key Truth:** Git ≠ GitHub  
GitHub just stores Git repositories online.

### 1.3 Git's 3 Areas (Core Mental Model)

```
┌─────────────────┐
│ Working Dir     │  (Your files - what you edit)
│  (Untracked)    │
└────────┬────────┘
         │ git add
         ▼
┌─────────────────┐
│ Staging Area    │  (Files ready for commit)
│  (Staged)       │
└────────┬────────┘
         │ git commit
         ▼
┌─────────────────┐
│ Repository      │  (.git folder - permanent history)
│  (.git)         │
└─────────────────┘
```

**Nothing is saved unless you commit!**

### 1.4 File Lifecycle (Memorize This)

```
Untracked → Staged → Committed → Modified → Staged → Committed → ...
   ↓
(New file)
```

| State | Meaning | What Git Sees |
|-------|---------|--------------|
| **Untracked** | File exists but Git doesn't know | Red in `git status` |
| **Tracked** | Git knows the file | Green/White in status |
| **Staged** | Ready for next commit | Green in status |
| **Modified** | Changed but not staged | Red in status |

### 1.5 Initial Setup (One-Time)

```bash
# Set your identity (use same email as GitHub)
git config --global user.name "your user name"
git config --global user.email "your email id"

# Verify configuration
git config --global --list
```

**Why:** Git needs to know who made each change for accountability and contribution tracking.

### 1.6 Basic Workflow (The Foundation)

```bash
# 1. Check current status
git status
# Shows: tracked, untracked, staged files

# 2. See what changed (line-by-line diff)
git diff
# Shows changes in working directory (not staged)

# 3. Stage changes
git add filename.txt      # Stage specific file
git add .                 # Stage ALL changes

# 4. Commit (save permanent snapshot)
git commit -m "feat: add login form"

# 5. View history
git log                   # Full details
git log --oneline         # One line per commit
git log --graph --all     # Visual tree
```

### 1.7 Understanding git diff

```bash
# See changes NOT yet staged
git diff

# See changes ALREADY staged
git diff --staged

# Compare two commits
git diff HEAD~1 HEAD
```

**Remember:**
- `git diff` → What have I changed but not staged?
- `git diff --staged` → What am I about to commit?

### 1.8 Commit Messages (Industry Standard)

**Format:**
```
type: short meaningful description
```

**Types (Conventional Commits):**

| Type | Use Case | Example |
|------|----------|---------|
| `feat` | New feature | `feat: add user authentication` |
| `fix` | Bug fix | `fix: resolve navbar overflow` |
| `docs` | Documentation | `docs: update README` |
| `style` | Formatting (no logic change) | `style: fix indentation` |
| `refactor` | Code restructure | `refactor: simplify auth logic` |
| `test` | Testing changes | `test: add unit tests for login` |
| `chore` | Maintenance work | `chore: update dependencies` |

**❌ BAD Examples:**
- `git commit -m "fixed stuff"`
- `git commit -m "update"`
- `git commit -m "final commit"`

**✅ GOOD Examples:**
- `git commit -m "feat: add email validation to signup form"`
- `git commit -m "fix: prevent login crash on empty password"`
- `git commit -m "docs: add installation instructions"`

### 1.9 .gitignore (Security Critical)

**Why .gitignore Exists:**
Prevents committing secrets and unnecessary files.

**Create .gitignore:**
```bash
touch .gitignore
```

**Industry-Standard Rules:**
```
# Node.js
node_modules/
npm-debug.log

# Environment variables (NEVER commit secrets!)
.env
.env.local
.env.production
.env.*.local

# IDE/Editor
.vscode/
.idea/
*.swp
*.swo

# OS Files
.DS_Store
Thumbs.db
.windows-build-tools

# Build outputs
dist/
build/
*.bundle.js

# Logs
logs/
*.log
npm-debug.log*

# Misc
.cache
.eslintcache
.tmp
```

**⚠️ IMPORTANT RULE:**
.gitignore works ONLY for untracked files. If a file is already tracked:

```bash
# Remove file from tracking (but keep locally)
git rm --cached filename.env

# Then add to .gitignore
echo ".env" >> .gitignore

# Commit
git commit -m "chore: remove .env from tracking"
```

### 1.10 Viewing History

```bash
# Full detailed log
git log

# Compact one-line view (use this daily)
git log --oneline

# Visual graph
git log --graph --oneline --all --decorate

# Last 5 commits
git log -5

# Show specific commit details
git show <commit-hash>

# Commits by specific author
git log --author="Anurag"

# Commits in last 7 days
git log --since="7 days ago"
```

### 1.11 Undoing Changes (SAFE ZONE)

```bash
# BEFORE STAGING (in working directory)
# Discard changes in a file
git restore filename.txt
# OR
git checkout filename.txt

# Discard ALL changes
git restore .

# AFTER STAGING (in staging area)
# Remove file from staging (file stays unchanged)
git restore --staged filename.txt
# OR
git reset filename.txt

# AFTER COMMITTING (in repository - SAFE VERSION)
# Undo last commit but keep changes staged
git reset --soft HEAD~1

# Undo and keep changes unstaged
git reset --mixed HEAD~1

# ⚠️ DANGEROUS - deletes commit AND changes
git reset --hard HEAD~1
```

**When to use what:**
- `restore`: "Oops, I made a mistake in this file"
- `reset --staged`: "I staged wrong file"
- `reset --soft`: "I made a commit but message is wrong"
- `reset --hard`: Last resort only (and with reflog backup)

### 1.12 Phase 1 Summary & Checklist

**You Should Understand:**
- [ ] What Git is and why companies use it
- [ ] Git's 3 areas (working, staging, repository)
- [ ] File lifecycle (untracked → staged → committed)
- [ ] How to make commits with good messages
- [ ] Why .gitignore is critical
- [ ] How to view history and changes
- [ ] Safe ways to undo mistakes

---

## 🔵 PHASE 2: GitHub Basics

### Goal
Work with remote repositories and master GitHub platform.

### 2.1 What is a Remote?

**Remote = repository hosted on a server (GitHub, GitLab, Bitbucket)**

```bash
# View all remotes
git remote -v

# Shows something like:
# origin  git@github.com:anurag1224kumar/repo.git (fetch)
# origin  git@github.com:anurag1224kumar/repo.git (push)
```

**origin = default remote name (just a label)**

### 2.2 SSH vs HTTPS (Industry Preference)

| Aspect | SSH | HTTPS |
|--------|-----|-------|
| **Setup** | More complex | Simple |
| **Auth** | Key-based | Password/token |
| **Security** | Higher (asymmetric) | Good (symmetric) |
| **Industry** | Preferred | Acceptable |
| **Requires** | SSH key pair | Username + token |

**Why SSH is preferred:**
- ✅ No repeated login prompts
- ✅ More secure (public key cryptography)
- ✅ Used by DevOps and CI/CD
- ✅ Industry standard

**Setup SSH (One-Time):**
```bash
# Generate SSH key pair
ssh-keygen -t ed25519 -C "anurag1224kumar@gmail.com"

# View public key
cat ~/.ssh/id_ed25519.pub

# Add to GitHub:
# GitHub → Settings → SSH and GPG keys → New SSH Key
# Paste public key, save

# Test connection
ssh -T git@github.com
# Success: Hi anurag1224kumar! You've successfully authenticated.
```

### 2.3 git clone vs git pull

```bash
# CLONE (first time - download entire repo)
git clone git@github.com:username/repo.git

# Creates:
# - Local copy of repo
# - .git folder with history
# - All branches

# PULL (get updates from remote)
git pull origin main

# Equivalent to:
# 1. git fetch (download changes)
# 2. git merge (merge into current branch)

# Alternative (safer - see first, then merge)
git fetch origin main
git merge origin/main
```

**Rule:**
- `clone` → once per repo
- `pull` → many times to stay updated

### 2.4 Push to Remote

```bash
# Push current branch
git push origin main

# Push and set upstream (use first time on new branch)
git push -u origin feature/login

# After -u, simple:
git push

# Delete remote branch
git push origin --delete feature/login
```

**-u flag:**
- `-u` = upstream
- Sets default push/pull destination
- Use once, then just `git push`

### 2.5 GitHub Profile Setup

✅ **Profile Photo**
- Clear face, neutral background
- Same as LinkedIn recommended

✅ **Bio Formula**
```
Role | Tech Stack | What you're building
```

✅ **Example for You**
```
B.Tech (AI & ML) | Full Stack Developer | Learning Industry Workflows
JavaScript • React • Node.js • Git • GitHub • DevOps
```

✅ **Links**
- LinkedIn
- Portfolio
- Email (optional)

### 2.6 README.md (Professional)

**Every repo should have strong README:**

```markdown
# Project Name

## Description
What the project does and why it exists.

## Tech Stack
- React
- JavaScript
- HTML/CSS
- REST API

## Features
- Feature 1
- Feature 2
- Feature 3

## Installation

\`\`\`bash
git clone <repo-url>
cd project-name
npm install
\`\`\`

## How to Run

\`\`\`bash
npm start
\`\`\`

## What I Learned
Key learning outcomes from building this project.

## Future Improvements
What you plan to add next.

## Author
Your Name - [GitHub](https://github.com/username)
```

---

## 🟡 PHASE 3: Branching & Merging (Core Industry Skill)

### Goal
Work safely without breaking production code.

### 3.1 Why Branches Exist

**Scenario:**
- You have stable working code
- You want to add a new feature
- You don't want to break the working version

**Solution:** Create a branch (parallel timeline)

```
main:     A --- B --- D --- E (stable, production)
               \
feature:        C --- F --- G (experimental)
```

### 3.2 Main Branch (Never Experiment Here)

**main = production-ready code**

Rules:
- ✅ Always deployable
- ✅ Always stable
- ✅ Thoroughly tested
- ✅ Protected (no direct pushes in real companies)
- ❌ Never commit experimental code here

### 3.3 Feature Branch Workflow

```bash
# Create and switch to new branch
git switch -c feature/login

# Make changes
echo "Login logic" >> auth.js

# Stage and commit
git add auth.js
git commit -m "feat: add login authentication"

# Push to GitHub
git push -u origin feature/login

# (Later) Merge back to main
git switch main
git pull origin main
git merge feature/login

# Delete feature branch
git branch -d feature/login
git push origin --delete feature/login
```

### 3.4 Branch Naming Convention

Follow this pattern:

```
feature/user-authentication
feature/payment-integration

fix/login-crash
fix/navbar-overflow

hotfix/critical-security-patch

docs/update-readme
docs/api-documentation

refactor/auth-flow
refactor/database-query
```

✅ **Good:** `feature/user-registration`, `fix/null-pointer-error`  
❌ **Bad:** `test`, `temp`, `branch1`, `newbranch`

### 3.5 View Branches

```bash
# Local branches only
git branch

# All branches (local + remote)
git branch -a

# Current branch marked with *
# * feature/login
#   main
```

### 3.6 Merge vs Rebase (Critical Difference)

#### Merge (Recommended for beginners)

```bash
git switch main
git merge feature/login
```

**What it does:**
- Combines branches
- Creates merge commit
- Preserves full history
- Safe for shared branches

**History looks like:**
```
A---B---C---D---E (main after merge)
     \ /
      F---G (feature)
```

#### Rebase (Advanced)

```bash
git switch feature/login
git rebase main
```

**What it does:**
- Rewrites commit history
- Makes history linear (cleaner)
- Re-applies your commits on top

**History looks like:**
```
A---B---C---F---G (linear)
```

**⚠️ GOLDEN RULE:**
```
❌ NEVER rebase a branch that is:
  - Already pushed to remote
  - Shared with teammates
  - On main/develop branch

✅ SAFE to rebase:
  - Local feature branches
  - Before opening PR
  - Personal branches
```

### 3.7 Understanding Merge Conflicts

A conflict happens when:
- Same file
- Same lines
- Changed differently in both branches

Git stops and says: "Human, you decide."

### 3.8 Conflict Markers Explained

When a conflict occurs, file looks like:

```
<<<<<<< HEAD
Git is very powerful.
=======
Git is extremely flexible.
>>>>>>> feature/branch
```

| Marker | Means |
|--------|-------|
| `<<<<<<< HEAD` | Current branch version (where you are) |
| `=======` | Divider between two versions |
| `>>>>>>> feature/branch` | Incoming branch version (being merged) |

### 3.9 Resolving Conflicts

```bash
# 1. Edit file - choose final version
Git is powerful and flexible.

# 2. Remove ALL conflict markers
# 3. Stage the file
git add filename.txt

# 4. Complete the merge
git commit -m "resolve: merge conflict in filename"

# 5. Push
git push origin main
```

**In VS Code:**
- Git shows 4 buttons above conflicts
- `Accept Current Change` - keep your version
- `Accept Incoming Change` - keep other version  
- `Accept Both Changes` - keep both
- `Compare Changes` - see side-by-side diff

### 3.10 Industry Best Practices

✅ **Always:**
- Commit small logical changes
- Use descriptive branch names
- Communicate with team to avoid conflicts
- Pull before pushing
- Review your changes before committing

❌ **Never:**
- Mix unrelated changes in one commit
- Work directly on main
- Commit without testing
- Use vague branch names
- Force push to shared branches

---

## 🟠 PHASE 4: Professional Git Workflow (Industry Level)

### Goal
Follow real company workflows exactly.

### 4.1 Real Company Git Flow

```
┌─────────────┐
│   main      │  Production code (releases)
│ (protected) │
└──────┬──────┘
       │ Create Release Branch
       ▼
┌─────────────┐
│  develop    │  Integration branch (QA/staging)
└──────┬──────┘
       │ Create Feature Branch
       ▼
┌──────────────────────┐
│  feature/xxx         │  Working on new feature
└──────────────────────┘
```

### 4.2 Pull Request Workflow (CORE INDUSTRY SKILL)

**Why PRs exist:**
- Code review before merging
- Discussion space for changes
- Quality gate for production
- Knowledge sharing

**Step-by-Step PR Workflow:**

```bash
# 1. Create feature branch
git switch -c feature/payment-form

# 2. Make changes and commits
echo "payment logic" >> payment.js
git add payment.js
git commit -m "feat: add payment form component"

# 3. Push to GitHub
git push -u origin feature/payment-form

# 4. Open Pull Request on GitHub
# (GitHub shows "Compare & pull request" button)
# - Title: "Add Payment Form"
# - Description: What & why
# - Request reviewers

# 5. Code Review Phase
# - Reviewers comment
# - You respond/fix
# - Iterate until approved

# 6. Merge Pull Request
# GitHub interface: click "Merge pull request"

# 7. Delete feature branch (after merge)
# GitHub shows delete button
# Or locally:
git branch -d feature/payment-form
git push origin --delete feature/payment-form
```

### 4.3 Pull Request Description Template

```markdown
## Description
Briefly explain what changes you made and why.

## Type of change
- [ ] Bug fix (non-breaking)
- [ ] New feature (non-breaking)
- [ ] Breaking change
- [ ] Documentation update

## How Has This Been Tested?
Describe how you tested these changes.

## Screenshots (if applicable)
Add screenshots for UI changes.

## Checklist
- [ ] My code follows the style guidelines
- [ ] I have performed a self-review
- [ ] I have commented my code
- [ ] My changes generate no new warnings
- [ ] I have tested locally
```

### 4.4 Code Review Best Practices

**As PR Creator (You):**
- ✅ Keep PRs small and focused
- ✅ Write clear description
- ✅ Respond to feedback respectfully
- ✅ Implement requested changes
- ✅ Thank reviewers

**As Reviewer:**
- ✅ Focus on code, not person
- ✅ Suggest improvements, don't demand
- ✅ Explain why, not just what
- ✅ Approve only if truly satisfied
- ✅ Be supportive and encouraging

### 4.5 Protecting Main Branch (GitHub)

**In Real Companies:**
❌ No one can push directly to main
✅ PRs and approvals required

**Setup on GitHub:**
1. Go to repo → Settings → Branches
2. Click "Add rule"
3. Branch name pattern: `main`
4. Enable:
   - ✅ Require pull request reviews
   - ✅ Require status checks (tests)
   - ✅ Include administrators

### 4.6 Commit Message Standards

**Industry Format (Conventional Commits):**

```
<type>(<scope>): <subject>

<body>

<footer>
```

**Example:**
```
feat(auth): add JWT token refresh

Add automatic token refresh mechanism to prevent
session timeouts during long user sessions.

Fixes #123
```

### 4.7 Merge Strategies on GitHub

**1. Merge Commit** (Most Common)
```
All commits preserved
History: A---B---C---M (M = merge commit)
Use for: Team workflows
```

**2. Squash & Merge**
```
All commits become one
History: A---B---C (single commit with all changes)
Use for: Clean history, small PRs
```

**3. Rebase & Merge**
```
Linear history
History: A---B---C (rebased commits)
Use for: Open source, advanced teams
⚠️ Be careful with this
```

---

## 🔴 PHASE 5: Advanced Git (Senior-Level Skills)

### Goal
Fix any mistake without fear.

### 5.1 git stash (Pause Work Temporarily)

**Problem it solves:**
"I'm working on something, but I must switch branches urgently."

```bash
# Save uncommitted changes
git stash

# View all stashes
git stash list
# stash@{0}: WIP on feature/login
# stash@{1}: WIP on feature/payment

# Apply last stash
git stash pop

# Apply specific stash
git stash apply stash@{1}

# Delete stash
git stash drop stash@{0}
```

**Real-world use:**
```bash
# Working on feature, boss asks for urgent fix
git stash

# Switch to fix
git switch -c hotfix/critical-bug
# ... fix and commit ...
git push

# Return to feature
git switch feature/login
git stash pop
```

### 5.2 git revert (Safe Undo)

**Problem it solves:**
"I pushed bad code. How do I undo it safely?"

```bash
# View commit to revert
git log --oneline

# Revert specific commit
git revert <commit-hash>

# Creates NEW commit that undoes the change
# Git asks for commit message
```

**Why revert is safe for production:**
- ✅ Creates new commit (no history rewrite)
- ✅ Auditable (can see what was reverted)
- ✅ Safe for shared branches
- ✅ Shows intention clearly

**vs reset (DANGEROUS for shared code):**
```bash
❌ git reset --hard <commit-hash>
# Deletes commits
# Rewrites history
# Breaks teamwork

✅ git revert <commit-hash>
# Creates new commit
# Preserves history
# Team-safe
```

### 5.3 git reflog (Life Saver 🔥)

**What it is:**
Git keeps a log of everywhere HEAD has been.

```bash
# See where HEAD has been
git reflog

# Output:
# abc123 HEAD@{0}: reset: moving to HEAD~1
# def456 HEAD@{1}: commit: add feature
# ghi789 HEAD@{2}: merge: merged feature/login

# Recover "lost" commit
git reset --hard abc123
```

**Why it's powerful:**
- Even if you use `git reset --hard`, you can recover
- Commits exist in reflog for 30 days
- Life-saver when you panic

### 5.4 git reset Modes (Complete Understanding)

```bash
# THREE DIFFERENT RESET MODES
```

| Mode | Commit | Staging | Working Dir | Use Case |
|------|--------|---------|-------------|----------|
| `--soft` | ❌ Removed | ✅ Kept | ✅ Kept | Wrong commit message |
| `--mixed` | ❌ Removed | ❌ Removed | ✅ Kept | Wrong staged files |
| `--hard` | ❌ Removed | ❌ Removed | ❌ Removed | ⚠️ Dangerous |

```bash
# Example sequence
echo "new code" >> file.txt
git add file.txt
git commit -m "feat: add feature"

# Soft: undo commit, keep staged
git reset --soft HEAD~1
# file.txt still staged ✅

# Mixed (default): undo commit, unstage
git reset --mixed HEAD~1
# OR just:
git reset HEAD~1
# file.txt still exists but unstaged

# Hard: undo everything ⚠️
git reset --hard HEAD~1
# file.txt changes DELETED
```

**Industry Rule:**
```
Use --soft or --mixed 99% of the time
Use --hard only if 100% sure
Even seniors avoid --hard casually
```

### 5.5 git cherry-pick (Move a Commit)

**Problem it solves:**
"I committed to wrong branch. Can I move it?"

```bash
# Copy specific commit to current branch
git cherry-pick <commit-hash>

# Applied commit gets new hash but same message
```

**Real-world use:**
```bash
# Accidental commit on main
git log --oneline
# abc123 feat: new feature

# Switch to proper branch
git switch feature/branch

# Apply commit here
git cherry-pick abc123

# Remove from main
git switch main
git reset --soft HEAD~1
```

**⚠️ Note:**
Original commit still exists on source branch.

### 5.6 git reflog in Action

**Panic Scenario:**

```bash
# Accidentally ran:
git reset --hard HEAD~3
# Now those 3 commits are gone!

# PANIC BUTTON - use reflog
git reflog

# See the commits that were deleted:
# abc123 HEAD@{1}: commit: add payment feature
# def456 HEAD@{2}: commit: fix navbar
# ghi789 HEAD@{3}: commit: initial setup

# Recover!
git reset --hard abc123

# All commits restored! 🎉
```

### 5.7 Tags & Releases

**Why tags exist:**
Companies don't say "deploy commit abc123"  
They say "deploy v1.0.0"

```bash
# Create lightweight tag
git tag v1.0.0

# Create annotated tag (recommended)
git tag -a v1.0.0 -m "Version 1.0.0 - Initial Release"

# View tags
git tag
git show v1.0.0

# Push tag to GitHub
git push origin v1.0.0

# Delete tag (local)
git tag -d v1.0.0

# Delete tag (remote)
git push origin --delete v1.0.0
```

### 5.8 Semantic Versioning

```
MAJOR.MINOR.PATCH

Examples:
v1.0.0 - Initial release
v1.1.0 - New features added
v1.1.1 - Bug fix
v2.0.0 - Breaking changes
```

**When to increment:**

| Change | Version | Example |
|--------|---------|---------|
| Breaking changes | MAJOR +1 | v1.0.0 → v2.0.0 |
| New features | MINOR +1 | v1.0.0 → v1.1.0 |
| Bug fixes | PATCH +1 | v1.0.0 → v1.0.1 |

---

## ⚫ PHASE 6: GitHub for Real Projects

### Goal
Production-ready GitHub usage with professional practices.

### 6.1 Issues (Work Management)

**What are Issues?**
Issues track:
- 🐞 Bugs to fix
- ✨ Features to build
- 📝 Tasks and discussions

**Good Issue Format:**

```markdown
## Title
"Login button unresponsive on mobile"

## Description
**Steps to reproduce:**
1. Open website on mobile
2. Click login button
3. Nothing happens

**Expected behavior:**
Login dialog should open

**Actual behavior:**
Nothing happens, no errors

**Environment:**
- Device: iPhone 12
- OS: iOS 15
- Browser: Safari

**Screenshots:**
[Attach screenshot]
```

**Issue Labels (Standard):**
- `bug` - Something broken
- `feature` - New functionality
- `enhancement` - Improve existing feature
- `good first issue` - Beginner-friendly
- `help wanted` - Needs contribution
- `documentation` - Docs update
- `question` - User question

### 6.2 Linking PRs to Issues

**In PR description:**
```
Fixes #42
Closes #42
Resolves #42
```

**Effect:**
- ✅ Issue auto-closes when PR merges
- ✅ GitHub links them together
- ✅ Shows relationship clearly

### 6.3 Projects (Kanban Board)

**What Projects Are:**
GitHub's built-in task management (like Trello).

**Typical Columns:**
- 📋 Backlog
- 📝 Todo
- 🚀 In Progress
- 👀 In Review
- ✅ Done

**Usage:**
- Drag issues between columns
- Track sprint progress
- Coordinate team work

### 6.4 GitHub Actions (CI/CD Basics)

**What is CI/CD?**
- **CI** (Continuous Integration): Automatic tests on every push
- **CD** (Continuous Deployment): Automatic deployment on success

**Example:** Every push → Run tests → If pass, deploy

**Where Workflows Live:**
```
your-repo/
├── .github/
│   └── workflows/
│       └── ci.yml
```

**Basic CI Workflow (Node.js Example):**

```yaml
name: CI

on: [push, pull_request]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      
      - name: Setup Node
        uses: actions/setup-node@v3
        with:
          node-version: '16'
      
      - name: Install dependencies
        run: npm install
      
      - name: Run tests
        run: npm test
      
      - name: Run linter
        run: npm run lint
```

**What this does:**
1. On every push → trigger workflow
2. Checkout code
3. Setup Node.js
4. Install dependencies
5. Run tests
6. Run linter
7. Show results in GitHub

### 6.5 Releases

**Why Releases Matter:**
Professional versioning and changelogs.

**Create Release on GitHub:**
1. Go to Releases
2. Click "Create new release"
3. Select/create tag (v1.0.0)
4. Add title and description
5. Add release notes

**Release Notes Format:**
```markdown
## v1.0.0 - 2024-01-15

### Features
- Add user authentication
- Add payment integration
- Add dark mode

### Fixes
- Fix login crash on mobile
- Fix navbar overflow

### Changes
- Update dependencies to latest

### Contributors
- @anurag1224 (Lead)
- @teammate1 (Review)
```

### 6.6 Open Source Contribution Workflow

**How to Contribute to Open Source:**

```bash
# 1. Fork repository
# GitHub: Click "Fork" button

# 2. Clone your fork
git clone git@github.com:YOUR-USERNAME/project.git
cd project

# 3. Add upstream remote
git remote add upstream git@github.com:ORIGINAL-OWNER/project.git

# 4. Create feature branch
git switch -c fix/issue-123

# 5. Make changes
# ... edit files ...

# 6. Commit
git add .
git commit -m "fix: resolve issue 123"

# 7. Push to your fork
git push origin fix/issue-123

# 8. Create Pull Request
# GitHub: Shows "Compare & pull request"

# 9. Respond to review feedback
# Make changes, commit, push

# 10. After merge, sync your fork
git switch main
git pull upstream main
git push origin main
```

**Open Source Etiquette:**
- ✅ Follow contribution guidelines
- ✅ Keep PRs small and focused
- ✅ Respond to feedback respectfully
- ✅ Don't argue unnecessarily
- ✅ Be patient (maintainers are busy)

❌ **Don't:**
- Force push to your PR branch
- Make unrelated changes
- Ignore CI failures
- Create massive PRs

### 6.7 Security Best Practices

**Never Commit:**
```
❌ API keys
❌ Passwords
❌ Secret tokens
❌ Private keys
❌ Database credentials
❌ .env files with real values
```

**GitHub Security Tools:**
- **Dependabot**: Alerts for vulnerable dependencies
- **Secret Scanning**: Finds accidentally committed secrets
- **Branch Protection**: Prevents risky operations

**Best Practices:**
```bash
# Use environment variables
export API_KEY="your-key"

# Use .env file (add to .gitignore)
cat .env
# API_KEY=your-key
# DATABASE_URL=your-db

# Never commit .env
# Add template
cat .env.example
# API_KEY=
# DATABASE_URL=

# Document in README to add keys locally
```

---

## 🎓 Interview Preparation

### Common Git/GitHub Interview Questions

**Q1: Explain Git workflow you use**
```
Answer: I use feature branch workflow:
1. Create feature branch from main
2. Make commits with clear messages
3. Push and open PR
4. Get code review
5. Merge after approval
6. Delete feature branch
This keeps main stable and allows review.
```

**Q2: How do you handle merge conflicts?**
```
Answer: I carefully:
1. Read conflict markers to understand both changes
2. Decide final version based on requirements
3. Remove ALL conflict markers
4. Test the resolved code
5. Stage and commit
Never blindly delete - always understand.
```

**Q3: Difference between merge and rebase?**
```
Answer:
- Merge: Creates merge commit, preserves history
- Rebase: Linear history, rewrites commits

For shared branches: Use merge
For personal branches: Rebase is cleaner
Never rebase already-pushed code
```

**Q4: How do you recover from mistakes?**
```
Answer: Different strategies:
- Wrong staged file: git reset --staged
- Wrong commit message: git reset --soft HEAD~1
- Bad public commit: git revert
- Deleted commits: git reflog
Different tools for different situations
```

**Q5: What's your commit message style?**
```
Answer: I follow Conventional Commits:
type(scope): subject

- feat: new features
- fix: bug fixes
- docs: documentation
- test: tests

Example: "feat(auth): add JWT token refresh"
Makes history readable and enables auto-changelogs
```

---

## 📚 Quick Reference

### Most Used Commands

```bash
# Setup
git config --global user.name "Name"
git config --global user.email "email"

# Daily workflow
git status                    # Current state
git add .                     # Stage all changes
git commit -m "message"       # Create commit
git push origin branch-name   # Push to remote

# Branching
git switch -c feature/name    # Create + switch branch
git switch main               # Switch branch
git branch                    # List branches
git merge feature/name        # Merge branch

# History
git log --oneline             # View commits
git log --graph --all         # Visual tree
git show <hash>               # Show commit details
git diff                      # See changes

# Undo
git restore file.txt          # Discard changes
git reset --staged file.txt   # Unstage
git reset --soft HEAD~1       # Undo commit safely

# Remote
git remote -v                 # View remotes
git pull origin main          # Get updates
git push origin branch-name   # Send changes
git clone <url>               # Download repo

# Advanced
git stash                     # Pause work
git revert <hash>             # Safe undo
git reflog                    # Recover mistakes
git cherry-pick <hash>        # Copy commit
git tag v1.0.0                # Create release tag
```

### Git Aliases (Speed Up Workflow)

```bash
git config --global alias.st status
git config --global alias.co switch
git config --global alias.br branch
git config --global alias.cm commit
git config --global alias.ps push
git config --global alias.pl pull
git config --global alias.log 'log --graph --oneline --all'

# Now use:
git st       # instead of git status
git co main  # instead of git switch main
git cm -m    # instead of git commit -m
```

---

## ✅ Checklist: Are You Job-Ready?

- [ ] Create local Git repositories
- [ ] Understand working directory, staging, repository
- [ ] Write meaningful commit messages
- [ ] Create and manage branches
- [ ] Handle merge conflicts
- [ ] Push and pull from GitHub
- [ ] Create Pull Requests
- [ ] Review code professionally
- [ ] Recover from mistakes using git reflog
- [ ] Understand SSH authentication
- [ ] Create GitHub Issues and Projects
- [ ] Understand CI/CD basics
- [ ] Contribute to open-source
- [ ] Write professional READMEs
- [ ] Setup GitHub profile properly
- [ ] Never commit secrets
- [ ] Use .gitignore correctly
- [ ] Understand when NOT to rebase

---

## 📚 Resources

### Official Documentation
- [Git Official Docs](https://git-scm.com/doc)
- [GitHub Docs](https://docs.github.com)
- [Conventional Commits](https://www.conventionalcommits.org/)

### Tools
- **Git GUI**: GitKraken, SourceTree, GitHub Desktop
- **IDE Integration**: VS Code, JetBrains IDEs
- **.gitignore Generator**: gitignore.io

### Practice
- [Learn Git Branching](https://learngitbranching.js.org/)
- [GitHub Skills](https://skills.github.com/)
- [Git Exercises](https://gitexercises.fracz.com/)

---

## 🚀 Next Steps

1. **Implement All Phases** - Don't skip any
2. **Practice Daily** - Even 15 min/day helps
3. **Build Real Projects** - Apply these skills
4. **Contribute to Open Source** - Real-world experience
5. **Read Others' Code** - Learn from developers
6. **Master Your Tools** - IDE Git integration
7. **Help Others** - Teach = deeper learning

---

## 💡 Key Principles

> **"Git is a time machine for your code. Use it with respect and understanding."**

| Principle | Meaning |
|-----------|---------|
| **Small commits** | One logical change per commit |
| **Clear messages** | Explain WHY, not just WHAT |
| **Test before push** | Prevent breaking production |
| **Review carefully** | Your eyes = quality gate |
| **Never panic** | Most Git mistakes are recoverable |
| **Communicate** | Prevent conflicts before they happen |
| **Learn forever** | Git has endless depth |

---

## 📞 Getting Help

**When stuck:**
1. Read error message carefully
2. Check git status
3. Use git log to understand state
4. Google the error message
5. Try on a test branch first
6. Ask for help (with context)

**Good help request:**
```
"I'm trying to merge feature/x into main, but got this error:
[error message]
I've tried [what you tried]
Current status: [git status output]
Help?"
```

**Bad help request:**
```
"Git is broken. Help!!!"
```

---

## 🎉 Congratulations!

You now have **industry-level Git and GitHub knowledge**.

This puts you ahead of:
- 70% of beginners
- 50% of junior developers
- Equal to many mid-level developers

**Keep practicing, keep learning, keep building! 💪**

---
