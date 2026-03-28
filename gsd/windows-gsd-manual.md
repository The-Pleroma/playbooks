**THE COMPLETE BEGINNER'S MANUAL**

**Warp + Windsurf + GSD**

on Claude Code for Windows

────────────────────────

*How to Create, Manage, and Research Projects*

Windows 10/11

Works on Every Claude Tier:

**Free · Pro (\$20/mo) · Max 5x (\$100/mo) · Max 20x (\$200/mo)**

February 2026

**PART 1: WHAT YOU NEED TO KNOW BEFORE YOU START**

**The Three Tools**

**1. Warp --- Your Modern Terminal**

Warp is a modern terminal that replaces Command Prompt and PowerShell
with a faster, AI-powered experience. It supports PowerShell, WSL, and
Git Bash on Windows. It groups command output into blocks, has
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
| You describe what you want in plain English.                          |
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

Git is version control software. GSD requires it.

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

**PART 7: INSTALLING AND USING GSD (GET SHIT DONE)**

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

**PART 8: THE COMPLETE WORKFLOW --- START TO FINISH**

This walks you through creating a project from scratch. Example:
building a personal portfolio website.

**Phase 1: Set Up Your Project Folder**

> mkdir C:\\Users\\YourName\\Developer\\my-portfolio
>
> cd C:\\Users\\YourName\\Developer\\my-portfolio

Initialize a Git repository:

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
| new-project → research-project → define-requirements → create-roadmap |
| → \[plan-phase N → execute-plan\] (repeat) → complete-milestone       |
+-----------------------------------------------------------------------+

**PART 9: ADDING AN EXISTING PROJECT TO GSD**

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

If you see "fatal: not a git repository," then:

> git init
>
> git add .
>
> git commit -m \"Initial commit: existing project files\"

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

**PART 10: TIER-SPECIFIC WORKFLOW STRATEGIES**

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

**PART 11: TROUBLESHOOTING & FAQ**

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

+-----------------------------------------------------------------------+
| **REMEMBER**                                                          |
|                                                                       |
| Warp is where you type. Claude Code is the AI that builds. GSD keeps  |
| the AI focused. Windsurf is where you see the code. You are the       |
| project manager.                                                      |
+-----------------------------------------------------------------------+

*─── End of Manual ───*
