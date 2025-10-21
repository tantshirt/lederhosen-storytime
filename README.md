# Lederhosen Story Time - Team Collaboration Guide

A collaborative storytelling project where team members contribute humorous sentences to build a creative narrative incorporating German vocabulary. This project teaches Git branching, merging, conflict resolution, and Pull Request workflows.

---

## Table of Contents
1. [Project Overview](#project-overview)
2. [Repository Contents](#repository-contents)
3. [Getting Started](#getting-started)
4. [Your First Contribution](#your-first-contribution)
5. [Story Guidelines](#story-guidelines)
6. [Common Scenarios](#common-scenarios)
7. [Project Phases](#project-phases)

---

## Project Overview

**Objective**: Build a humorous story collaboratively using German vocabulary words.

**Key Rules**:
- Each sentence MUST use at least one German word from `dictionary.txt`
- Each contribution is made via a separate Git branch
- Pull Requests are used to merge changes
- Merge conflicts are expected and encouraged as learning opportunities
- Keep the tone fun and maintain narrative flow

---

## Repository Contents

- **`dictionary.txt`** - List of 22 German words with English translations. Every sentence in the story must use at least one of these words.
- **`story.txt`** - The collaborative story. New sentences are appended to the end.
- **`README.md`** - This file. Full instructions for team members.
- **`.gitignore`** - Specifies which files Git should ignore.

---

## Getting Started

### Step 1: Clone the Repository

Open your terminal and run:

```bash
git clone https://github.com/tantshirt/lederhosen-storytime.git
cd lederhosen-storytime
```

### Step 2: Configure Git (First Time Only)

If you haven't set up Git on your machine, configure your name and email:

```bash
git config user.name "Your Full Name"
git config user.email "your.email@example.com"
```

To verify it worked:
```bash
git config user.name
git config user.email
```

### Step 3: Update Your Local Repository

Always pull the latest changes before you start:

```bash
git pull origin main
```

This ensures you have the most recent story content from your teammates.

---

## Your First Contribution

### Step 1: Create a New Branch

Create a branch for your contribution. Use a descriptive name:

```bash
git checkout -b add-sentence-firstname
```

Example: `git checkout -b add-sentence-alice`

### Step 2: Read the Current Story

Open `story.txt` and read what's already been written. Understand the context and humor style so your sentence fits naturally.

### Step 3: Add Your Sentence

1. Open `story.txt` in your text editor
2. Go to the END of the file
3. Add your sentence on a new line
4. Your sentence MUST include at least one German word from `dictionary.txt`

**Example sentence**:
```
Klaus discovered that ordering Apfelkuchen from a random Doener stand was not his best life decision.
```

### Step 4: Check What You Changed

```bash
git status
```

This shows you which files have been modified. You should see `story.txt` listed.

### Step 5: Review Your Changes

```bash
git diff story.txt
```

This shows the exact changes you made. Verify it looks correct before committing.

### Step 6: Stage Your Changes

```bash
git add story.txt
```

### Step 7: Commit Your Changes

```bash
git commit -m "Add sentence: [brief description of your sentence]"
```

**Good commit message example**:
```
git commit -m "Add sentence about Klaus's Apfelkuchen mistake"
```

**Bad commit message example**:
```
git commit -m "update"  # Too vague
```

### Step 8: Push Your Branch to GitHub

```bash
git push origin add-sentence-firstname
```

Example: `git push origin add-sentence-alice`

### Step 9: Create a Pull Request (PR)

1. Go to https://github.com/tantshirt/lederhosen-storytime
2. You should see a banner suggesting to create a Pull Request for your branch
3. Click **"Compare & pull request"** or go to **Pull Requests** tab and click **New Pull Request**
4. Make sure:
   - **Base**: `main` (where your changes will merge)
   - **Compare**: `add-sentence-firstname` (your branch)
5. Add a title: `Add sentence: [brief description]`
6. Add a description: Explain what your sentence adds to the story
7. Click **Create Pull Request**

### Step 10: Wait for Review and Merge

The repository maintainer or another team member will:
- Review your PR
- Provide feedback if needed
- Approve and merge your changes

Once merged, your sentence is part of the official story!

---

## Story Guidelines

### What Makes a Good Story Contribution?

1. **Uses a German Word**: Every sentence must include at least one word from `dictionary.txt`
2. **Fits the Narrative**: Read the existing story and make your sentence flow naturally
3. **Humorous Tone**: Keep it funny and lighthearted
4. **Clear Writing**: Use proper grammar and punctuation
5. **Reasonable Length**: One sentence that's not excessively long (typically 15-30 words)
6. **Builds on Context**: Don't contradict previous sentences; build on the established storyline

### Examples of Good Sentences:

✅ "The Ratskeller was crowded with tourists wearing Dirndel and Lederhose, all demanding free Bratwurst."

✅ "His BMW broke down on the Hauptstrasse, and he called a tow truck from Raesfeld."

✅ "The Hund stole Klaus's Brot and ran toward the Biergarten."

### Examples of Poor Sentences:

❌ "The story was interesting." (No German word)

❌ "Klaus then teleported to Mars." (Breaks narrative context)

❌ "The sky was blue." (Doesn't advance the story)

---

## Common Scenarios

### Scenario 1: You Pull and There's a Merge Conflict

**What happened**: Someone else merged a change while you were working on your branch. Git doesn't know which version to use.

**How to resolve**:

1. Pull the latest changes:
   ```bash
   git pull origin main
   ```

2. You'll see conflict markers in `story.txt`:
   ```
   <<<<<<< HEAD
   Your sentence here
   =======
   Their sentence here
   >>>>>>> branch-name
   ```

3. Decide what to keep. Usually, you keep both sentences in the correct order:
   ```
   Their sentence here
   Your sentence here
   ```

4. Remove the conflict markers (`<<<<`, `====`, `>>>>`)

5. Stage and commit:
   ```bash
   git add story.txt
   git commit -m "Resolve merge conflict"
   git push origin add-sentence-firstname
   ```

### Scenario 2: You Forgot to Create a Branch

If you committed directly to `main`, don't panic:

```bash
git reset HEAD~1
git checkout -b add-sentence-firstname
git commit -m "Add sentence: [description]"
git push origin add-sentence-firstname
```

### Scenario 3: You Need to Update Your Branch with Latest Changes

```bash
git fetch origin
git rebase origin/main
git push origin add-sentence-firstname --force-with-lease
```

### Scenario 4: Your PR Needs Changes

1. Make edits to `story.txt` in your branch
2. Stage and commit:
   ```bash
   git add story.txt
   git commit -m "Update sentence based on feedback"
   git push origin add-sentence-firstname
   ```
3. Your PR automatically updates with the new changes

---

## Project Phases

### Phase 1: Team Story Building (Your Current Phase)

- ✅ Repository created and files uploaded
- ⏳ Each team member adds sentences via branches and PRs
- ⏳ Resolve merge conflicts as they arise
- Target: Complete 5-10 sentences as a team

### Phase 2: Cross-Team Contributions

- ⏳ Find other teams' story repositories in Slack #project
- ⏳ Clone other teams' repositories
- ⏳ Create branches and add funny sentences to their stories
- ⏳ Submit PRs to other teams

### Phase 3: Documentation & Voting

- ⏳ Create `PullRequest_List.md` documenting all PRs you created for other teams
- ⏳ Review and approve/decline PRs from other teams
- ⏳ Post your repository link in Slack #project
- ⏳ Vote for your favorite story with a thumbsup emoji

---

## Quick Reference - Command Cheat Sheet

```bash
# Clone the repo (do this once)
git clone https://github.com/tantshirt/lederhosen-storytime.git

# Get latest changes
git pull origin main

# Create a new branch
git checkout -b add-sentence-yourname

# Check what you changed
git status
git diff story.txt

# Stage and commit
git add story.txt
git commit -m "Your commit message"

# Push to GitHub
git push origin add-sentence-yourname

# Switch to main branch
git checkout main

# Delete your local branch (after PR is merged)
git branch -d add-sentence-yourname
```

---

## Need Help?

- **Git not installed?** Visit https://git-scm.com/downloads
- **Git questions?** Ask your instructor or check https://git-scm.com/doc
- **GitHub questions?** Visit https://docs.github.com
- **Stuck on a merge conflict?** Call a team meeting or reach out to the instructor

---

**Let's build something hilarious together! 🍺🥨**

*Project created for SER316 - GitHub Collaboration Exercise*
