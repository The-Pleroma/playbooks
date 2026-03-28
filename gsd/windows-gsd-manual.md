**THE COMPLETE BEGINNER'S MANUAL**

**Warp + Windsurf + GSD**

on Claude Code for Windows

────────────────────────

*How to Create, Manage, and Research Projects*

Windows 10/11

Works on Every Claude Tier:

**Free · Pro (\$20/mo) · Max 5x (\$100/mo) · Max 20x (\$200/mo)**

March 2026

---

## Table of Contents

- [Part 1: What You Need to Know Before You Start](#part-1-what-you-need-to-know-before-you-start)
- [Part 2: Understanding Claude's Subscription Tiers](#part-2-understanding-claudes-subscription-tiers)
- [Part 3: Setting Up Your Windows PC](#part-3-setting-up-your-windows-pc)
- [Part 4: Installing and Using Warp Terminal](#part-4-installing-and-using-warp-terminal)
- [Part 5: Installing and Using Windsurf IDE](#part-5-installing-and-using-windsurf-ide)
- [Part 6: Installing Claude Code](#part-6-installing-claude-code)
- [Part 7: Skills, Plugins, and MCPs — Extending Claude Code](#part-7-skills-plugins-and-mcps--extending-claude-code)
- [Part 8: Installing and Using GSD (Get Shit Done)](#part-8-installing-and-using-gsd-get-shit-done)
- [Part 9: The Complete Workflow — Start to Finish](#part-9-the-complete-workflow--start-to-finish)
- [Part 10: Adding an Existing Project to GSD](#part-10-adding-an-existing-project-to-gsd)
- [Part 11: Tier-Specific Workflow Strategies](#part-11-tier-specific-workflow-strategies)
- [Part 12: Troubleshooting & FAQ](#part-12-troubleshooting--faq)
- [Part 13: Connecting Obsidian (Your Second Brain)](#part-13-connecting-obsidian-your-second-brain)
- [Part 14: Expert Sub-Agents & Additional Skills](#part-14-expert-sub-agents--additional-skills)
- [Quick Reference: All Commands at a Glance](#quick-reference-all-commands-at-a-glance)
- [Addendum: Session Handoff Skill](#addendum-session-handoff-skill)

---

**PART 1: WHAT YOU NEED TO KNOW BEFORE YOU START**

**The Three Tools**

**1. Warp --- Your Modern Terminal**

Warp is a modern terminal that replaces Command Prompt and PowerShell
with a faster, AI-powered experience. It supports PowerShell, WSL, and
Git Bash on Windows. (Git Bash is a terminal environment that gets installed alongside Git in Part 3 — it lets you use the same commands as Mac and Linux users.) It groups command output into blocks, has
autocomplete, and built-in AI. Free to download.

**2. Windsurf --- Your AI Code Editor**

Windsurf is an AI-powered code editor (IDE) with an AI assistant called
Cascade. You use it to see and manage the files that Claude Code
creates. Free tier available.

**3. GSD (Get Shit Done) --- Your AI Project Manager**

GSD is a workflow system that sits on top of Claude Code. It prevents
context rot by breaking projects into phases and tasks, each running in
a fresh memory space. Free and open source.

**How They Work Together**

1.  **Open Warp** (your terminal) and navigate to your project folder.

2.  **Launch Claude Code** inside Warp by typing "claude" and pressing
    Enter.

3.  **Use GSD commands** inside Claude Code to plan, research, and
    build.

4.  **Open Windsurf** to view files, read code, or use Cascade for extra
    AI help.

+-----------------------------------------------------------------------+
| **KEY CONCEPT**                                                       |
|                                                                       |
| You do not need to know how to code. GSD was built for non-coders.    |
| You describe what you want in plain English. GSD builds things piece  |
| by piece. Each piece gets automatically saved to a change history on  |
| your computer using a tool called Git (you will install it in Part 3).|
+-----------------------------------------------------------------------+

**Prerequisites**

- Windows 10 version 1809 or later (Windows 11 recommended)

- An internet connection

- A Claude Pro or Max account (\$20/month minimum for full workflow)

- About 30--45 minutes for setup

- No coding experience required

**PART 2: UNDERSTANDING CLAUDE'S SUBSCRIPTION TIERS**

Your Claude subscription tier determines how much you can use these
tools and how fast they will work. This is the same regardless of your
operating system.

**The Four Tiers at a Glance**

  ---------- ----------- ---------- ------------- ---------------------------
  **Tier**   **Monthly   **Usage    **Claude Code **Best For**
             Cost**      vs. Free** Access**

  Free       \$0         Baseline   Not included  Testing, light tasks

  Pro        \$20/mo     5x Free    Included      Daily use, solo projects

  Max 5x     \$100/mo    25x Free   Full access   Heavy daily use

  Max 20x    \$200/mo    100x Free  Full access   All-day power use
  ---------- ----------- ---------- ------------- ---------------------------

**Detailed Breakdown**

**Free Tier (\$0/month)**

Access to Claude's mid-range models via web chat. Roughly 9 messages per
five-hour window. Does NOT include Claude Code access.

+-----------------------------------------------------------------------+
| **IMPORTANT: Free Tier Limitation**                                   |
|                                                                       |
| Claude Code requires a Claude Pro or Max subscription, or an          |
| Anthropic API key with active billing. The full workflow in this      |
| manual requires at minimum the Pro tier (\$20/month).                 |
+-----------------------------------------------------------------------+

**Pro Tier (\$20/month)**

5x the usage of Free. Access to all Claude models including Opus.
Includes Claude Code. Approximately 45 messages per five-hour window.
This is the minimum tier for the full workflow.

**Max 5x (\$100/month)**

25x the usage of Free. Maximum priority access and full Claude Code
capabilities. Comfortable for multi-phase GSD projects in a single day.

**Max 20x (\$200/month)**

100x the usage of Free. Anthropic's highest individual tier. Rate limits
are rarely a concern. Leave GSD running for extended sessions.

**Which Tier Should You Choose?**

  ---------------------- ------------------ ------------------------------
  **Your Situation**     **Recommended      **Why**
                         Tier**

  Just exploring         Pro (\$20)         Minimum for Claude Code + GSD

  1--2 projects per week Pro (\$20)         Enough for focused sessions

  Building daily         Max 5x (\$100)     Avoids rate limit
                                            interruptions

  Full-time AI           Max 20x (\$200)    Uninterrupted, maximum
  development                               capacity
  ---------------------- ------------------ ------------------------------

+-----------------------------------------------------------------------+
| **COST-SAVING TIP**                                                   |
|                                                                       |
| Start with Pro. You can upgrade mid-month. Anthropic prorates the     |
| difference.                                                           |
+-----------------------------------------------------------------------+

**PART 3: SETTING UP YOUR WINDOWS PC**

**Step 1: Install Git for Windows**

Git is version control software that runs on your computer and tracks every change to your project files — like a detailed undo history that never expires. GSD relies on it heavily. Once Git is installed, you never need to run Git commands yourself — GSD handles saving your changes automatically as you build.

5.  **Go to:** git-scm.com/download/win

6.  **Download** the 64-bit installer and run it.

7.  **Accept all defaults** during installation. The important ones: Git
    Bash integration and adding Git to your PATH.

Verify by opening PowerShell or Git Bash and typing:

> git \--version

**Step 2: Install Node.js**

Node.js lets your computer run JavaScript programs. Claude Code and GSD
both need it.

8.  **Go to:** nodejs.org

9.  **Download** the LTS (Long Term Support) version for Windows.

10. **Run the installer.** Accept all defaults. Check the box for
    "Automatically install necessary tools" if prompted.

Verify in PowerShell or Git Bash:

> node \--version

You need version 18 or higher.

> npm \--version

**Step 3: Install Windows Subsystem for Linux (Optional but
Recommended)**

Claude Code runs natively on Windows via Git Bash, but many developers
prefer running it inside WSL (Windows Subsystem for Linux) for better
compatibility. If you want WSL:

Open PowerShell as Administrator and type:

> wsl \--install

Restart your computer when prompted. WSL installs Ubuntu by default.

+-----------------------------------------------------------------------+
| **CHECKPOINT**                                                        |
|                                                                       |
| You should now have: Git installed, Node.js 18+, npm installed, and   |
| optionally WSL. Verify each with \--version commands before           |
| proceeding.                                                           |
+-----------------------------------------------------------------------+

### Step 4: Set Up GitHub (Recommended)

GitHub is a separate, free online service that stores a copy of your project in the cloud. It works on top of Git, the tool you installed in Step 1. Think of it this way: **Git** is the tool on your computer that saves every change you make. **GitHub** is a website where you upload those saved changes so they are backed up online and accessible from any computer. They are two different things with similar names — Git works without GitHub, but GitHub needs Git. GSD works fine without GitHub, but once you have more than one project, GitHub becomes essential for keeping everything safe and organized.

You do not need GitHub to start using GSD. You can skip this step and come back to it later. But if you are working on anything you would be upset to lose, set it up now.

#### Create a GitHub Account

1. Go to https://github.com and click **Sign up**
2. Use your real email address — this is how your commits (saved changes) get linked to your profile
3. Pick a username you are comfortable with — it will be visible on your repos
4. Free tier is all you need

#### Install the GitHub CLI

The GitHub CLI (`gh`) lets you create repos, push code, and manage everything from Warp or Git Bash without opening a browser.

**Option A — winget (recommended):**
```powershell
winget install GitHub.cli
```

**Option B — download installer:**
Go to https://cli.github.com and download the Windows installer (.msi).

After installing, close and reopen your terminal so the `gh` command is available.

#### Authenticate

In Warp or Git Bash, run:

```bash
gh auth login
```

It will ask you a few questions. Pick these:

1. **GitHub.com** (not Enterprise)
2. **HTTPS** (simpler than SSH)
3. **Login with a web browser**

It gives you a one-time code, opens your browser, you paste the code, done. You only do this once — it stays authenticated across all your projects.

#### Set Your Git Identity (So GitHub Knows Who You Are)

This step configures Git — the local tool on your computer — with your name and email. GitHub uses this information to label your contributions. Run these two commands, replacing the example values with your own:

```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

Use the same email address you used when creating your GitHub account. This links your local Git saves to your GitHub profile.

#### Create Your First Repository

Once you have a project you want to back up, navigate to its folder and run:

```bash
gh repo create your-username/your-project-name --private --source . --remote origin
```

This creates a private repo on GitHub, links it to your local project, and sets it as the remote. Now "push" your code — this means uploading your locally saved changes from Git (on your computer) to GitHub (in the cloud):

```bash
git push -u origin main
```

That is it — your code is now backed up on GitHub. After this, GSD's automatic commits will stay local until you push. To push new work up to GitHub at any point:

```bash
git push
```

#### Public vs Private Repos

- **Private** — only you can see it. Use for anything with API keys, business logic, or code you are not ready to share.
- **Public** — anyone can see it. Use for open source projects, shared manuals, or things you want to showcase.

You can change a repo from private to public (or vice versa) at any time in GitHub's settings.

#### Organizations (Optional)

If you are working with a team or want a shared space for documentation:

1. Go to https://github.com → click your profile icon → **Your organizations** → **New organization**
2. Free tier works fine
3. Create repos under the org (e.g., `your-org/playbooks`) that all members can push to

#### When to Push

- **End of a work session** — back up your progress
- **After completing a GSD phase** — natural checkpoint
- **Before switching machines** — so you can download your latest changes on the other computer (called "pulling")
- **Before any risky operation** — safety net

You do not need to push after every single commit. GSD makes lots of small commits locally — push when you have reached a meaningful stopping point.

---

**PART 4: INSTALLING AND USING WARP TERMINAL**

**Installing Warp on Windows**

11. **Go to:** warp.dev/download

12. **Click the Windows download** (x64 or ARM64 depending on your PC).
    An .exe installer downloads.

13. **Run the installer.** Follow the on-screen instructions.

14. **Launch Warp** from the Start menu.

15. **Create a free account** when prompted (optional but recommended
    for AI features).

Alternative: install via WinGet:

> winget install Warp.Warp

**Warp Shell Options on Windows**

Warp supports three shells on Windows:

- PowerShell --- Windows' default shell. Works out of the box.

- Git Bash --- A Bash environment that comes with Git for Windows.
  Recommended for this workflow because commands match macOS/Linux.

- WSL --- Full Linux environment inside Windows. Most compatible, but
  requires WSL installation (see Part 3).

+-----------------------------------------------------------------------+
| **RECOMMENDATION**                                                    |
|                                                                       |
| Use Git Bash as your default Warp shell. This way, all commands in    |
| this manual (mkdir, cd, ls, etc.) work identically to macOS and       |
| Linux.                                                                |
+-----------------------------------------------------------------------+

**Key Commands**

  --------------------- ------------------------ -------------------------
  **What You Want to    **Git Bash / WSL         **PowerShell Equivalent**
  Do**                  Command**

  See where you are     pwd                      Get-Location

  List files            ls                       dir

  Go into a folder      cd foldername            cd foldername

  Go up one folder      cd ..                    cd ..

  Create a folder       mkdir foldername         mkdir foldername

  Launch Claude Code    claude                   claude
  --------------------- ------------------------ -------------------------

**Useful Warp Shortcuts (Windows)**

  -------------------------- --------------------------------------------
  **Shortcut**               **Action**

  Ctrl + T                   New tab

  Ctrl + D                   Split pane vertically

  Ctrl + Shift + D           Split pane horizontally

  Ctrl + K                   Clear terminal

  Ctrl + P                   Command palette

  Up Arrow                   Previous command

  Ctrl + R                   Search command history
  -------------------------- --------------------------------------------

**PART 5: INSTALLING AND USING WINDSURF IDE**

**Installing Windsurf**

16. **Go to:** windsurf.com/download

17. **Download the Windows version.**

18. **Run the installer** and follow the prompts.

19. **Sign in** with Google or GitHub when prompted.

20. **Choose Free tier** to start (upgrade later if needed).

**Windsurf Interface**

- File Explorer (left) --- all your project files and folders

- Editor (center) --- where you read and edit code in tabs

- Terminal (bottom) --- open with Ctrl + \` (backtick)

- Cascade AI (right) --- open with Ctrl + Shift + L

**Opening Your Project in Windsurf**

Either use File \> Open Folder, or from your terminal:

> windsurf .

+-----------------------------------------------------------------------+
| **WORKFLOW TIP**                                                      |
|                                                                       |
| Use Claude Code + GSD as your primary builder and Windsurf as your    |
| viewer and secondary helper. This avoids confusion about which AI is  |
| making changes.                                                       |
+-----------------------------------------------------------------------+

**PART 6: INSTALLING CLAUDE CODE**

**Requirements**

- Claude Pro or Max subscription, OR Anthropic API key with active
  billing

- Node.js 18+ (installed in Part 3)

- Git Bash or WSL (for best compatibility)

**Installation --- Native Installer (Recommended)**

Option A --- PowerShell:

> irm https://claude.ai/install.ps1 \| iex

Option B --- Git Bash or WSL:

> curl -fsSL https://claude.ai/install.sh \| bash

Option C --- WinGet:

> winget install Anthropic.ClaudeCode

Verify:

> claude \--version

**Alternative Installation (npm)**

> npm install -g \@anthropic-ai/claude-code

+-----------------------------------------------------------------------+
| **IMPORTANT**                                                         |
|                                                                       |
| Never use sudo before the npm install command.                        |
+-----------------------------------------------------------------------+

**First-Time Authentication**

21. **Open Warp** and type: claude

22. **Claude Code opens a browser.** If it doesn't, copy the URL it
    displays and paste it in your browser.

23. **Log in** to your Claude account.

24. **Authorize Claude Code** when prompted.

25. **Return to Warp.** Claude Code is now ready.

**Running with Skip Permissions**

> claude \--dangerously-skip-permissions

+-----------------------------------------------------------------------+
| **UNDERSTAND THE RISK**                                               |
|                                                                       |
| This flag lets Claude Code read, write, and execute without asking.   |
| Only use in project folders, never in system directories.             |
+-----------------------------------------------------------------------+

**PART 7: SKILLS, PLUGINS, AND MCPs --- EXTENDING CLAUDE CODE**

Out of the box, Claude Code is very capable. But Claude's capabilities can be extended further with Skills and Plugins --- installable packages that add new behaviors, reference materials, specialized workflows, and custom commands.

**What Skills Are**

A Skill is a bundle of instructions that teaches Claude how to do a specific type of task with precision. Think of it as a domain expert that gets loaded into Claude's context on demand. When you invoke a skill, Claude reads its instructions and then applies that specialized knowledge to your request.

Examples of what a skill can do:

- Teach Claude the exact docx-js syntax for generating Word documents with specific formatting rules
- Give Claude a complete workflow for analyzing property records and financial instruments as a forensic investigator would
- Load a project's complete context --- all the ventures, team, investors, and rules --- so Claude starts any session with full orientation

**What Plugins Are**

A Plugin is a bundle that can include Skills, commands, and configuration settings. It's the packaged form of a more complete extension. Where a Skill is a single specialized capability, a Plugin might deliver multiple related Skills plus custom commands you can run with a slash command.

**Installing a Skill (.skill file)**

If you or Claude's Cowork tool has built a .skill file for you:

1. Save the .skill file to your PC
2. Open Claude's Cowork desktop app
3. Go to Settings and look for Skills or Extensions
4. Import or install the .skill file

Once installed, the skill is available in Claude Code sessions and in Cowork. You can invoke it by name, and it appears in the list of available skills.

**Installing a Plugin (.plugin file)**

Plugins follow the same pattern as skills --- import them through the Claude desktop app's settings. Once installed, any custom commands the plugin provides become available via slash commands inside Claude Code.

```
# Example: once a plugin is installed, its commands appear like:
/status        <- shows status of all active projects
/deck-status   <- shows status of investor decks in Gamma
```

**Verifying What's Installed**

Inside Claude Code, type:

```
/help
```

This lists all available commands, including those added by any installed plugins. It's the quickest way to see what's available in your current session.

**Building Custom Skills**

If you find yourself explaining the same specialized context to Claude repeatedly --- the same domain knowledge, the same rules, the same workflow --- that's a sign you should build a skill. The skill-creator capability in Cowork can help you build and package custom skills.

A well-built skill turns hours of context-setting into a single invocation. For anyone managing multiple complex projects with specialized domain knowledge, this is the highest-leverage investment you can make in your AI workflow.

**The Skill Ecosystem**

Skills and plugins are also available from plugin marketplaces --- curated collections of pre-built capabilities you can install for common professional workflows (legal research, marketing, data analysis, product management, etc.). These are a fast way to extend Claude's capabilities without building from scratch.

+-----------------------------------------------------------------------+
| **TIP**                                                               |
|                                                                       |
| Before building a custom skill, check if a pre-built one already      |
| covers your use case. The time cost of building a skill yourself vs.  |
| installing an existing one is significant. Browse the marketplace     |
| first.                                                                |
+-----------------------------------------------------------------------+

---

**What Are MCPs (Model Context Protocol Servers)?**

MCPs are a different layer from plugins. While plugins are installed through the `/plugins` browser inside Claude Code, MCPs are external server processes that Claude Code connects to for specialized capabilities. Some MCPs are installed with a `claude mcp add` command from the terminal. Others require cloning a GitHub repository, installing it manually, and registering it. The sections below walk you through both types.

**Step 5: Install the Sequential Thinking MCP**

With Claude Code open, type the following and press Enter:

```
please install sequential thinking MCP server
```

Claude Code handles the installation automatically. The Sequential Thinking MCP gives Claude structured step-by-step reasoning capabilities that significantly improve performance on complex, multi-part tasks. Install it once and it is available in every future session.

**Step 6: Install Essential Plugins via /plugins**

Type this inside Claude Code:

```
/plugins
```

This opens the plugin browser. Search for and install each of the following:

- **context7** --- Gives Claude Code access to up-to-date documentation for any software library. Without this, Claude may use outdated API methods. Essential for any coding project.
- **honcho** --- Personalization and memory. Honcho learns your preferences, communication style, and working patterns over time. Note: Honcho uses a custom marketplace --- search for it in /plugins and follow the prompt to add the Honcho marketplace (plastic-labs/claude-honcho) when asked.
- **playground** --- A sandbox for testing ideas and code snippets without touching your main project.
- **superpowers** --- A collection of enhanced capabilities that expand what Claude Code can do out of the box.
- **claude-md-management** --- Maintains and updates your CLAUDE.md project memory file automatically.
- **skill-creator** --- Lets Claude Code build reusable skills --- packaged sets of instructions for tasks you repeat across projects.
- **security-guidance** --- Adds security awareness to Claude's suggestions, flagging potential vulnerabilities as it helps you build.

**Step 7: Optional Plugins and MCPs**

Install these if they are relevant to your work. Some are available directly in `/plugins`; others require a separate install step as noted.

- **figma** --- Two-way Figma MCP integration. Claude Code can read design specs, component properties, and export assets directly from your Figma files. Available in /plugins.
- **gamma** --- MCP for Gamma (gamma.app), the AI presentation platform. Lets Claude Code create, edit, and update Gamma decks programmatically from the terminal. Available in /plugins.
- **supabase** --- Direct integration with Supabase databases. Essential if your apps use a Supabase backend. Available in /plugins.
- **frontend-design** --- Additional tools for web UI and frontend development. Available in /plugins.
- **huggingface-skills** --- Tools for working with machine learning models from HuggingFace. Available in /plugins.

- **netlify** --- Official Netlify MCP server (netlify.com). Deploy apps or static sites directly from the terminal. Install with this command:

  ```
  claude mcp add --transport stdio netlify -- npx -y @netlify/mcp
  ```

  Claude will prompt you to authenticate with your Netlify account on first use.

- **openrouter** --- Gives Claude Code access to 400+ AI models --- GPT-4o, Gemini, Mistral, Llama, and more --- through a single API (openrouter.ai). Get your API key at https://openrouter.ai/ then type this inside Claude Code:

  ```
  please configure OpenRouter as my model routing layer using my OPENROUTER_API_KEY
  ```

- **ACE Data Cloud** --- A platform (https://platform.acedata.cloud/) with MCP servers for AI image, audio, video, and music generation, all accessible directly from inside Claude Code. The suite includes:
  - **Image:** Nano Banana (Google Gemini image generation and editing), Midjourney, Flux
  - **Video:** Seedance (ByteDance), Luma Dream Machine, Veo, Sora
  - **Music and audio:** Suno (full songs, custom lyrics, remixes)

  *Important:* Each ACE Data Cloud service requires its own setup --- sign up at platform.acedata.cloud, navigate to the specific API, click Acquire to get your token, then clone the corresponding GitHub repo from github.com/acedatacloud, install with pip, and register with `claude mcp add`. Do one service at a time. If you get stuck, paste the error into Claude and it will troubleshoot with you.

+-----------------------------------------------------------------------+
| **IMPORTANT**                                                         |
|                                                                       |
| You'll want to create a place to keep all your API keys safe. Copy    |
| and paste them into your notes or a separate document. Keep them safe |
| in case you need to use them again --- if you lose them you can't     |
| always regenerate them.                                               |
+-----------------------------------------------------------------------+

**Recommended Skills to Install**

- **session-handoff** --- Prevents context and work loss during long sessions. Say "checkpoint" or "don't lose this" and it updates your CLAUDE.md and generates a handoff document. The session-handoff.skill file is included with this manual. Install it by opening the Cowork desktop app, going to Settings > Skills, and importing the file.
- **canvas-design (Print and Design)** --- Creates high-quality visual designs including posters, print layouts, and graphics as .png and .pdf files. Ask Claude to design something and it handles the visual composition, color, and layout. Install via the /plugins browser or as a .skill file from Cowork Settings > Skills.

When you have finished installing the plugins and MCPs you want, type `/exit` to close Claude Code. You are ready to install GSD in the next section.

**PART 8: INSTALLING AND USING GSD (GET SHIT DONE)**

**What Is GSD?**

GSD is a meta-prompting and context engineering system created by Tash
(TACHES). It layers on top of Claude Code and solves "context rot" ---
the quality degradation that happens as Claude fills its context window.
GSD breaks your project into phases and tasks, each running in a fresh
sub-agent with a clean 200K-token context.

GSD solves this by:

- Breaking your project into phases and tasks

- Running each task in a fresh sub-agent with a clean context window

- Automatically committing each completed task to Git

- Maintaining planning documents that give every sub-agent the full
  picture

- Including a research stage before building

**Installing GSD**

In your terminal, type:

> npx get-shit-done-cc@latest

**Option A: Global Install (Recommended)**

Global installation places GSD in your home Claude folder (`%USERPROFILE%\.claude\`), making it available in every project on your PC.

> npx get-shit-done-cc \--claude \--global

**Option B: Local Install**

> npx get-shit-done-cc \--claude \--local

**Verifying the Installation**

> cd C:\\Users\\YourName\\Developer\\your-project-folder
>
> claude \--dangerously-skip-permissions

Then type inside Claude Code:

> /gsd:help

You should see a list of all available GSD commands.

**Updating GSD**

> npx get-shit-done-cc@latest

To see what has changed, type inside Claude Code:

> /gsd:whats-new

**All GSD Commands**

**Project Setup**

  -------------------------- ----------------------------------------------
  **Command**                **What It Does**

  /gsd:new-project           Start a brand-new project

  /gsd:init-existing         Set up GSD on existing code

  /gsd:research-project      Research technologies and approaches

  /gsd:define-requirements   Define detailed technical requirements

  /gsd:settings              Configure models, sub-agents, branch behavior
  -------------------------- ----------------------------------------------

**Planning and Execution**

  ------------------------ ----------------------------------------------
  **Command**              **What It Does**

  /gsd:create-roadmap      Generate a phased roadmap

  /gsd:plan-phase          Create task plans for a phase
  \[number\]

  /gsd:execute-plan        Sub-agent implements tasks autonomously

  /gsd:status              See where you are
  ------------------------ ----------------------------------------------

**Management**

  ------------------------- ----------------------------------------------
  **Command**               **What It Does**

  /gsd:add-phase            Add a new phase to the roadmap

  /gsd:insert-phase \[n\]   Insert a phase at a specific position

  /gsd:remove-phase \[n\]   Remove a phase and its tasks

  /gsd:complete-milestone   Archive current milestone, prep for next
                            version

  /gsd:quick                Quick fix without full planning

  /gsd:map-codebase         Analyze existing codebase (7 documents)
  ------------------------- ----------------------------------------------

**PART 9: THE COMPLETE WORKFLOW --- START TO FINISH**

This walks you through creating a project from scratch. Example:
building a personal portfolio website.

**Phase 1: Set Up Your Project Folder**

> mkdir C:\\Users\\YourName\\Developer\\my-portfolio
>
> cd C:\\Users\\YourName\\Developer\\my-portfolio

Tell Git to start tracking this folder (this creates a hidden record of changes — called a "repository" — inside the folder):

> git init

**Phase 2: Launch Claude Code with GSD**

> claude \--dangerously-skip-permissions

**Phase 3: Start a New GSD Project**

> /gsd:new-project

GSD asks questions about your idea. Answer conversationally.

**Phase 4--6: Research, Requirements, Roadmap**

> /gsd:research-project
>
> /gsd:define-requirements
>
> /gsd:create-roadmap

**Phase 7--8: Plan and Execute Each Phase**

> /gsd:plan-phase 1
>
> /gsd:execute-plan

Repeat for each phase. Watch progress in your terminal; view files in
Windsurf.

**Phase 9: Complete the Milestone**

> /gsd:complete-milestone

+-----------------------------------------------------------------------+
| **WORKFLOW SUMMARY**                                                  |
|                                                                       |
| new-project -> research-project -> define-requirements -> create-roadmap |
| -> \[plan-phase N -> execute-plan\] (repeat) -> complete-milestone    |
+-----------------------------------------------------------------------+

**PART 10: ADDING AN EXISTING PROJECT TO GSD**

If you already have a project --- built in Claude's web chat, coded by
hand, or inherited --- you can bring it into the GSD workflow. You do
not need to start from scratch.

**Getting Your Files Ready**

**Scenario A: Files already on your computer**

Note the folder path and proceed to Step 1 below.

**Scenario B: Files created in Claude's web chat**

Download each file from your Claude conversation, then move them into a
project folder:

> mkdir C:\\Users\\YourName\\Developer\\my-existing-project
>
> move %USERPROFILE%\\Downloads\\index.html
> C:\\Users\\YourName\\Developer\\my-existing-project\\

**Scenario C: Project is on GitHub**

> git clone https://github.com/your-username/your-repo-name.git

**Step-by-Step**

**Step 1: Navigate to Your Project**

> cd C:\\Users\\YourName\\Developer\\my-existing-project

**Step 2: Initialize Git (If Needed)**

> git status

If you see "fatal: not a git repository," then run these three commands:

> git init

This tells Git to start tracking this folder (creates a hidden record of changes called a "repository").

> git add .

This stages all your current files — it tells Git "these are the files I want to save in the next snapshot."

> git commit -m \"Initial commit: existing project files\"

This saves a snapshot of all the staged files with a descriptive message. Think of it as pressing "Save" with a label.

+-----------------------------------------------------------------------+
| **IMPORTANT**                                                         |
|                                                                       |
| Always commit your current files before starting GSD. This gives you  |
| a clean snapshot to return to.                                        |
+-----------------------------------------------------------------------+

**Step 3: Launch Claude Code**

> claude \--dangerously-skip-permissions

**Step 4: Map Your Codebase (CRITICAL)**

> /gsd:map-codebase

GSD spawns parallel sub-agents that analyze your entire codebase and
produce seven detailed documents covering architecture, tech stack, code
patterns, components, data models, API surface, and technical debt.

+-----------------------------------------------------------------------+
| **DO NOT SKIP THIS STEP**                                             |
|                                                                       |
| Without /gsd:map-codebase, the AI builds on code it does not          |
| understand. It will duplicate functionality and use inconsistent      |
| patterns. Always map first.                                           |
+-----------------------------------------------------------------------+

**Step 5: Define What's Next**

> /gsd:new-project

Because it already analyzed your code, questions focus on what you want
to add or change, not what technologies to use.

**Steps 6--9: Research, Roadmap, Plan, Execute**

> /gsd:research-project
>
> /gsd:define-requirements
>
> /gsd:create-roadmap
>
> /gsd:plan-phase 1
>
> /gsd:execute-plan

**Quick Mode for Small Changes**

> /gsd:quick

For bug fixes, small features, and one-off tasks without a full roadmap.

**Starting a New Version**

> /gsd:complete-milestone
>
> /gsd:new-milestone

Starts a fresh planning cycle for V2, V3, etc.

**PART 11: TIER-SPECIFIC WORKFLOW STRATEGIES**

**Pro Tier (\$20/month)**

**Constraint:** \~5x free usage. You will hit rate limits during
extended builds.

- Plan and research in one session, then take a break.

- Execute 1--2 phases per session.

- Use GSD's "budget" profile (/gsd:settings) for lighter models.

- Close Claude Code when not actively building.

**Max 5x (\$100/month)**

**Constraint:** 25x free. Comfortable for a full GSD project in a single
day.

- Use the "balanced" profile --- strong models for planning, mid-tier
  for execution.

- Enable sub-agents for research.

- Plan and execute 3--4 phases per session.

**Max 20x (\$200/month)**

**Constraint:** 100x free. Rate limits rarely a concern.

- Use the "quality" profile --- most powerful models for everything.

- Enable all sub-agents.

- Run the entire workflow start-to-finish in one session.

**GSD Model Profiles**

  ------------- ------------------ ------------------ ----------------------
  **Profile**   **Planning Model** **Execution        **Best For**
                                   Model**

  Quality       Strongest          Strongest          Max tiers, critical
                                                      projects

  Balanced      Strong             Mid-tier           Max 5x, most projects

  Budget        Mid-tier           Lightweight        Pro tier, high-volume
                                                      work
  ------------- ------------------ ------------------ ----------------------

Change profile: /gsd:settings inside Claude Code.

**PART 12: TROUBLESHOOTING & FAQ**

**Installation Issues**

**"command not found: claude"**

Your shell cannot find the Claude Code binary. In PowerShell, try:

> \$env:Path += \";\$env:USERPROFILE\\.local\\bin\"

For a permanent fix, add the path to your system Environment Variables
via Settings \> System \> About \> Advanced System Settings \>
Environment Variables.

In Git Bash or WSL:

> echo \'export PATH=\"\$HOME/.local/bin:\$PATH\"\' \>\> \~/.bashrc
>
> source \~/.bashrc

**GSD commands not recognized**

26. Exit Claude Code (/exit or Ctrl+C).

27. Re-run: npx get-shit-done-cc@latest

28. Re-launch Claude Code and try /gsd:help again.

**Runtime Issues**

**Claude Code is slow or unresponsive**

- Check your internet connection.

- You may have hit a rate limit. Type `/exit` and wait for the window to reset.

- Run: `claude doctor` --- this diagnoses common issues.

**GSD execution stops mid-phase**

- Type `/gsd:status` to see where it stopped.

- Type `/gsd:execute-plan` again to resume from where it left off.

- If the problem persists, check the Git log: `git log --oneline -10`

**FAQ**

**Q: Do I need to know how to code?**

A: No. GSD was built for non-coders.

**Q: Can I use a different terminal?**

A: Yes. PowerShell, Git Bash, Windows Terminal, or WSL all work. Warp
just makes it nicer.

**Q: Can I use VS Code or Cursor instead of Windsurf?**

A: Yes. Any code editor works for viewing files.

**Q: How much does this all cost?**

A: Warp is free. Windsurf has a free tier. Claude Pro is \$20/month. GSD
is free. Minimum total: \$20/month.

**Q: Does this work on all operating systems?**

A: Yes. Warp, Windsurf, Claude Code, and GSD all support macOS, Windows,
and Linux. Separate manuals are available for each platform.

**Q: What if I want to undo something the AI built?**

A: GSD commits every task to Git individually. Use `git log --oneline` to find the commit you want to revert to, then use `git reset --hard [commit-hash]` to go back to that state.

**PART 13: CONNECTING OBSIDIAN (YOUR SECOND BRAIN)**

Obsidian is a markdown-based knowledge management app --- a "second brain" where you store notes, ideas, research, and brain dumps. By connecting it to Claude Code (and optionally Claude Co-Work on the web), Claude can read your notes, search your vault, and create new notes directly. This means you can brain dump ideas into Obsidian anytime, and Claude will naturally have that context in future sessions without you having to re-explain anything.

---

**13.1 Connecting via MCP (Model Context Protocol)**

**Prerequisites**

- Obsidian installed (https://obsidian.md --- free)
- A vault created (Obsidian will prompt you to create one on first launch)
- Claude Code installed and working

**How to Install**

**Step 1: Install two Obsidian community plugins**

Open Obsidian -> Settings (gear icon) -> Community Plugins -> Turn on community plugins -> Browse

Install and enable both of these:

1. **Local REST API** (by Adam Coddington) --- gives external tools secure access to your vault
2. **MCP Tools** (by Jack Steam) --- creates the MCP bridge between Obsidian and AI tools

**Step 2: Copy your API key**

After enabling Local REST API:

- Go to Settings -> Local REST API
- You'll see an API key displayed --- copy it (it's a long string of letters and numbers)
- Keep this somewhere safe; you'll need it in the next step

**Step 3: Install the MCP server**

In the MCP Tools plugin settings:

- Click **"Install Server"**
- The plugin will download a server binary into your vault's `.obsidian\plugins\mcp-tools\bin\` folder
- It will also auto-configure Claude Desktop if you have it installed

**Step 4: Connect to Claude Code globally**

This is the step that makes it work in Claude Code (not just Claude Desktop). You need to edit Claude Code's config file.

*Option A --- Ask Claude to do it:*

> "Add the Obsidian MCP server to my global Claude Code config. The server binary is at [your vault path]\\.obsidian\\plugins\\mcp-tools\\bin\\mcp-server.exe and the API key is [your key]."

*Option B --- Do it manually:*

Open `%USERPROFILE%\.claude.json` in any text editor (e.g. Notepad) and find the `"mcpServers"` section near the bottom of the file. Add the Obsidian entry:

```json
"mcpServers": {
    "obsidian": {
      "command": "C:\\Users\\YOUR_USERNAME\\Documents\\Obsidian Vault\\.obsidian\\plugins\\mcp-tools\\bin\\mcp-server.exe",
      "env": {
        "OBSIDIAN_API_KEY": "your_api_key_here"
      }
    }
}
```

**IMPORTANT:** Replace `YOUR_USERNAME` with your actual Windows username, adjust the vault path if yours is different, and paste your actual API key.

If you already have other MCP servers in that section (like Figma), add Obsidian as another entry with a comma between them.

**Step 5: Restart Claude Code**

Exit Claude Code and relaunch it (or run `/clear` and start a new session). The Obsidian MCP tools should now be available.

**Step 6: Test the connection**

In Claude Code, ask:

> "Can you see my Obsidian vault? List what's in it."

Claude should be able to list your vault's contents.

**What You Can Do With It**

Once connected, you can:

- **Brain dump freely** --- jot ideas, notes, research into Obsidian anytime, and Claude has access next session
- **Ask Claude to check your notes** --- "What did I write about X?" and Claude searches your vault
- **Have Claude create notes** --- "Save this research to my Obsidian vault" and Claude writes a new note
- **Cross-reference** --- Claude can pull context from your notes while working on code or projects

**Where Things Live**

  ----------------------------- -----------------------------------------------------------
  **What**                      **Location**

  Obsidian vault                `C:\Users\YourName\Documents\Obsidian Vault\` (or wherever you created it)

  MCP server binary             `[vault]\.obsidian\plugins\mcp-tools\bin\mcp-server.exe`

  Claude Code config            `%USERPROFILE%\.claude.json` (global MCP servers section)

  Claude Desktop config         `%APPDATA%\Claude\claude_desktop_config.json` (auto-configured)
  ----------------------------- -----------------------------------------------------------

**Troubleshooting**

- **"Obsidian tools not available"** --- Make sure Obsidian is open and both plugins are enabled. Restart Claude Code.
- **"Connection refused"** --- The Local REST API plugin may not be running. Check Obsidian -> Settings -> Local REST API -> make sure it's enabled.
- **Wrong vault path** --- If you moved your vault or named it differently, update the path in `%USERPROFILE%\.claude.json`.

**Migrating Existing Notes**

**Coming from Evernote:**

- Export notebooks from Evernote as `.enex` files
- In Obsidian: Settings -> Core Plugins -> Importer -> Enable -> Import -> select Evernote and your `.enex` files
- Obsidian converts them to markdown automatically

**Migrating PDF conversations or research:**

- Ask Claude: "Convert my PDF files in [folder] to markdown for Obsidian"
- Claude can batch-convert PDFs to markdown, dramatically reducing file size

**Source**

- **Obsidian:** https://obsidian.md (free for personal use)
- **MCP Tools plugin:** https://github.com/jacksteamdev/obsidian-mcp-tools
- **Local REST API plugin:** https://github.com/coddingtonbear/obsidian-local-rest-api

---

**13.2 Obsidian CLI --- Official Command Line Interface (Recommended)**

The official Obsidian CLI (added in v1.12.4, February 2026) gives Claude Code direct terminal access to your vault --- 100+ commands for reading, writing, searching, and manipulating notes. It's faster, more capable, and more scriptable than the MCP approach. **This is now the recommended way for Claude Code to interact with your vault.**

The MCP connection (documented above) still works and is still needed for Claude Co-Work (web), since Co-Work can't run terminal commands. But for Claude Code sessions, the CLI is superior.

**Prerequisites**

- Obsidian v1.12.4 or later (check: open Obsidian -> Settings -> About)
- Obsidian must be running (CLI auto-launches it if not)

**How to Install**

**Step 1: Enable the CLI in Obsidian**

Open Obsidian -> Settings -> General -> Advanced -> toggle **Command line interface** ON -> click **"Register CLI"**

This adds the `obsidian` binary to your system PATH automatically.

**Step 2: Verify in terminal**

Open Warp (Git Bash or PowerShell) and run:

```
obsidian version
```

You should see something like `1.12.7 (installer 1.12.7)`. If you get "command not found," the CLI may not have been added to your PATH. You can add it manually:

In PowerShell:

```
$env:Path += ";$env:LOCALAPPDATA\Obsidian\bin"
```

For a permanent fix, add `%LOCALAPPDATA%\Obsidian\bin` to your system Environment Variables via Settings > System > About > Advanced System Settings > Environment Variables.

In Git Bash:

```
echo 'export PATH="$PATH:/c/Users/YourName/AppData/Local/Obsidian/bin"' >> ~/.bashrc
source ~/.bashrc
```

**Step 3: Test vault access**

```
obsidian vaults          # Should show your vault name(s)
obsidian files | head    # Should list files in your vault (Git Bash/WSL)
obsidian daily:read      # Should show today's daily note
```

**What You Can Do With It**

  -------------------------------------------------------- ------------------------------------------
  **Command**                                              **What It Does**

  `obsidian files`                                         List all files in vault

  `obsidian read file="path/note.md"`                      Read a note's content

  `obsidian create name="path" content="text"`             Create a new note

  `obsidian append file="path" content="text"`             Add to end of a note

  `obsidian prepend file="path" content="text"`            Add after frontmatter

  `obsidian move file="old" to="new"`                      Move/rename (auto-updates wikilinks!)

  `obsidian delete file="path"`                            Move to trash

  `obsidian search query="text" format=json`               Full-text search with JSON output

  `obsidian tags`                                          List all tags in vault

  `obsidian links file="path"`                             Show outgoing links from a note

  `obsidian backlinks file="path"`                         Show incoming links to a note

  `obsidian orphans`                                       Find notes with no backlinks

  `obsidian unresolved`                                    Find broken wikilinks

  `obsidian properties file="path"`                        View frontmatter/metadata

  `obsidian property:set file="path" name="key" value="val"`  Set a frontmatter field

  `obsidian daily`                                         Open/create today's daily note

  `obsidian daily:read`                                    Read today's daily note

  `obsidian daily:append content="text"`                   Append to today's daily note

  `obsidian plugins`                                       List installed plugins

  `obsidian eval code="js_expression"`                     Execute JavaScript against Obsidian's API
  -------------------------------------------------------- ------------------------------------------

**Output formats** --- most commands support `format=` for scripting:
`json`, `csv`, `tsv`, `md`, `paths`, `yaml`, `text` (default), `tree`

**Scripting example (Git Bash or WSL):**

```
# Search vault and pipe to jq
obsidian search query="TODO" format=json | jq '.[].file'

# Bulk set a property on tagged files
obsidian tag tag="#archive" | xargs -I {} obsidian move file="{}" to="Archive/"
```

**CLI vs MCP --- When to Use Which**

  ----------------------------------- ---------------------------------------- ---------------------------------------------------
  **Environment**                     **Use**                                  **Why**

  **Claude Code** (terminal)          CLI (`obsidian` commands via Bash)       100+ commands, JSON output, scriptable, faster

  **Claude Co-Work** (web)            MCP (Obsidian MCP server)               Co-Work can't run terminal commands, MCP is the only option

  **Claude Desktop**                  Either                                  Both work, CLI is more capable
  ----------------------------------- ---------------------------------------- ---------------------------------------------------

Both hit the same vault --- they're just different doors. Your MCP setup still works and should stay configured for Co-Work sessions.

**Where Things Live**

  -------------------------------- -----------------------------------------------------------
  **What**                         **Location**

  CLI binary                       `%LOCALAPPDATA%\Obsidian\bin\obsidian.exe` (auto-added to PATH)

  Your vault                       `C:\Users\YourName\Documents\Obsidian Vault\` (or wherever you created it)

  MCP config (still active)        `%USERPROFILE%\.claude.json` -> `mcpServers` -> `obsidian`
  -------------------------------- -----------------------------------------------------------

**Source**

- **Official docs:** https://obsidian.md/help/cli
- **Requires:** Obsidian v1.12.4+ (GA release February 27, 2026)

---

**13.3 The 12 Vault Skills --- Obsidian + Claude Code Thinking Tools**

A set of 12 slash commands that turn your Obsidian vault into an active thinking partner. Each command uses the Obsidian CLI to read, search, and analyze your notes in different ways --- from morning planning to idea generation to end-of-day capture.

Inspired by Internet Vin's "Obsidian + Claude Code Codebook" --- adapted and installed as Claude Code skills.

**The 12 Commands**

  --------------------------------- ----------------------------------------------- -----------------------------------------------
  **Command**                       **What It Does**                                **When to Use**

  `/vault-context`                  Load your full life/work state into Claude's context   Session start --- "know everything about me"

  `/vault-today`                    Generate a prioritized plan for today from daily notes + tasks   Morning planning

  `/vault-trace [topic]`            Track how a specific idea evolved over time      See the arc of your thinking

  `/vault-connect [A] [B]`          Find unexpected links between two topics         When two ideas seem related but you can't see how

  `/vault-ghost [question]`         Answer a question the way you would, in your voice   Externalize your thinking, draft responses

  `/vault-challenge [topic]`        Find contradictions and weak points in your beliefs   Before big decisions, stress-testing ideas

  `/vault-ideas`                    Scan for emerging patterns, generate idea report   When you want fresh ideas from your notes

  `/vault-graduate`                 Promote half-formed daily note ideas into standalone notes   Weekly review

  `/vault-closeday`                 End-of-day capture: progress, new ideas, carryover   End of day, clear your head

  `/vault-drift`                    Surface recurring themes you haven't consciously noticed   When you sense something emerging but can't name it

  `/vault-emerge`                   Find idea clusters ready to become projects      When scattered thoughts are starting to cluster

  `/vault-schedule`                 Map your stated priorities to actual time blocks   Weekly planning
  --------------------------------- ----------------------------------------------- -----------------------------------------------

**How They Were Installed**

Each skill is a `SKILL.md` file in its own directory under `%USERPROFILE%\.claude\skills\`:

```
%USERPROFILE%\.claude\skills\vault-context\SKILL.md
%USERPROFILE%\.claude\skills\vault-today\SKILL.md
%USERPROFILE%\.claude\skills\vault-trace\SKILL.md
%USERPROFILE%\.claude\skills\vault-connect\SKILL.md
%USERPROFILE%\.claude\skills\vault-ghost\SKILL.md
%USERPROFILE%\.claude\skills\vault-challenge\SKILL.md
%USERPROFILE%\.claude\skills\vault-ideas\SKILL.md
%USERPROFILE%\.claude\skills\vault-graduate\SKILL.md
%USERPROFILE%\.claude\skills\vault-closeday\SKILL.md
%USERPROFILE%\.claude\skills\vault-drift\SKILL.md
%USERPROFILE%\.claude\skills\vault-emerge\SKILL.md
%USERPROFILE%\.claude\skills\vault-schedule\SKILL.md
```

Each file has YAML frontmatter (name + description) and detailed instructions telling Claude how to use the Obsidian CLI to accomplish the task. Claude auto-discovers these --- no configuration needed beyond creating the files.

**Skills that write to your vault** (`/vault-graduate`, `/vault-closeday`) are designed to ask for confirmation before creating or appending notes.

**Note on Co-Work**

These skills are Claude Code only (they need terminal access to run CLI commands). For Co-Work, the same concepts work but you'd need to describe what you want in natural language and let Claude use the Obsidian MCP tools instead. The prompts from each skill could be saved as custom instructions in a Co-Work Project if you want similar behavior there.

**Source**

- **Concept:** Internet Vin's "Obsidian + Claude Code Codebook" --- https://www.internetvin.com
- **Installed:** March 25, 2026

---

**13.4 Connecting Obsidian to Claude Co-Work (Web)**

Claude Co-Work (claude.ai web interface) is separate from Claude Code (terminal). Co-Work can't run terminal commands, so it needs the Obsidian MCP server (documented above in section 13.1) to access your vault.

**How It Works**

Co-Work sessions that are part of a **Project** can have MCP servers attached. The Obsidian MCP server gives Co-Work tools like `search_vault`, `get_vault_file`, `create_vault_file`, etc. --- a smaller set than the CLI's 100+ commands, but enough for reading, searching, and writing notes.

**Key Differences from Claude Code**

  --------------------------------- ----------------------------------- ----------------------------------
  **Feature**                       **Claude Code (CLI)**               **Co-Work (MCP)**

  Available commands                100+                                ~15 MCP tools

  Search output                     JSON, CSV, YAML, etc.              Tool-specific format

  Scripting/piping                  Full shell scripting               Not available

  Vault skills (/vault-*)           All 12 work                        Not available (use natural language instead)

  Backlinks/orphans                 Built-in commands                  Limited

  Frontmatter editing               `property:set` command             Manual note editing
  --------------------------------- ----------------------------------- ----------------------------------

**Setup in Co-Work**

The MCP connection to Obsidian is configured in `%USERPROFILE%\.claude.json` (global) or in the Co-Work Project settings. If the MCP was set up following section 13.1 above, it should already be available in Co-Work Projects.

To verify: Open a Co-Work Project -> check that Obsidian tools appear in the available tools list.

**What Co-Work Can Do With Obsidian**

- Search your vault for specific topics
- Read note contents
- Create new notes
- Simple text searches (no backlink traversal or link graph analysis)
- Append to existing notes

**What You Set Up in Co-Work Stays in Co-Work**

Claude Code and Co-Work are completely separate environments. They don't share:

- Skills or slash commands
- Settings or permissions
- Session history or memory
- MCP configurations (though both can connect to the same MCP servers)

The vault itself is shared (same files on disk), but the tools used to access it are different.

**PART 14: EXPERT SUB-AGENTS & ADDITIONAL SKILLS**

---

**14.1 Installing 136 Expert Sub-Agents (Codex Experts)**

**What This Is**

A collection of 136 specialized AI sub-agents converted from the open-source [awesome-codex-subagents](https://github.com/VoltAgent/awesome-codex-subagents) repository. Each agent is an expert in a specific domain --- backend development, security auditing, React, PostgreSQL, prompt engineering, UX research, and more. When installed, Claude can delegate specialized tasks to these experts instead of doing everything as a generalist.

Think of it like giving Claude a company of 136 specialists to call on. Claude becomes the project manager who knows which expert to bring in for each task.

**The 10 Categories (136 agents total)**

  -------------------------------- ---------- ---------------------------------------------------------
  **Category**                     **Agents** **Examples**

  Core Development                 12         backend-developer, frontend-developer, mobile-developer, api-designer

  Language Specialists             27         react-specialist, typescript-pro, python-pro, swift-expert

  Infrastructure & DevOps          16         devops-engineer, docker-expert, kubernetes-specialist, terraform-engineer

  Quality & Security               16         code-reviewer, security-auditor, debugger, penetration-tester, qa-expert

  Data & AI                        12         prompt-engineer, llm-architect, postgres-pro, ml-engineer

  Developer Experience             13         refactoring-specialist, mcp-developer, documentation-engineer

  Specialized Domains              12         game-developer, fintech-engineer, payment-integration

  Business & Product               11         product-manager, ux-researcher, legal-advisor, technical-writer

  Meta & Orchestration             12         task-distributor, multi-agent-coordinator, workflow-orchestrator

  Research & Analysis              7          competitive-analyst, market-researcher, trend-analyst
  -------------------------------- ---------- ---------------------------------------------------------

**How to Install**

**Step 1: Clone the source repository**

Open Warp (Git Bash or PowerShell) and run:

```
cd %TEMP%
git clone https://github.com/VoltAgent/awesome-codex-subagents.git
```

**Step 2: Create the conversion script**

Ask Claude to create the conversion script by saying:

> "Create a Python script that converts all the TOML agent files in %TEMP%\awesome-codex-subagents\categories\ into Claude Code markdown instruction files. Save the converted agents to %USERPROFILE%\.claude\agents\codex-experts\ organized by category. Include an INDEX.md and INDEX.json for quick lookup."

Or run the conversion script yourself:

```
python %TEMP%\convert-agents.py
```

The conversion script reads each `.toml` file, extracts the agent's name, description, working instructions, and quality checks, then writes a markdown file Claude can read when dispatching sub-agents.

**Step 3: Create the router skill**

Create the directory:

In Git Bash:
```
mkdir -p ~/.claude/skills/codex-experts
```

In PowerShell:
```
New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\.claude\skills\codex-experts"
```

Then create `%USERPROFILE%\.claude\skills\codex-experts\SKILL.md` with a skill definition that tells Claude how to find and dispatch these experts. The skill should:

- Have the name "codex-experts"
- Describe when to use it (code review, security audit, backend dev, etc.)
- Explain the 3-step dispatch process: find expert -> read instructions -> spawn agent
- Include a quick reference table of the most commonly needed experts

**Step 4: Verify installation**

In Claude Code, you should now see `codex-experts` in your available skills. Ask Claude:

> "What expert sub-agents do you have available?"

Claude should reference the 136 agents across 10 categories.

**Where Things Live After Installation**

  ----------------------------------------- -----------------------------------------------------------
  **What**                                  **Location**

  Agent instruction files                   `%USERPROFILE%\.claude\agents\codex-experts\{category}\{name}.md`

  Full index (human-readable)               `%USERPROFILE%\.claude\agents\codex-experts\INDEX.md`

  Machine-readable index                    `%USERPROFILE%\.claude\agents\codex-experts\INDEX.json`

  Router skill                              `%USERPROFILE%\.claude\skills\codex-experts\SKILL.md`
  ----------------------------------------- -----------------------------------------------------------

**How Claude Uses Them**

When Claude encounters a task that matches an expert's specialty, it:

1. Reads the expert's instruction file (working mode, focus areas, quality checks)
2. Spawns a sub-agent with those expert instructions baked into the prompt
3. Adds project-specific context (your files, requirements, constraints)
4. Receives the expert's findings or implementation
5. Synthesizes the results before presenting to you

You don't need to do anything special --- Claude automatically knows when to bring in a specialist.

**Source**

- **GitHub:** https://github.com/VoltAgent/awesome-codex-subagents
- **License:** MIT (free to use)
- **Originally designed for:** OpenAI Codex --- converted for Claude Code

---

**14.2 Installing Dream Memory Consolidation**

**What This Is**

Dream Memory Consolidation is a skill that lets Claude perform a "sleep cycle" on its memory files. Just like how humans consolidate memories during sleep --- reorganizing, pruning, and strengthening important connections --- this skill has Claude review all its memory files, merge duplicates, fix stale information, remove contradictions, and keep the memory index lean and fast.

Over time, Claude's memory files accumulate session logs, duplicate facts, and outdated information. Running `/dream` periodically keeps everything tight so future sessions load faster and Claude has a clearer picture of your project.

**How to Install**

**Step 1: Create the skill directory**

In Git Bash:
```
mkdir -p ~/.claude/skills/dream
```

In PowerShell:
```
New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\.claude\skills\dream"
```

**Step 2: Create the skill file**

Create `%USERPROFILE%\.claude\skills\dream\SKILL.md` with the dream consolidation instructions. The skill should define four phases:

1. **Orient** --- Read the memory directory, check MEMORY.md index, skim existing files
2. **Gather Recent Signal** --- Find new information worth persisting from session logs, git history, and existing memories that have drifted from reality
3. **Consolidate** --- Merge duplicates, convert relative dates to absolute, delete contradicted facts, promote repeated patterns into concise rules
4. **Prune and Index** --- Update MEMORY.md to stay under 200 lines, remove stale pointers, resolve contradictions

You can find the original source at:
https://github.com/Piebald-AI/Claude-code-system-prompts/blob/main/system-prompts/agent-prompt-dream-memory-consolidation.md

**Step 3: Verify installation**

In Claude Code, type:

```
/dream
```

Claude should begin the memory consolidation process and return a summary of what was consolidated, updated, or pruned.

**When to Use It**

- **After long sessions** --- especially sessions where many decisions were made
- **When Claude seems confused** about project state --- memories may be contradicting each other
- **Periodically** --- once a week or whenever the MEMORY.md index feels bloated
- **Before starting a new milestone** --- clean slate for clean planning

**What It Does (and Doesn't Do)**

**Does:**

- Merges duplicate information across memory files
- Fixes stale facts (e.g., a phase marked "in progress" that's actually complete)
- Converts relative dates ("yesterday") to absolute dates ("2026-03-25")
- Removes memory entries that duplicate what's in CLAUDE.md
- Keeps MEMORY.md under 200 lines (the system truncates after that)
- Archives old session logs whose content has been absorbed

**Does NOT:**

- Delete any memory without reason
- Change your preferences or project decisions
- Modify code or project files
- Require any input from you (fully automatic once invoked)

**Source**

- **GitHub:** https://github.com/Piebald-AI/Claude-code-system-prompts
- **Original concept:** Anthropic's upcoming dream memory feature (adapted for current Claude Code)
- **License:** Open source

---

**QUICK REFERENCE: ALL COMMANDS AT A GLANCE**

**One-Time Setup**

  --------------------- -------------------------------------------------
  **Step**              **Command**

  Install Git           git-scm.com/download/win (installer)

  Install Node.js       nodejs.org (LTS installer)

  Install Claude Code   irm https://claude.ai/install.ps1 \| iex

  Install GSD globally  npx get-shit-done-cc \--claude \--global

  Download Warp         warp.dev/download

  Download Windsurf     windsurf.com/download
  --------------------- -------------------------------------------------

**Every New Project**

  ------------------- ------------------------------------ --------------
  **Step**            **Command**                          **Where**

  1\. Create folder   mkdir C:\\Users\\You\\Dev\\project   Terminal

  2\. Navigate        cd C:\\Users\\You\\Dev\\project      Terminal

  3\. Init Git        git init                             Terminal

  4\. Launch Claude   claude                               Warp
                      \--dangerously-skip-permissions

  5\. Start GSD       /gsd:new-project                     Claude Code

  6\. Research        /gsd:research-project                Claude Code

  7\. Requirements    /gsd:define-requirements             Claude Code

  8\. Roadmap         /gsd:create-roadmap                  Claude Code

  9\. Plan phase      /gsd:plan-phase 1                    Claude Code

  10\. Build          /gsd:execute-plan                    Claude Code

  11\. Repeat 9--10   /gsd:plan-phase N +                  Claude Code
                      /gsd:execute-plan

  12\. Finish         /gsd:complete-milestone              Claude Code
  ------------------- ------------------------------------ --------------

**GSD Commands (run inside Claude Code / Warp)**

  --------------------------------- ------------- -----------------------------------------------------------
  **Command**                       **Alias**     **What It Does**

  `/gsd:init`                                     Initialize GSD on a new or existing project. Creates CLAUDE.md and project scaffolding.

  `/gsd:resume-work`                `/gsd:progress`   Resume a previous session. Reads STATE.md and picks up exactly where you left off.

  `/gsd:plan`                                     Break a feature or task into a structured plan with phases and steps.

  `/gsd:execute`                                  Execute the current plan step-by-step. GSD tracks progress automatically.

  `/gsd:status`                                   Show where you are in the current plan --- what's done, what's next.

  `/gsd:new`                                      Start a new task or sub-project within the current GSD session.

  `/gsd:create`                                   Generate a new file, component, or module as part of the current plan.

  `/gsd:add`                                      Add a step or task to the current plan.

  `/gsd:complete`                                 Mark the current step as done and advance to the next.

  `/gsd:research`                                 Ask GSD to research a topic or codebase before planning.

  `/gsd:codebase`                                 Map and summarize the current codebase structure.

  `/gsd:map`                                      Generate a visual or text map of your project structure.

  `/gsd:define`                                   Define a concept, component, or requirement in project context.

  `/gsd:insert`                                   Insert generated code or content into a specific location.

  `/gsd:remove`                                   Remove a step, file, or component from the plan.

  `/gsd:quick`                                    Run a quick one-off task without creating a full plan.

  `/gsd:settings`                                 View or change GSD configuration for the current project.

  `/gsd:help`                                     List all available GSD commands with descriptions.

  `/gsd:whats`                                    Ask GSD what it is currently working on or what comes next.
  --------------------------------- ------------- -----------------------------------------------------------

**Claude Code Commands (Warp terminal)**

  --------------------------------- ----------------------------------------------- -----------------------------------------------------------
  **Command**                       **Flag / Option**                               **What It Does**

  `claude`                                                                          Start an interactive Claude Code session in the current directory.

  `claude --version`                                                                Check which version of Claude Code is installed.

  `claude --global`                 `--global`                                      Apply a setting or MCP globally across all projects.

  `claude --local`                  `--local`                                       Apply a setting or MCP to the current project only.

  `claude --dangerously-skip-permissions`                                           Skip permission prompts (use with caution in trusted environments).

  `claude doctor`                                                                   Run a health check on your Claude Code installation.

  `claude mcp add --transport stdio`                                                Register a new MCP server (e.g. Netlify, Sequential Thinking).
  --------------------------------- ----------------------------------------------- -----------------------------------------------------------

**Key Phrases That Trigger Skills (Cowork / Claude)**

  ----------------------------------------- ----------------------- -----------------------------------------------------------
  **Phrase / Trigger**                      **Skill**               **What Happens**

  "checkpoint"                              session-handoff         Updates CLAUDE.md with session progress. Done in ~2 minutes.

  "don't lose this"                         session-handoff         Full handoff --- updates CLAUDE.md + generates a handoff document with opening prompt for next session.

  "save our progress"                       session-handoff         Same as Full Handoff above.

  "make a Word doc"                         docx                    Creates a formatted .docx file.

  "make a presentation"                     pptx                    Creates or edits a .pptx slide deck.

  "create a PDF"                            pdf                     Creates, merges, or extracts content from PDF files.

  "make a poster / design"                  canvas-design           Generates visual art and design as .png or .pdf.

  "install sequential thinking MCP"         Claude Code AI          Installs the Sequential Thinking MCP server automatically.
  ----------------------------------------- ----------------------- -----------------------------------------------------------

**Obsidian Vault Skills (Claude Code only)**

  --------------------------------- -----------------------------------------------------------
  **Command**                       **What It Does**

  `/vault-context`                  Load life/work state at session start

  `/vault-today`                    Morning planning from daily notes

  `/vault-trace [topic]`            Track idea evolution over time

  `/vault-connect [A] [B]`          Find links between two topics

  `/vault-ghost [question]`         Answer in your voice from your writing

  `/vault-challenge [topic]`        Pressure-test beliefs, find contradictions

  `/vault-ideas`                    Generate ideas from vault patterns

  `/vault-graduate`                 Promote daily note ideas to standalone notes

  `/vault-closeday`                 End-of-day capture + carryover

  `/vault-drift`                    Surface recurring themes

  `/vault-emerge`                   Find idea clusters ready to become projects

  `/vault-schedule`                 Map priorities to time blocks
  --------------------------------- -----------------------------------------------------------

**Additional Skills**

  --------------------------------- ------------------------------------------------- -----------------------------------------------------------
  **Tool**                          **Command / Trigger**                             **What It Does**

  Codex Experts                     (automatic --- Claude invokes when needed)        136 specialist sub-agents for expert tasks

  Dream                             `/dream`                                          Memory consolidation --- merge, prune, deduplicate

  Obsidian MCP                      (automatic --- for Co-Work web sessions)          Read, search, write notes via MCP

  Obsidian CLI                      (automatic --- for Claude Code sessions)          100+ vault commands via terminal
  --------------------------------- ------------------------------------------------- -----------------------------------------------------------

**MCP Install Cheat Sheet**

For full installation instructions and descriptions of each tool, see Part 7: Skills, Plugins, and MCPs.

  -------------------------------- ------------------------------------------------------- ----------------------------
  **MCP / Tool**                   **How to Install**                                      **Where to Get It**

  Sequential Thinking              Tell Claude: "please install sequential thinking MCP server"   Installed automatically by Claude Code

  Figma                            Tell Claude: "please install the Figma MCP" + paste your API token   figma.com/developers

  Gamma                            Tell Claude: "please install the Gamma MCP" + paste your API key   gamma.app

  Netlify                          `claude mcp add --transport stdio netlify -- npx -y @netlify/mcp`   netlify.com

  OpenRouter                       Tell Claude your API key and ask it to use OpenRouter   openrouter.ai

  ACE Data Cloud                   git clone + pip install per service (see Part 7)        platform.acedata.cloud

  Context7                         `/plugins` in Claude Code --- search "Context7" and install   Plugin directory

  Honcho                           `/plugins` in Claude Code --- search "Honcho" and install   Plugin directory
  -------------------------------- ------------------------------------------------------- ----------------------------

All skills installed globally at `%USERPROFILE%\.claude\skills\` --- available across all projects.
Obsidian CLI registered to system PATH --- available from any terminal.
Obsidian MCP configured in `%USERPROFILE%\.claude.json` --- available in Claude Code and Co-Work.

+-----------------------------------------------------------------------+
| **REMEMBER**                                                          |
|                                                                       |
| Warp is where you type. Claude Code is the AI that builds. GSD keeps  |
| the AI focused. Windsurf is where you see the code. You are the       |
| project manager.                                                      |
+-----------------------------------------------------------------------+

---

**ADDENDUM: SESSION HANDOFF SKILL**

The Session Handoff skill protects your work from context loss and session crashes. Copy the content below in its entirety and save it as a file named `session-handoff.skill`. Then install it by opening the Cowork desktop app, going to Settings > Skills, and importing the file.

Once installed, just say "checkpoint" or "don't lose this" at any point during a session and Claude will update your CLAUDE.md and generate a handoff document. Use it aggressively.

```yaml
---
name: session-handoff
description: "Preserves session context and prevents work loss by updating CLAUDE.md and generating handoff documents. Trigger this skill immediately whenever the user says 'checkpoint', 'handoff', 'save our progress', 'update the notes', 'session summary', 'save this', 'don't lose this', or expresses any worry about losing context or the session crashing. Also trigger proactively after any major deliverable is completed. Two modes: Checkpoint (quick mid-session CLAUDE.md update, 2 minutes) and Full Handoff (complete CLAUDE.md update + handoff document for the next session)."
---
```

**Session Handoff Skill**

This skill preserves work by keeping CLAUDE.md current and generating handoff documents when needed.

**Determine Mode**

**Checkpoint** (default for "checkpoint", "save this", mid-session saves):
- Read CLAUDE.md, identify what's new or changed, make targeted updates
- Confirm what was updated in 2-3 sentences. Done in under 2 minutes.

**Full Handoff** (for "handoff", "session summary", end-of-session):
- Everything in Checkpoint, plus generate a `Session_Handoff_[Date].md` document
- Provide a link to the file

**Step 1: Read Current State**

Read CLAUDE.md completely before making any changes.

**Step 2: Scan the Conversation**

Look for changes across: Projects & Products, People & Contacts, Documents & Deliverables, Decisions Made, Pending Tasks.

**Step 3: Update CLAUDE.md**

Make targeted, surgical updates only. Add new Recent Session Work entries at the TOP of that section.

**Step 4: Full Handoff Document (Full Handoff mode only)**

Generate `Session_Handoff_[MonthDay_Year].md` in the workspace root with:

- Opening Prompt for Next Session (paste this to resume)
- What Was Accomplished
- Where Things Stand (table)
- Pending Tasks (prioritized)
- Key File Locations

**Step 5: Confirm**

- **Checkpoint:** "Checkpoint saved. Updated CLAUDE.md: [2-3 specific things]. Nothing lost."
- **Full Handoff:** "Session captured." + link to handoff file.

*--- End of Manual ---*
