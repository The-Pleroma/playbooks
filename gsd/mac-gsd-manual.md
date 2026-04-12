# The Complete Beginner's Manual

## Warp + GSD on Claude Code for Mac

**How to Create, Manage, and Research Projects — From Zero Experience to Full Workflow**

---

Works on Every Claude Tier:
**Free** | **Pro** ($20/mo) | **Max 5x** ($100/mo) | **Max 20x** ($200/mo)

*March 2026*

---

## Table of Contents

- [Part 1: What You Need to Know Before You Start](#part-1-what-you-need-to-know-before-you-start)
- [Part 2: Understanding Claude's Subscription Tiers](#part-2-understanding-claudes-subscription-tiers)
- [Part 3: Setting Up Your Mac](#part-3-setting-up-your-mac) (includes GitHub setup)
- [Part 4: Installing and Using Warp Terminal](#part-4-installing-and-using-warp-terminal)
- [Part 5: Installing Claude Code](#part-5-installing-claude-code)
- [Part 6: Skills, Plugins, and MCPs — Extending Claude Code](#part-6-skills-plugins-and-mcps--extending-claude-code)
- [Part 7: Installing and Using GSD](#part-7-installing-and-using-gsd-get-shit-done)
- [Part 8: The Complete Workflow — Start to Finish](#part-8-the-complete-workflow--start-to-finish)
- [Part 9: Adding an Existing Project to GSD](#part-9-adding-an-existing-project-to-gsd)
- [Part 10: Tier-Specific Workflow Strategies](#part-10-tier-specific-workflow-strategies)
- [Part 11: Troubleshooting & FAQ](#part-11-troubleshooting--faq)
- [Part 12: Connecting Obsidian (Your Second Brain)](#part-12-connecting-obsidian-your-second-brain)
- [Part 13: Expert Sub-Agents & Additional Skills](#part-13-expert-sub-agents--additional-skills)
- [Quick Reference: All Commands at a Glance](#quick-reference-all-commands-at-a-glance)
- [Addendum: Session Handoff Skill](#addendum-session-handoff-skill)

---

## Part 1: What You Need to Know Before You Start

### What This Manual Covers

This manual teaches you how to use three powerful tools together on your MacBook or MacBook Air to work with artificial intelligence on any kind of project — whether that is building software, writing and editing a book, managing documents, doing research, or any other multi-step creative or analytical work. You do not need to know how to code. These tools handle the technical complexity for you. Your job is to be the project manager — you describe what you want, and the AI does it.

### The Two Tools

**1. Warp — Your Modern Terminal**

Warp is a modern replacement for the Terminal app that comes with your Mac. Think of it as the command center where you type instructions for your computer. Warp makes this easier because it has built-in AI assistance, groups your commands into readable blocks, and has autocomplete that predicts what you want to type. It is free to download and use.

**2. GSD (Get Shit Done) — Your AI Project Manager**

GSD is a workflow system created by a developer named Tash (TACHES) that sits on top of Claude Code. As of 2025, GSD also supports other AI runtimes (OpenCode, Gemini CLI, GitHub Copilot, and others) — but Claude Code remains the primary and recommended runtime for this workflow. GSD solves a critical problem: when you use Claude Code on its own, it eventually fills up its memory (called the "context window") and starts forgetting things. GSD prevents this by breaking your project into small, manageable phases and tasks, each running in a fresh memory space. It is free and open source.

### How They Work Together

Here is the relationship between the tools, in plain English:

- You open **Warp** (your terminal) and navigate to your project folder.
- You launch **Claude Code** inside Warp by typing the word `claude` and pressing Enter.
- You use **GSD commands** inside Claude Code to plan, research, and build your project step by step.
- You open your code editor to view the files being created, read the code, make visual edits, or use additional AI help.

> **KEY CONCEPT: You Do Not Need to Code**
>
> GSD was built for non-coders. You describe what you want in plain English. The system asks you clarifying questions, creates a plan, then builds it piece by piece. Each piece gets tested and automatically saved to a history log on your computer using a tool called Git (you will install Git in Part 3 — it keeps a complete record of every change so you can always undo mistakes).

### Prerequisites (What You Need)

- A MacBook or MacBook Air running macOS 10.15 (Catalina) or newer
- An internet connection
- A Claude.ai account — sign up free at claude.ai. You will need at least the Pro tier ($20/month) to use Claude Code. See Part 2 for a full breakdown of tiers.
- About 30-45 minutes for the full setup
- No coding experience required

---

## Part 2: Understanding Claude's Subscription Tiers

Your Claude subscription tier determines how much you can use these tools and how fast they will work. This section explains each tier and its practical impact on your workflow.

### The Four Tiers at a Glance

| Tier | Monthly Cost | Usage vs. Free | Claude Code Access | Best For |
|------|-------------|----------------|-------------------|----------|
| Free | $0 | Baseline | Not included | Testing, light tasks |
| Pro | $20/mo | 5x Free | Included | Daily use, solo projects |
| Max 5x | $100/mo | 25x Free | Full access | Heavy daily use, complex projects |
| Max 20x | $200/mo | 100x Free | Full access | All-day power use, large builds |

> **IMPORTANT: Free Tier Limitation**
>
> Claude Code requires a Claude Pro or Max subscription, or an Anthropic API key with active billing. The full Warp + GSD workflow in this manual requires at minimum the Pro tier ($20/month). Free tier users can still install and use Warp, but cannot run Claude Code or GSD.

### Detailed Breakdown

**Free Tier ($0/month)**

The Free tier gives you access to Claude's mid-range models (like Claude Sonnet 4.6 or Haiku 4.5) through the web chat at claude.ai. It has a soft daily usage cap that resets every five hours. You get roughly 9 messages per five-hour window.

*Impact on this workflow:* The Free tier does NOT include Claude Code access. This means you cannot run Claude Code in your terminal, and therefore you cannot use GSD. You can still install and use Warp as your terminal, but the full AI workflow described in this manual requires at least the Pro tier.

**Pro Tier ($20/month)**

Pro gives you 5 times the usage of the Free tier, access to all Claude models (including the most powerful Opus 4.6), and Claude Code access. You get approximately 45 messages per five-hour window on the web, and a generous allocation for Claude Code.

*Impact on this workflow:* This is the minimum tier for the full workflow. You can run Claude Code, install GSD, and build projects. However, you may hit usage limits during long building sessions. When you hit a limit, you'll need to wait for the five-hour window to reset. **Strategy:** Plan and research first, then execute in focused bursts.

**Max 5x ($100/month)**

Max 5x gives you 5 times the usage of Pro (25 times Free). You get maximum priority access and full Claude Code capabilities. This tier is ideal for people who use Claude for several hours each day.

*Impact on this workflow:* You can comfortably run multi-phase GSD projects without worrying about hitting limits in a single session. Subagents (which GSD spawns for research and execution) consume usage, so having higher limits means smoother, uninterrupted builds.

**Max 20x ($200/month)**

Max 20x provides 20 times the usage of Pro (100 times Free). This is Anthropic's highest individual tier, designed for people who use Claude as a full-time productivity tool.

*Impact on this workflow:* You can leave GSD running for extended periods, execute multiple phases back-to-back, and use the most powerful model settings in GSD's configuration without worrying about token costs or limits.

### Which Tier Should You Choose?

| Your Situation | Recommended Tier | Why |
|----------------|-----------------|-----|
| Just exploring, want to try it | Pro ($20) | Minimum to access Claude Code + GSD |
| Building 1-2 projects per week | Pro ($20) | Enough for focused build sessions |
| Building daily, multi-phase projects | Max 5x ($100) | Avoids rate limit interruptions |
| Full-time AI-assisted development | Max 20x ($200) | Uninterrupted, maximum capacity |

> **COST-SAVING TIP**
>
> Start with Pro. You can always upgrade mid-month if you find yourself hitting limits. Anthropic prorates the difference, so you only pay the extra for the remaining days.

---

## Part 3: Setting Up Your Mac

Before installing any of the tools, your Mac needs two pieces of software that they all depend on: Homebrew (a package manager) and Node.js (a software runtime). This section walks you through both.

### Step 1: Open Terminal (One Last Time)

You need your Mac's built-in Terminal app just for initial setup. After that, you'll use Warp instead.

1. Press **Command + Space** on your keyboard. This opens Spotlight Search.
2. Type **"Terminal"** and press Enter.
3. A window with a blinking cursor will appear. This is your terminal.

### Step 2: Install Homebrew

Homebrew is a package manager for macOS. It lets you install software with a single command instead of downloading files from websites.

Copy and paste this entire command into Terminal and press Enter:

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

You will be asked for your Mac's password (the one you use to log in). Type it and press Enter. You will not see the characters appear as you type — this is normal.

The installation takes 2-5 minutes. When it finishes, it will show instructions to add Homebrew to your PATH. Follow those instructions (they will look something like this):

```bash
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv)"
```

Verify it worked by typing:

```bash
brew --version
```

You should see a version number like "Homebrew 4.x.x".

### Step 3: Install Node.js

Node.js lets your computer run JavaScript programs. Claude Code and GSD both need it.

Type this command and press Enter:

```bash
brew install node
```

Wait for it to finish (1-3 minutes). Then verify:

```bash
node --version
```

You need version 18 or higher. You should see something like "v20.x.x" or "v22.x.x".

Also verify npm (Node's package manager) is installed:

```bash
npm --version
```

You should see a version number. If both commands show version numbers, you are ready.

### Step 4: Install Git

Git is version control software that runs on your computer and tracks every change to your project — like a detailed undo history that never expires. GSD relies on it heavily. Once Git is installed, you never need to run Git commands yourself — GSD handles saving your changes automatically as you build.

You may occasionally see a prompt mentioning "GitHub." Ignore it for now — GitHub is a separate online service covered in Step 5. It is optional.

Type:

```bash
git --version
```

If you see a version number, Git is already installed. If not, install it:

```bash
brew install git
```

> **CHECKPOINT**
>
> At this point you should have: Homebrew installed and working, Node.js version 18+, npm installed, and Git installed. If any of these are not working, do not proceed — the remaining tools depend on them.

### Step 5: Set Up GitHub (Recommended)

GitHub is a separate, free online service that stores a copy of your project in the cloud. It works on top of Git, the tool you installed in Step 4. Think of it this way: **Git** is the tool on your computer that saves every change you make. **GitHub** is a website where you upload those saved changes so they are backed up online and accessible from any computer. They are two different things with similar names — Git works without GitHub, but GitHub needs Git. GSD works fine without it, but once you have more than one project, GitHub becomes essential for keeping everything safe and organized.

You do not need GitHub to start using GSD. You can skip this step and come back to it later. But if you are working on anything you would be upset to lose, set it up now.

#### Create a GitHub Account

1. Go to https://github.com and click **Sign up**
2. Use your real email address — this is how your commits (saved changes) get linked to your profile
3. Pick a username you are comfortable with — it will be visible on your repos
4. Free tier is all you need

#### Install the GitHub CLI

The GitHub CLI (`gh`) lets you create repos, push code, and manage everything from Warp without opening a browser. Install it:

```bash
brew install gh
```

#### Authenticate

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

Once you have a project you want to back up, navigate to its folder in Warp and run:

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

## Part 4: Installing and Using Warp Terminal

### What Is Warp?

Warp is a modern terminal application that replaces the default Terminal on your Mac. It was built from scratch in the Rust programming language, which makes it extremely fast. Warp adds features that the default Terminal does not have: AI-powered command suggestions, code-editor-style text editing, command output organized into blocks, and autocomplete for hundreds of common commands.

You will use Warp as the place where you type all your commands — launching Claude Code, running GSD, navigating folders, and more.

### Installing Warp

1. Open your web browser and go to: **warp.dev/download**
2. Click the download button for macOS. A `.dmg` file will download.
3. Open the `.dmg` file and drag the Warp icon into your Applications folder.
4. Open Warp from your Applications folder (or press Command + Space, type "Warp", and press Enter).
5. On first launch, macOS may show a security prompt. Click "Open" to confirm.
6. Create a free Warp account when prompted. You can sign up with your email or Google/GitHub account.

### Essential Warp Concepts for Beginners

**Blocks**

Every time you run a command, Warp creates a "block" that contains your command and its output. This is much cleaner than the default Terminal, where everything runs together in one long scroll. You can click on any block to select it, copy it, or share it.

**The Input Area**

At the bottom of the Warp window is the input area where you type commands. Unlike the default Terminal, you can use your mouse to click and position your cursor anywhere in this area, just like a text editor. You can also select text, copy/paste, and use keyboard shortcuts like Command+A to select all.

**AI Assistance**

Press the `#` (hash) key at the beginning of a line to activate Warp's AI. Type a question in plain English, like "how do I list all files in this folder?" and Warp will suggest the correct command. Press Enter to run it.

### Key Commands You Will Use in Warp

| What You Want to Do | Command to Type | What It Does |
|---------------------|----------------|-------------|
| See where you are | `pwd` | Prints the current folder path |
| List files in a folder | `ls` | Shows files and folders |
| Go into a folder | `cd foldername` | Changes to that folder |
| Go up one folder | `cd ..` | Moves to the parent folder |
| Create a new folder | `mkdir foldername` | Makes a new empty folder |
| Clear the screen | `clear` | Cleans up the terminal view |
| Launch Claude Code | `claude` | Starts the AI coding assistant |

### Setting Warp as Your Default Terminal

1. Open Warp Settings by pressing **Command + Comma (,)**.
2. Navigate to "General" in the left sidebar.
3. Toggle on "Set Warp as default terminal". Now, whenever any app tries to open a terminal, it will open Warp.

### Useful Warp Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| Command + T | Open a new tab |
| Command + D | Split the pane vertically |
| Command + Shift + D | Split the pane horizontally |
| Command + K | Clear the terminal |
| Command + P | Open the command palette |
| Up Arrow | Recall previous command |
| Ctrl + R | Search command history |

> **WHY WARP INSTEAD OF DEFAULT TERMINAL?**
>
> You can technically do everything in the default Terminal.app that comes with macOS. Warp simply makes it easier, especially for beginners. The AI suggestions, the block-based output, and the text-editor-style input area remove a lot of friction. If you are comfortable with the default Terminal, you can use that instead — all the commands in this manual will work the same way.

---

## Part 5: Installing Claude Code

### What Is Claude Code?

Claude Code is Anthropic's command-line AI coding tool. It runs inside your terminal (Warp) and can read your files, write code, run commands, manage Git, and build entire applications — all from natural language instructions. It is the engine that powers the entire workflow in this manual.

### Requirements

- A Claude Pro or Max subscription ($20/month minimum), **OR**
- An Anthropic API key with active billing on console.anthropic.com
- Node.js version 18+ (installed in Part 3)

### Installation (Recommended Method)

Anthropic now offers a native installer that is simpler than the old npm method. Open Warp and type:

```bash
curl -fsSL https://claude.ai/install.sh | bash
```

After it finishes, reload your terminal configuration:

```bash
source ~/.zshrc
```

Verify the installation:

```bash
claude --version
```

You should see a version number. If you see "command not found," try this:

```bash
echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc
claude --version
```

**Alternative Installation (via Homebrew)**

```bash
brew install --cask claude-code
```

**Alternative Installation (via npm)**

```bash
npm install -g @anthropic-ai/claude-code
```

> **IMPORTANT**
>
> Never use `sudo` before the npm install command. Do NOT type: `sudo npm install -g @anthropic-ai/claude-code`. This creates permission problems that are difficult to fix.

### First-Time Authentication

1. Open Warp and type: `claude`
2. Claude Code will try to open a browser window. If it does not open automatically, it will display a URL. Hold Command and click the URL to open it, or copy and paste it into your browser.
3. Log in to your Claude account (or Anthropic console account) in the browser.
4. Authorize Claude Code when prompted.
5. Return to Warp. Claude Code should now be authenticated and ready to use.

### Running Claude Code with Dangerously Skip Permissions

When you launch Claude Code, it normally asks you to approve every file read, write, and command it runs. For the GSD workflow, this constant approval is impractical. The creator of GSD recommends launching Claude Code with auto-approval:

```bash
claude --dangerously-skip-permissions
```

> **UNDERSTAND THE RISK**
>
> The `--dangerously-skip-permissions` flag lets Claude Code read, write, and execute commands without asking you first. Only use this in project folders where you are comfortable giving the AI full access. Never use this in sensitive directories like your home folder or system folders.

A safer alternative is to configure specific permissions in your Claude Code settings. GSD provides a recommended permissions template in its documentation.

### Quick Test

To verify everything works, create a test folder and try Claude Code:

```bash
mkdir ~/test-project
cd ~/test-project
claude
```

Then type in the Claude Code prompt: "Create a simple hello world HTML file". If it creates the file successfully, your installation is working.

---

## Part 6: Skills, Plugins, and MCPs — Extending Claude Code

Out of the box, Claude Code is very capable. But Claude's capabilities can be extended further with Skills and Plugins — installable packages that add new behaviors, reference materials, specialized workflows, and custom commands.

### What Skills Are

A Skill is a bundle of instructions that teaches Claude how to do a specific type of task with precision. Think of it as a domain expert that gets loaded into Claude's context on demand. When you invoke a skill, Claude reads its instructions and then applies that specialized knowledge to your request.

Examples of what a skill can do:

- Teach Claude the exact docx-js syntax for generating Word documents with specific formatting rules
- Give Claude a complete workflow for analyzing property records and financial instruments as a forensic investigator would
- Load a project's complete context — all the ventures, team, investors, and rules — so Claude starts any session with full orientation

### What Plugins Are

A Plugin is a bundle that can include Skills, commands, and configuration settings. It's the packaged form of a more complete extension. Where a Skill is a single specialized capability, a Plugin might deliver multiple related Skills plus custom commands you can run with a slash command.

### Installing a Skill (.skill file)

If you or Claude's Cowork tool has built a .skill file for you:

1. Save the .skill file to your Mac
2. Open Claude's Cowork desktop app
3. Go to Settings and look for Skills or Extensions
4. Import or install the .skill file

Once installed, the skill is available in Claude Code sessions and in Cowork. You can invoke it by name, and it appears in the list of available skills.

### Installing a Plugin (.plugin file)

Plugins follow the same pattern as skills — import them through the Claude desktop app's settings. Once installed, any custom commands the plugin provides become available via slash commands inside Claude Code.

```
# Example: once a plugin is installed, its commands appear like:
/status        <- shows status of all active projects
/deck-status   <- shows status of investor decks in Gamma
```

### Verifying What's Installed

Inside Claude Code, type:

```
/help
```

This lists all available commands, including those added by any installed plugins. It's the quickest way to see what's available in your current session.

### Building Custom Skills

If you find yourself explaining the same specialized context to Claude repeatedly — the same domain knowledge, the same rules, the same workflow — that's a sign you should build a skill. The skill-creator capability in Cowork can help you build and package custom skills.

A well-built skill turns hours of context-setting into a single invocation. For anyone managing multiple complex projects with specialized domain knowledge, this is the highest-leverage investment you can make in your AI workflow.

### The Skill Ecosystem

Skills and plugins are also available from plugin marketplaces — curated collections of pre-built capabilities you can install for common professional workflows (legal research, marketing, data analysis, product management, etc.). These are a fast way to extend Claude's capabilities without building from scratch.

> **TIP**
>
> Before building a custom skill, check if a pre-built one already covers your use case. The time cost of building a skill yourself vs. installing an existing one is significant. Browse the marketplace first.

---

### What Are MCPs (Model Context Protocol Servers)?

MCPs are a different layer from plugins. While plugins are installed through the `/plugins` browser inside Claude Code, MCPs are external server processes that Claude Code connects to for specialized capabilities. Some MCPs are installed with a `claude mcp add` command from the terminal. Others require cloning a GitHub repository, installing it manually, and registering it. The plugin section below walks you through both types.

### Step 5: Install the Sequential Thinking MCP

With Claude Code open, type the following and press Enter:

```
please install sequential thinking MCP server
```

Claude Code handles the installation automatically. The Sequential Thinking MCP gives Claude structured step-by-step reasoning capabilities that significantly improve performance on complex, multi-part tasks. Install it once and it is available in every future session.

### Step 6: Install Essential Plugins via /plugins

Type this inside Claude Code:

```
/plugins
```

This opens the plugin browser. Search for and install each of the following:

- **context7** — Gives Claude Code access to up-to-date documentation for any software library. Without this, Claude may use outdated API methods. Essential for any coding project.
- **honcho** — Personalization and memory. Honcho learns your preferences, communication style, and working patterns over time. Note: Honcho uses a custom marketplace — search for it in /plugins and follow the prompt to add the Honcho marketplace (plastic-labs/claude-honcho) when asked.
- **playground** — A sandbox for testing ideas and code snippets without touching your main project.
- **superpowers** — A collection of enhanced capabilities that expand what Claude Code can do out of the box.
- **claude-md-management** — Maintains and updates your CLAUDE.md project memory file automatically.
- **skill-creator** — Lets Claude Code build reusable skills — packaged sets of instructions for tasks you repeat across projects.
- **security-guidance** — Adds security awareness to Claude's suggestions, flagging potential vulnerabilities as it helps you build.

### Step 7: Optional Plugins and MCPs

Install these if they are relevant to your work. Some are available directly in `/plugins`; others require a separate install step as noted.

- **figma** — Two-way Figma MCP integration. Claude Code can read design specs, component properties, and export assets directly from your Figma files. Available in /plugins.
- **gamma** — MCP for Gamma (gamma.app), the AI presentation platform. Lets Claude Code create, edit, and update Gamma decks programmatically from the terminal. Available in /plugins.
- **supabase** — Direct integration with Supabase databases. Essential if your apps use a Supabase backend. Available in /plugins.
- **frontend-design** — Additional tools for web UI and frontend development. Available in /plugins.
- **swift-lsp** — Language server support for Swift. Install if you are building iOS or macOS apps. Available in /plugins.
- **huggingface-skills** — Tools for working with machine learning models from HuggingFace. Available in /plugins.

- **netlify** — Official Netlify MCP server (netlify.com). Deploy apps or static sites directly from the terminal. Install with this command:

  ```bash
  claude mcp add --transport stdio netlify -- npx -y @netlify/mcp
  ```

  Claude will prompt you to authenticate with your Netlify account on first use.

- **openrouter** — Gives Claude Code access to 400+ AI models — GPT-4o, Gemini, Mistral, Llama, and more — through a single API (openrouter.ai). Get your API key at https://openrouter.ai/ then type this inside Claude Code:

  ```
  please configure OpenRouter as my model routing layer using my OPENROUTER_API_KEY
  ```

- **ACE Data Cloud** — A platform (https://platform.acedata.cloud/) with MCP servers for AI image, audio, video, and music generation, all accessible directly from inside Claude Code. The suite includes:
  - **Image:** Nano Banana (Google Gemini image generation and editing), Midjourney, Flux
  - **Video:** Seedance (ByteDance), Luma Dream Machine, Veo, Sora
  - **Music and audio:** Suno (full songs, custom lyrics, remixes)

  *Important:* Each ACE Data Cloud service requires its own setup — sign up at platform.acedata.cloud, navigate to the specific API, click Acquire to get your token, then clone the corresponding GitHub repo from github.com/acedatacloud, install with uv or pip, and register with `claude mcp add`. Do one service at a time. If you get stuck, paste the error into Claude and it will troubleshoot with you.

> **IMPORTANT**
>
> You'll want to create a place to keep all your API keys safe. Copy and paste them into your notes or a separate document. Keep them safe in case you need to use them again — if you lose them you can't always regenerate them.

### Recommended Skills to Install

- **session-handoff** — Prevents context and work loss during long sessions. Say "checkpoint" or "don't lose this" and it updates your CLAUDE.md and generates a handoff document. The session-handoff.skill file is included with this manual. Install it by opening the Cowork desktop app, going to Settings > Skills, and importing the file.
- **canvas-design (Print and Design)** — Creates high-quality visual designs including posters, print layouts, and graphics as .png and .pdf files. Ask Claude to design something and it handles the visual composition, color, and layout. Install via the /plugins browser or as a .skill file from Cowork Settings > Skills.

When you have finished installing the plugins and MCPs you want, type `/exit` to close Claude Code. You are ready to install GSD in the next section.

---

## Part 7: Installing and Using GSD (Get Shit Done)

### What Is GSD?

GSD is a meta-prompting and context engineering system created by Tash (TACHES). It is a set of commands and agents that layer on top of Claude Code. As of 2025, GSD supports six runtimes: Claude Code, OpenCode, Gemini CLI, Codex, GitHub Copilot, and Antigravity. This manual uses the Claude Code runtime (the original and most mature option). Without GSD, using Claude Code for anything larger than a simple script is like trying to build a house without blueprints — the AI starts strong but gradually loses track of what it is doing as its context window fills up.

GSD solves this by:

- Breaking your project into phases and tasks
- Running each task in a fresh sub-agent with a clean context window (200K tokens of pure focus)
- Automatically committing each completed task to Git (so nothing is ever lost)
- Maintaining planning documents that give every sub-agent the full picture of your project
- Including a research stage that investigates the best technologies and approaches before building

### Installing GSD

In Warp, type:

```bash
npx get-shit-done-cc@latest
```

You will see a prompt asking: "Where would you like to install it?"

**Option A: Global Install (Recommended)**

Global installation places GSD in your home Claude folder (`~/.claude/`), making it available in every project on your Mac.

```bash
npx get-shit-done-cc --claude --global
```

**Option B: Local Install**

Local installation places GSD only in the current project's `.claude/` folder.

```bash
npx get-shit-done-cc --claude --local
```

Choose Global if you plan to use GSD for multiple projects. Choose Local if you only want it for one specific project.

### Verifying the Installation

After installing, launch Claude Code in any project folder:

```bash
cd ~/your-project-folder
claude --dangerously-skip-permissions
```

Then type inside Claude Code:

```
/gsd:help
```

You should see a list of all available GSD commands. If you see "unknown command," the installation may not have completed correctly. Try running the install command again.

### Updating GSD

GSD is under very active development with frequent improvements. Update regularly:

```bash
npx get-shit-done-cc@latest
```

To see what has changed since your last update, type inside Claude Code:

```
/gsd:whats-new
```

### All GSD Commands

**Project Setup Commands**

| Command | What It Does |
|---------|-------------|
| `/gsd:new-project` | Start a brand-new project. Asks questions about your idea and creates PROJECT.md. |
| `/gsd:init-existing` | Set up GSD on a project that already has code. |
| `/gsd:research-project` | Research technologies and approaches for your project before building. |
| `/gsd:define-requirements` | Define detailed technical requirements based on research. |
| `/gsd:settings` | Configure GSD settings like models, sub-agents, and branch behavior. |

**Planning and Execution Commands**

| Command | What It Does |
|---------|-------------|
| `/gsd:create-roadmap` | Generate a phased roadmap from your project description. |
| `/gsd:plan-phase [number]` | Create detailed task plans for a specific phase. |
| `/gsd:execute-plan` | Start building. A sub-agent implements each task autonomously. |
| `/gsd:status` | See where you are in the project. |

**Management Commands**

| Command | What It Does |
|---------|-------------|
| `/gsd:add-phase` | Add a new phase to the end of the roadmap. |
| `/gsd:insert-phase [n]` | Insert a new phase at a specific position. |
| `/gsd:remove-phase [n]` | Remove a phase and cascade-delete its tasks. |
| `/gsd:complete-milestone` | Archive current milestone, prepare for the next version. |
| `/gsd:add-todo` | Add a to-do item for future reference. |
| `/gsd:codebase-map` | Analyze the existing codebase (generates 7 analysis documents). |

**Utility Commands**

| Command | What It Does |
|---------|-------------|
| `/gsd:help` | Show all available commands. |
| `/gsd:whats-new` | Show changes since your last update. |

---

## Part 8: The Complete Workflow — Start to Finish

This section walks you through the entire process of creating a project from scratch using all the tools together. We will use a real example: building a personal portfolio website.

> **THE VISUAL WORKFLOW SUMMARY**
>
> `new-project` -> `research-project` -> `define-requirements` -> `create-roadmap` -> [`plan-phase N` -> `execute-plan`] (repeat for each phase) -> `complete-milestone`

### Phase 1: Set Up Your Project Folder

Create your project folder in Finder (inside your Developer folder), using a lowercase name like `my-portfolio` or `virtual-valet`. Then navigate to it in Warp:

```bash
cd ~/Developer/my-portfolio
```

### Phase 2: Launch Claude Code with GSD

Start Claude Code in dangerously-skip-permissions mode:

```bash
claude --dangerously-skip-permissions
```

You are now inside Claude Code. The prompt changes to show you are in the Claude Code environment.

### Phase 3: Start a New GSD Project

Type:

```
/gsd:new-project
```

GSD will begin asking you questions about what you want to build. Answer conversationally. For example:

> **GSD:** What are you building?
>
> **You:** I want to build a personal portfolio website that showcases my work, has a contact form, and looks modern and clean. I want it to be a single-page site that scrolls smoothly between sections.

GSD will continue asking questions until it understands your project fully. It will then create a PROJECT.md file that captures everything.

### Phase 4: Research Your Project

Type:

```
/gsd:research-project
```

GSD spawns a sub-agent that researches the best technologies, frameworks, and approaches for your specific project. This is done in a separate context to keep your main session clean. The research results are saved for use in later stages.

### Phase 5: Define Requirements

Type:

```
/gsd:define-requirements
```

Based on the project description and research, GSD creates detailed technical requirements. This ensures that when the AI starts building, it knows exactly what to build and how.

### Phase 6: Create the Roadmap

Type:

```
/gsd:create-roadmap
```

GSD breaks your entire project into numbered phases. Each phase is a logical chunk of work. For a portfolio site, this might look like:

1. Phase 1: Project setup and configuration
2. Phase 2: Layout and navigation
3. Phase 3: Hero section and about section
4. Phase 4: Portfolio/work showcase section
5. Phase 5: Contact form and footer
6. Phase 6: Responsive design and polish

### Phase 7: Plan a Phase

Type:

```
/gsd:plan-phase 1
```

GSD creates detailed task plans for Phase 1. Each plan has a maximum of 3 tasks to keep things focused. Each task includes specific instructions, file paths, and verification steps.

### Phase 8: Execute the Plan

Type:

```
/gsd:execute-plan
```

Now the magic happens. GSD spawns a sub-agent with a fresh 200K-token context window. This sub-agent reads the task plan, implements the code, runs the verification checks, and commits the work to Git. When it finishes a task, it moves to the next one.

You can watch the progress in real-time in Warp as GSD executes each task.

### Phase 9: Review and Continue

After execution completes, check your project status:

```
/gsd:status
```

Then plan and execute the next phase:

```
/gsd:plan-phase 2
/gsd:execute-plan
```

Repeat this cycle for each phase: plan, execute, review. If something is not right, you can tell Claude Code what to fix, or use Git to revert changes.

### Phase 10: Complete the Milestone

When all phases are done:

```
/gsd:complete-milestone
```

This archives your V1 work and prepares the system for V2 if you want to add more features later.

---

## Part 9: Adding an Existing Project to GSD

If you already have a project — whether you built it with Claude in the chat interface, coded it by hand, inherited it from someone else, or developed it with any other tool — you can absolutely bring it into the GSD workflow. You do not need to start from scratch. This section walks you through every step.

### Why This Matters

Many people start projects in Claude's web chat (claude.ai), working back and forth with the AI to build files. That works fine for getting started, but eventually you end up with a collection of files on your computer and no structured system for continuing development. Moving that project into the GSD workflow gives you phased planning, automatic Git commits, context management, and the ability to keep building without the AI losing track of what it's doing.

### Before You Begin: Getting Your Files Ready

**Scenario A: Your project files are on your Mac already**

If you have a folder on your Mac with your project files (code, documents, assets, etc.), you are ready. Just note the folder path. For example: `~/Documents/my-app` or `~/Developer/my-project`.

**Scenario B: Your project files were created in Claude's web chat**

If you built your project in Claude's web chat or desktop app, the files Claude created need to be saved to your Mac. Claude's chat interface lets you download individual files or artifacts. You need to:

1. Create a project folder. Open Warp and type:

   ```bash
   mkdir -p ~/Developer/my-existing-project
   cd ~/Developer/my-existing-project
   ```

2. Download each file from your Claude conversation. Click the download icon on each code artifact or file that Claude created.

3. Move the downloaded files into your project folder. You can drag and drop them from Finder into the folder, or use Warp:

   ```bash
   mv ~/Downloads/index.html ~/Developer/my-existing-project/
   mv ~/Downloads/styles.css ~/Developer/my-existing-project/
   mv ~/Downloads/app.js ~/Developer/my-existing-project/
   ```

4. Organize the files into the correct folder structure if needed. If Claude built a project with folders like `src/`, `public/`, etc., recreate that structure:

   ```bash
   mkdir -p src public
   mv app.js src/
   mv index.html public/
   ```

> **TIP: Ask Claude to Help You Organize**
>
> If you are unsure how to organize your files, you can ask Claude in the web chat: "List all the files you created for this project and show me the folder structure." Then recreate that structure on your Mac.

**Scenario C: Your project is in a GitHub or remote repository**

If your project is hosted on GitHub, GitLab, or another Git hosting service, clone it to your Mac:

```bash
cd ~/Developer
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
```

Your project already has Git history, which is great — GSD will work with it.

### Step-by-Step: Bringing an Existing Project into GSD

**Step 1: Navigate to Your Project Folder**

Open Warp and navigate to your project:

```bash
cd ~/Developer/my-existing-project
```

**Step 2: Initialize Git (If Not Already Done)**

Check if your project already has Git:

```bash
git status
```

If you see "fatal: not a git repository," you need to tell Git to start tracking this folder (this creates a hidden record of changes — called a "repository" — inside the folder):

```bash
git init
git add .
git commit -m "Initial commit: existing project files"
```

- `git init` — creates a new Git repository in this folder (a one-time setup step)
- `git add .` — tells Git to include all existing files in the first save
- `git commit -m "..."` — saves a snapshot of those files with a short description

If `git status` shows information about your repository, Git is already set up and you can skip this step.

> **IMPORTANT: Commit Before You Start**
>
> Always commit your current files to Git before starting GSD. This gives you a clean snapshot to return to if anything goes wrong. Think of it as taking a photo of your project before letting the AI start modifying it.

**Step 3: Launch Claude Code**

```bash
claude --dangerously-skip-permissions
```

**Step 4: Map Your Codebase**

This is the critical first step for existing projects. Type:

```
/gsd:map-codebase
```

GSD spawns multiple sub-agents that work in parallel to analyze your entire codebase. They produce seven detailed documents saved to `.planning/codebase/`:

- **Architecture overview** — how your project is structured
- **Technology stack** — what languages, frameworks, and libraries you use
- **Code patterns** — conventions and patterns found in your code
- **Component map** — what each file and module does
- **Data models** — how data flows through your application
- **API surface** — endpoints, interfaces, and external integrations
- **Concerns and technical debt** — issues or risks the AI identified

This process takes a few minutes depending on the size of your project. Let it finish completely. These documents are loaded automatically during all future planning, so the AI always understands your existing code before making changes.

> **WHY THIS STEP IS ESSENTIAL**
>
> Without `/gsd:map-codebase`, the AI would be building on top of code it does not understand. It would likely duplicate functionality, use inconsistent patterns, or break existing features. The codebase map gives every sub-agent a complete picture of what already exists.

> **DO NOT SKIP STEP 4**
>
> The most common mistake people make when adding an existing project to GSD is skipping `/gsd:map-codebase`. Without it, the AI does not know your codebase's patterns and conventions. It will write code that feels disconnected from what already exists. Always map first.

**Step 5: Start a New Project Definition**

Now that GSD understands your code, type:

```
/gsd:new-project
```

GSD will ask you questions, but because it has already analyzed your codebase, the questions will be different from a greenfield project. Instead of asking what technologies to use (it already knows), it will focus on:

- What do you want to add or change?
- What is the next set of features you want to build?
- Are there bugs or issues you want to fix?
- What is the overall direction for this next phase of work?

Answer conversationally. Tell it what you want to do next with your project. GSD creates a PROJECT.md that captures both what already exists and what you want to build.

**Step 6: Research, Requirements, and Roadmap**

From here, the workflow is the same as a new project:

```
/gsd:research-project
/gsd:define-requirements
/gsd:create-roadmap
```

The key difference is that the AI now factors in your existing code when creating the roadmap. It will not re-create things that already exist. The phases will focus on what is new or needs to change.

**Step 7: Plan and Execute**

Plan and build just like a new project:

```
/gsd:plan-phase 1
/gsd:execute-plan
```

Each sub-agent that executes tasks will have access to the codebase map documents, so it knows your conventions, your patterns, and where things belong.

### Quick Mode: For Small Changes

If you do not need a full phased roadmap and just want to make a quick fix or add a small feature to your existing project, GSD has a shortcut:

```
/gsd:quick
```

GSD will ask you what you want to do. For example:

> **GSD:** What do you want to do?
>
> **You:** Add a dark mode toggle to the settings page

GSD creates a mini-plan, executes it, and commits it — all with atomic Git commits and state tracking, but without the overhead of a full roadmap. Use this for bug fixes, small features, configuration changes, or one-off tasks.

### New Milestone: When You Finish a Version

After completing all the phases of your current work, type:

```
/gsd:complete-milestone
```

Then, when you are ready to start the next round of improvements:

```
/gsd:new-milestone
```

This starts a fresh planning cycle for V2, V3, etc. — same flow as `/gsd:new-project` but it already knows your codebase. Each milestone is a clean cycle: define what you want, build it, ship it.

### The Existing Project Workflow at a Glance

| Step | Command | What Happens |
|------|---------|-------------|
| 1. Go to project folder | `cd ~/Developer/your-project` | Navigate to existing code |
| 2. Initialize Git (if needed) | `git init && git add . && git commit -m "Initial"` | Tell Git to start tracking this folder (only if not already a Git repo) |
| 3. Launch Claude Code | `claude --dangerously-skip-permissions` | Start the AI in your project |
| 4. Map existing code | `/gsd:map-codebase` | AI analyzes your entire codebase |
| 5. Define next goals | `/gsd:new-project` | Tell GSD what you want to build next |
| 6. Research | `/gsd:research-project` | AI investigates best approaches |
| 7. Requirements | `/gsd:define-requirements` | Define technical requirements |
| 8. Roadmap | `/gsd:create-roadmap` | Break work into phases |
| 9. Plan + Execute | `/gsd:plan-phase N` + `/gsd:execute-plan` | Build each phase |
| 10. Quick fix (optional) | `/gsd:quick` | Small changes without full planning |
| 11. Finish version | `/gsd:complete-milestone` | Archive and prep for next version |

---

## Part 10: Tier-Specific Workflow Strategies

Your Claude subscription tier directly affects how you should use this workflow. Here are specific strategies for each tier.

### Pro Tier Strategy ($20/month)

**Your constraint:** Roughly 5x the free tier's usage. You will likely hit rate limits during extended building sessions.

**Recommended approach:**

- Plan before you build. Do `/gsd:new-project` and `/gsd:research-project` in one session.
- Do `/gsd:create-roadmap` in the same session if possible.
- Take a break. Let your usage window reset.
- Come back and do `/gsd:plan-phase` and `/gsd:execute-plan` for 1-2 phases per session.
- Use GSD's "budget" profile (`/gsd:settings`) to use lighter models for execution tasks.
- Close Claude Code when not actively building. Idle sessions still consume tokens.

> **PRO TIP FOR PRO TIER**
>
> In GSD settings, disable sub-agents for research and debugging if you are hitting limits frequently. This uses fewer tokens per operation. You trade some quality for more capacity.

### Max 5x Strategy ($100/month)

**Your constraint:** 25x the free tier's usage. You can comfortably work through a full GSD project in a single day.

**Recommended approach:**

- Use the "balanced" profile in GSD settings — strong models for planning, mid-tier for execution.
- Enable sub-agents for research (they produce significantly better results).
- Plan and execute 3-4 phases per session.
- You can leave Claude Code running during longer build processes.

### Max 20x Strategy ($200/month)

**Your constraint:** 100x the free tier's usage. Rate limits are rarely a concern.

**Recommended approach:**

- Use the "quality" profile in GSD settings — the most powerful models for everything.
- Enable all sub-agents (research, debugging, codebase mapping).
- Run the entire workflow from new-project to complete-milestone in a single extended session.
- Use `/gsd:codebase-map` liberally to keep the AI's understanding of your project current.
- Run multiple projects if needed.

### GSD Model Profiles Explained

| Profile | Planning Model | Execution Model | Best For |
|---------|---------------|-----------------|----------|
| Quality | Strongest (e.g., Claude Sonnet 4.6 or Opus 4.6) | Strongest | Max tiers, critical projects |
| Balanced | Strong | Mid-tier | Max 5x, most projects |
| Budget | Mid-tier | Lightweight | Pro tier, high-volume work |

Change your profile inside Claude Code:

```
/gsd:settings
```

Then select your preferred profile.

---

## Part 11: Troubleshooting & FAQ

### Installation Issues

**"command not found: claude"**

This means your shell cannot find the Claude Code binary. Fix it:

```bash
echo 'export PATH="$HOME/.local/bin:$HOME/.claude/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc
claude --version
```

**"command not found: npx"**

This means Node.js is not installed or not in your PATH. Reinstall:

```bash
brew install node
source ~/.zshrc
```

**GSD commands not recognized**

If `/gsd:help` returns an error inside Claude Code:

1. Exit Claude Code (type `/exit` or press Ctrl+C).
2. Re-run the GSD installer: `npx get-shit-done-cc@latest`
3. Choose global install.
4. Re-launch Claude Code and try `/gsd:help` again.

### Runtime Issues

**Claude Code is slow or unresponsive**

- Check your internet connection.
- You may have hit a rate limit. Type `/exit` and wait for the window to reset.
- Run: `claude doctor` — this diagnoses common issues.

**GSD execution stops mid-phase**

- Type `/gsd:status` to see where it stopped.
- Type `/gsd:execute-plan` again to resume from where it left off.
- If the problem persists, check the Git log: `git log --oneline -10`

### Frequently Asked Questions

**Q: Do I need to know how to code?**
A: No. GSD was specifically designed for non-coders. You describe what you want in plain English, and the system builds it.

**Q: Can I use the default Mac Terminal instead of Warp?**
A: Yes. All commands work the same. Warp just makes the experience nicer.

**Q: Can I use VS Code, Cursor, or another editor to view my files?**
A: Yes. Any code editor or text editor works fine for viewing the files Claude Code creates. You do not need a specific editor for this workflow.

**Q: What if I want to undo something the AI built?**
A: GSD commits every task to Git individually. Use `git log --oneline` to find the commit you want to revert to, then use `git reset --hard [commit-hash]` to go back to that state.

**Q: Claude keeps saying it did something but when I check, it didn't actually make the changes. What's going on?**
A: This is a known behavior called "lazy completion" — Claude's system prompt has many instructions to be minimal and terse, which can cause it to shortcut work and report success without actually executing. Two fixes:

1. **Disable Adaptive Thinking** — add this environment variable to your shell profile (`~/.zshrc` on Mac):
```bash
echo 'export claude_code_disable_adaptive_thinking=1' >> ~/.zshrc
source ~/.zshrc
```
This prevents Claude from deciding "this is simple, I'll think less" and skipping work.

2. **Set Effort to Max** — at the start of each session, type:
```
/effort max
```
This forces full reasoning depth on every request. More tokens used per response, but you get actual thoroughness.

Both settings apply to the CLI. The environment variable also affects the desktop app if launched from your shell.

**Q: How do I make Claude work harder and produce more thorough code?**
A: Beyond the fixes above, you can also:
- Add instructions to your global `~/.claude/CLAUDE.md` file (e.g., "Make BOLD changes using proven patterns rather than small incremental tweaks")
- Use the two-pass rule: if an approach fails twice, delegate to a specialist agent instead of letting Claude keep guessing
- Run `/effort max` at session start — this persists for the session

**Q: How much does this all cost?**
A: Warp is free. Claude Pro is $20/month (required minimum). GSD is free and open source. The minimum total cost is $20/month.

**Q: Does this work on MacBook Air?**
A: Yes. Everything in this manual works on MacBook, MacBook Air, MacBook Pro, iMac, and Mac Mini. The tools are not hardware-intensive — the AI processing happens on Anthropic's servers, not your Mac.

**Q: Can I use this on Windows or Linux?**
A: Warp and Claude Code both support Windows and Linux. GSD works on all three platforms. This manual is written for macOS, but the commands are almost identical on other platforms.

---

## Part 12: Connecting Obsidian (Your Second Brain)

Obsidian is a markdown-based knowledge management app — a "second brain" where you store notes, ideas, research, and brain dumps. By connecting it to Claude Code (and optionally Claude Co-Work on the web), Claude can read your notes, search your vault, and create new notes directly. This means you can brain dump ideas into Obsidian anytime, and Claude will naturally have that context in future sessions without you having to re-explain anything.

### 12.1 Connecting via MCP (Model Context Protocol)

#### Prerequisites

- Obsidian installed (https://obsidian.md — free)
- A vault created (Obsidian will prompt you to create one on first launch)
- Claude Code installed and working

#### How to Install

**Step 1: Install two Obsidian community plugins**

Open Obsidian -> Settings (gear icon) -> Community Plugins -> Turn on community plugins -> Browse

Install and enable both of these:

1. **Local REST API** (by Adam Coddington) — gives external tools secure access to your vault
2. **MCP Tools** (by Jack Steam) — creates the MCP bridge between Obsidian and AI tools

**Step 2: Copy your API key**

After enabling Local REST API:

- Go to Settings -> Local REST API
- You'll see an API key displayed — copy it (it's a long string of letters and numbers)
- Keep this somewhere safe; you'll need it in the next step

**Step 3: Install the MCP server**

In the MCP Tools plugin settings:

- Click **"Install Server"**
- The plugin will download a server binary into your vault's `.obsidian/plugins/mcp-tools/bin/` folder
- It will also auto-configure Claude Desktop if you have it installed

**Step 4: Connect to Claude Code globally**

This is the step that makes it work in Claude Code (not just Claude Desktop). You need to edit Claude Code's config file.

*Option A — Ask Claude to do it:*

> "Add the Obsidian MCP server to my global Claude Code config. The server binary is at [your vault path]/.obsidian/plugins/mcp-tools/bin/mcp-server and the API key is [your key]."

*Option B — Do it manually:*

Open `~/.claude.json` in any text editor and find the `"mcpServers"` section near the bottom of the file. Add the Obsidian entry:

```json
"mcpServers": {
    "obsidian": {
      "command": "/Users/YOUR_USERNAME/Documents/Obsidian Vault/.obsidian/plugins/mcp-tools/bin/mcp-server",
      "env": {
        "OBSIDIAN_API_KEY": "your_api_key_here"
      }
    }
}
```

**IMPORTANT:** Replace `YOUR_USERNAME` with your actual macOS username, adjust the vault path if yours is different, and paste your actual API key.

If you already have other MCP servers in that section (like Figma), add Obsidian as another entry with a comma between them.

**Step 5: Restart Claude Code**

Exit Claude Code and relaunch it (or run `/clear` and start a new session). The Obsidian MCP tools should now be available.

**Step 6: Test the connection**

In Claude Code, ask:

> "Can you see my Obsidian vault? List what's in it."

Claude should be able to list your vault's contents.

#### What You Can Do With It

Once connected, you can:

- **Brain dump freely** — jot ideas, notes, research into Obsidian anytime, and Claude has access next session
- **Ask Claude to check your notes** — "What did I write about X?" and Claude searches your vault
- **Have Claude create notes** — "Save this research to my Obsidian vault" and Claude writes a new note
- **Cross-reference** — Claude can pull context from your notes while working on code or projects

#### Where Things Live

| What | Location |
|------|----------|
| Obsidian vault | `~/Documents/Obsidian Vault/` (or wherever you created it) |
| MCP server binary | `[vault]/.obsidian/plugins/mcp-tools/bin/mcp-server` |
| Claude Code config | `~/.claude.json` (global MCP servers section) |
| Claude Desktop config | `~/Library/Application Support/Claude/claude_desktop_config.json` (auto-configured) |

#### Troubleshooting

- **"Obsidian tools not available"** — Make sure Obsidian is open and both plugins are enabled. Restart Claude Code.
- **"Connection refused"** — The Local REST API plugin may not be running. Check Obsidian -> Settings -> Local REST API -> make sure it's enabled.
- **Wrong vault path** — If you moved your vault or named it differently, update the path in `~/.claude.json`.

#### Migrating Existing Notes

**Coming from Evernote:**

- Export notebooks from Evernote as `.enex` files
- In Obsidian: Settings -> Core Plugins -> Importer -> Enable -> Import -> select Evernote and your `.enex` files
- Obsidian converts them to markdown automatically

**Migrating PDF conversations or research:**

- Ask Claude: "Convert my PDF files in [folder] to markdown for Obsidian"
- Claude can batch-convert PDFs to markdown, dramatically reducing file size

#### Source

- **Obsidian:** https://obsidian.md (free for personal use)
- **MCP Tools plugin:** https://github.com/jacksteamdev/obsidian-mcp-tools
- **Local REST API plugin:** https://github.com/coddingtonbear/obsidian-local-rest-api

---

### 12.2 Obsidian CLI — Official Command Line Interface (Recommended)

The official Obsidian CLI (added in v1.12.4, February 2026) gives Claude Code direct terminal access to your vault — 100+ commands for reading, writing, searching, and manipulating notes. It's faster, more capable, and more scriptable than the MCP approach. **This is now the recommended way for Claude Code to interact with your vault.**

The MCP connection (documented above) still works and is still needed for Claude Co-Work (web), since Co-Work can't run terminal commands. But for Claude Code sessions, the CLI is superior.

#### Prerequisites

- Obsidian v1.12.4 or later (check: open Obsidian -> Settings -> About)
- Obsidian must be running (CLI auto-launches it if not)

#### How to Install

**Step 1: Enable the CLI in Obsidian**

Open Obsidian -> Settings -> General -> Advanced -> toggle **Command line interface** ON -> click **"Register CLI"**

This adds the `obsidian` binary to your system PATH automatically.

**Step 2: Verify in terminal**

Open Warp and run:

```bash
obsidian version
```

You should see something like `1.12.7 (installer 1.12.7)`. If you get "command not found," add this to your `~/.zshrc`:

```bash
export PATH="$PATH:/Applications/Obsidian.app/Contents/MacOS"
```

Then run `source ~/.zshrc` and try again.

**Step 3: Test vault access**

```bash
obsidian vaults          # Should show your vault name(s)
obsidian files | head    # Should list files in your vault
obsidian daily:read      # Should show today's daily note
```

#### What You Can Do With It

| Command | What It Does |
|---------|-------------|
| `obsidian files` | List all files in vault |
| `obsidian read file="path/note.md"` | Read a note's content |
| `obsidian create name="path" content="text"` | Create a new note |
| `obsidian append file="path" content="text"` | Add to end of a note |
| `obsidian prepend file="path" content="text"` | Add after frontmatter |
| `obsidian move file="old" to="new"` | Move/rename (auto-updates wikilinks!) |
| `obsidian delete file="path"` | Move to trash |
| `obsidian search query="text" format=json` | Full-text search with JSON output |
| `obsidian tags` | List all tags in vault |
| `obsidian links file="path"` | Show outgoing links from a note |
| `obsidian backlinks file="path"` | Show incoming links to a note |
| `obsidian orphans` | Find notes with no backlinks |
| `obsidian unresolved` | Find broken wikilinks |
| `obsidian properties file="path"` | View frontmatter/metadata |
| `obsidian property:set file="path" name="key" value="val"` | Set a frontmatter field |
| `obsidian daily` | Open/create today's daily note |
| `obsidian daily:read` | Read today's daily note |
| `obsidian daily:append content="text"` | Append to today's daily note |
| `obsidian plugins` | List installed plugins |
| `obsidian eval code="js_expression"` | Execute JavaScript against Obsidian's API |

**Output formats** — most commands support `format=` for scripting:
`json`, `csv`, `tsv`, `md`, `paths`, `yaml`, `text` (default), `tree`

**Scripting example:**

```bash
# Search vault and pipe to jq
obsidian search query="TODO" format=json | jq '.[].file'

# Bulk set a property on tagged files
obsidian tag tag="#archive" | xargs -I {} obsidian move file="{}" to="Archive/"
```

#### CLI vs MCP — When to Use Which

| Environment | Use | Why |
|-------------|-----|-----|
| **Claude Code** (terminal) | CLI (`obsidian` commands via Bash) | 100+ commands, JSON output, scriptable, faster |
| **Claude Co-Work** (web) | MCP (Obsidian MCP server) | Co-Work can't run terminal commands, MCP is the only option |
| **Claude Desktop** | Either | Both work, CLI is more capable |

Both hit the same vault — they're just different doors. Your MCP setup still works and should stay configured for Co-Work sessions.

#### Where Things Live

| What | Location |
|------|----------|
| CLI binary | `/Applications/Obsidian.app/Contents/MacOS/obsidian` (auto-added to PATH) |
| Your vault | `~/Documents/Obsidian Vault/` (or wherever you created it) |
| MCP config (still active) | `~/.claude.json` -> `mcpServers` -> `obsidian` |

#### Source

- **Official docs:** https://obsidian.md/help/cli
- **Requires:** Obsidian v1.12.4+ (GA release February 27, 2026)

---

### 12.3 The 12 Vault Skills — Obsidian + Claude Code Thinking Tools

A set of 12 slash commands that turn your Obsidian vault into an active thinking partner. Each command uses the Obsidian CLI to read, search, and analyze your notes in different ways — from morning planning to idea generation to end-of-day capture.

Inspired by Internet Vin's "Obsidian + Claude Code Codebook" — adapted and installed as Claude Code skills.

#### The 12 Commands

| Command | What It Does | When to Use |
|---------|-------------|-------------|
| `/vault-context` | Load your full life/work state into Claude's context | Session start — "know everything about me" |
| `/vault-today` | Generate a prioritized plan for today from daily notes + tasks | Morning planning |
| `/vault-trace [topic]` | Track how a specific idea evolved over time | See the arc of your thinking |
| `/vault-connect [A] [B]` | Find unexpected links between two topics | When two ideas seem related but you can't see how |
| `/vault-ghost [question]` | Answer a question the way you would, in your voice | Externalize your thinking, draft responses |
| `/vault-challenge [topic]` | Find contradictions and weak points in your beliefs | Before big decisions, stress-testing ideas |
| `/vault-ideas` | Scan for emerging patterns, generate idea report | When you want fresh ideas from your notes |
| `/vault-graduate` | Promote half-formed daily note ideas into standalone notes | Weekly review |
| `/vault-closeday` | End-of-day capture: progress, new ideas, carryover | End of day, clear your head |
| `/vault-drift` | Surface recurring themes you haven't consciously noticed | When you sense something emerging but can't name it |
| `/vault-emerge` | Find idea clusters ready to become projects | When scattered thoughts are starting to cluster |
| `/vault-schedule` | Map your stated priorities to actual time blocks | Weekly planning |

#### How They Were Installed

Each skill is a `SKILL.md` file in its own directory under `~/.claude/skills/`:

```
~/.claude/skills/vault-context/SKILL.md
~/.claude/skills/vault-today/SKILL.md
~/.claude/skills/vault-trace/SKILL.md
~/.claude/skills/vault-connect/SKILL.md
~/.claude/skills/vault-ghost/SKILL.md
~/.claude/skills/vault-challenge/SKILL.md
~/.claude/skills/vault-ideas/SKILL.md
~/.claude/skills/vault-graduate/SKILL.md
~/.claude/skills/vault-closeday/SKILL.md
~/.claude/skills/vault-drift/SKILL.md
~/.claude/skills/vault-emerge/SKILL.md
~/.claude/skills/vault-schedule/SKILL.md
```

Each file has YAML frontmatter (name + description) and detailed instructions telling Claude how to use the Obsidian CLI to accomplish the task. Claude auto-discovers these — no configuration needed beyond creating the files.

**Skills that write to your vault** (`/vault-graduate`, `/vault-closeday`) are designed to ask for confirmation before creating or appending notes.

#### Note on Co-Work

These skills are Claude Code only (they need terminal access to run CLI commands). For Co-Work, the same concepts work but you'd need to describe what you want in natural language and let Claude use the Obsidian MCP tools instead. The prompts from each skill could be saved as custom instructions in a Co-Work Project if you want similar behavior there.

#### Source

- **Concept:** Internet Vin's "Obsidian + Claude Code Codebook" — https://www.internetvin.com
- **Installed:** March 25, 2026

---

### 12.4 Connecting Obsidian to Claude Co-Work (Web)

Claude Co-Work (claude.ai web interface) is separate from Claude Code (terminal). Co-Work can't run terminal commands, so it needs the Obsidian MCP server (documented above in section 12.1) to access your vault.

#### How It Works

Co-Work sessions that are part of a **Project** can have MCP servers attached. The Obsidian MCP server gives Co-Work tools like `search_vault`, `get_vault_file`, `create_vault_file`, etc. — a smaller set than the CLI's 100+ commands, but enough for reading, searching, and writing notes.

#### Key Differences from Claude Code

| Feature | Claude Code (CLI) | Co-Work (MCP) |
|---------|-------------------|---------------|
| Available commands | 100+ | ~15 MCP tools |
| Search output | JSON, CSV, YAML, etc. | Tool-specific format |
| Scripting/piping | Full shell scripting | Not available |
| Vault skills (/vault-*) | All 12 work | Not available (use natural language instead) |
| Backlinks/orphans | Built-in commands | Limited |
| Frontmatter editing | `property:set` command | Manual note editing |

#### Setup in Co-Work

The MCP connection to Obsidian is configured in `~/.claude.json` (global) or in the Co-Work Project settings. If the MCP was set up following section 12.1 above, it should already be available in Co-Work Projects.

To verify: Open a Co-Work Project -> check that Obsidian tools appear in the available tools list.

#### What Co-Work Can Do With Obsidian

- Search your vault for specific topics
- Read note contents
- Create new notes
- Simple text searches (no backlink traversal or link graph analysis)
- Append to existing notes

#### What You Set Up in Co-Work Stays in Co-Work

Claude Code and Co-Work are completely separate environments. They don't share:

- Skills or slash commands
- Settings or permissions
- Session history or memory
- MCP configurations (though both can connect to the same MCP servers)

The vault itself is shared (same files on disk), but the tools used to access it are different.

---

### 12.5 Using Obsidian as a Project Hub (Recommended Structure)

Once Obsidian is connected via MCP and CLI, the question becomes: what should live in your vault versus in your project repositories?

#### The Hybrid Rule

**Obsidian holds strategic knowledge** — decisions, research, meeting notes, cross-project thinking, daily planning, idea incubation.

**Project repos hold technical state** — all `.planning/` GSD state, `CLAUDE.md`, phase artifacts, code, codebase intelligence.

**Why this split?** GSD skills (all 29 of them) hardcode relative paths to `.planning/` from the project root. Moving planning files into Obsidian breaks every GSD command. Don't do it. Let each tool do what it's best at.

#### Recommended Vault Structure

```
Your_Vault/
  Projects/                # One folder per project
    Project-A/             # Decision log, research, competitive analysis
    Project-B/             # Same structure
    Corporate/             # Cross-project business docs
  Calendar/
    Daily/                 # YYYY-MM-DD.md daily notes
  Templates/               # Daily Note, Decision, Meeting Notes, Research
  Resources/               # Reference material, API docs, design guides
  Archive/                 # Completed/inactive projects
```

Each project folder contains:
- **Decision Log** — key decisions with context, options considered, and rationale
- **Research notes** — market research, competitive analysis, technical investigations
- **Meeting notes** — investor meetings, team discussions, vendor calls

#### Daily Notes Workflow

Daily notes are the bridge between sessions:

1. **Session start:** Run `/vault-today` — pulls your daily note and recent context into Claude's awareness
2. **During work:** Decisions and ideas get captured in the daily note automatically
3. **Session end:** Run `/vault-closeday` — summarizes what happened, captures carryover items

The daily note template should have sections per project so you can track work across multiple concurrent projects in one place.

#### Templates to Create

Set up these four templates in Obsidian (Settings → Templates → Template folder → point to your Templates folder):

| Template | When to Use |
|----------|-------------|
| Daily Note | Every day — work log, decisions, ideas, blockers |
| Decision | When making a choice that affects project direction |
| Meeting Notes | Investor meetings, team syncs, vendor calls |
| Research | Market research, technical investigations, API evaluations |

#### Memory Stack — Where Each Tool Fits

With Obsidian connected, you have a clean separation of concerns:

| Layer | Tool | What It Stores | Persistence |
|-------|------|---------------|-------------|
| Session state | Claude auto-memory (`~/.claude/projects/*/memory/`) | Working rules, preferences, project snapshots | Local files, per-project |
| Cross-session inference | Honcho plugin | Behavioral patterns, stable preferences | Cloud, survives resets |
| Strategic knowledge | Obsidian vault | Decisions, research, ideas, daily planning | Local markdown, human-readable |
| Conversation history | MemPalace (optional) | Verbatim past conversations, semantic search | Local ChromaDB |

The key insight: Claude's auto-memory stores *rules about how to work*. Obsidian stores *what was decided and why*. They complement each other — don't duplicate content across both.

---

## Part 13: Expert Sub-Agents & Additional Skills

### 13.1 Installing 136 Expert Sub-Agents (Codex Experts)

#### What This Is

A collection of 136 specialized AI sub-agents converted from the open-source [awesome-codex-subagents](https://github.com/VoltAgent/awesome-codex-subagents) repository. Each agent is an expert in a specific domain — backend development, security auditing, React, PostgreSQL, prompt engineering, UX research, and more. When installed, Claude can delegate specialized tasks to these experts instead of doing everything as a generalist.

Think of it like giving Claude a company of 136 specialists to call on. Claude becomes the project manager who knows which expert to bring in for each task.

#### The 10 Categories (136 agents total)

| Category | Agents | Examples |
|----------|--------|----------|
| Core Development | 12 | backend-developer, frontend-developer, mobile-developer, api-designer |
| Language Specialists | 27 | react-specialist, typescript-pro, python-pro, swift-expert |
| Infrastructure & DevOps | 16 | devops-engineer, docker-expert, kubernetes-specialist, terraform-engineer |
| Quality & Security | 16 | code-reviewer, security-auditor, debugger, penetration-tester, qa-expert |
| Data & AI | 12 | prompt-engineer, llm-architect, postgres-pro, ml-engineer |
| Developer Experience | 13 | refactoring-specialist, mcp-developer, documentation-engineer |
| Specialized Domains | 12 | game-developer, fintech-engineer, payment-integration |
| Business & Product | 11 | product-manager, ux-researcher, legal-advisor, technical-writer |
| Meta & Orchestration | 12 | task-distributor, multi-agent-coordinator, workflow-orchestrator |
| Research & Analysis | 7 | competitive-analyst, market-researcher, trend-analyst |

#### How to Install

**Step 1: Clone the source repository**

Open Warp and run:

```bash
cd /tmp
git clone https://github.com/VoltAgent/awesome-codex-subagents.git
```

**Step 2: Create the conversion script**

Ask Claude to create the conversion script by saying:

> "Create a Python script that converts all the TOML agent files in /tmp/awesome-codex-subagents/categories/ into Claude Code markdown instruction files. Save the converted agents to ~/.claude/agents/codex-experts/ organized by category. Include an INDEX.md and INDEX.json for quick lookup."

Or paste this command to create and run it yourself:

```bash
python3 /tmp/convert-agents.py
```

The conversion script reads each `.toml` file, extracts the agent's name, description, working instructions, and quality checks, then writes a markdown file Claude can read when dispatching sub-agents.

**Step 3: Create the router skill**

Create the directory:

```bash
mkdir -p ~/.claude/skills/codex-experts
```

Then create `~/.claude/skills/codex-experts/SKILL.md` with a skill definition that tells Claude how to find and dispatch these experts. The skill should:

- Have the name "codex-experts"
- Describe when to use it (code review, security audit, backend dev, etc.)
- Explain the 3-step dispatch process: find expert -> read instructions -> spawn agent
- Include a quick reference table of the most commonly needed experts

**Step 4: Verify installation**

In Claude Code, you should now see `codex-experts` in your available skills. Ask Claude:

> "What expert sub-agents do you have available?"

Claude should reference the 136 agents across 10 categories.

#### Where Things Live After Installation

| What | Location |
|------|----------|
| Agent instruction files | `~/.claude/agents/codex-experts/{category}/{name}.md` |
| Full index (human-readable) | `~/.claude/agents/codex-experts/INDEX.md` |
| Machine-readable index | `~/.claude/agents/codex-experts/INDEX.json` |
| Router skill | `~/.claude/skills/codex-experts/SKILL.md` |

#### How Claude Uses Them

When Claude encounters a task that matches an expert's specialty, it:

1. Reads the expert's instruction file (working mode, focus areas, quality checks)
2. Spawns a sub-agent with those expert instructions baked into the prompt
3. Adds project-specific context (your files, requirements, constraints)
4. Receives the expert's findings or implementation
5. Synthesizes the results before presenting to you

You don't need to do anything special — Claude automatically knows when to bring in a specialist.

#### Source

- **GitHub:** https://github.com/VoltAgent/awesome-codex-subagents
- **License:** MIT (free to use)
- **Originally designed for:** OpenAI Codex — converted for Claude Code

---

### 13.2 Installing Dream Memory Consolidation

#### What This Is

Dream Memory Consolidation is a skill that lets Claude perform a "sleep cycle" on its memory files. Just like how humans consolidate memories during sleep — reorganizing, pruning, and strengthening important connections — this skill has Claude review all its memory files, merge duplicates, fix stale information, remove contradictions, and keep the memory index lean and fast.

Over time, Claude's memory files accumulate session logs, duplicate facts, and outdated information. Running `/dream` periodically keeps everything tight so future sessions load faster and Claude has a clearer picture of your project.

#### How to Install

**Step 1: Create the skill directory**

```bash
mkdir -p ~/.claude/skills/dream
```

**Step 2: Create the skill file**

Create `~/.claude/skills/dream/SKILL.md` with the dream consolidation instructions. The skill should define four phases:

1. **Orient** — Read the memory directory, check MEMORY.md index, skim existing files
2. **Gather Recent Signal** — Find new information worth persisting from session logs, git history, and existing memories that have drifted from reality
3. **Consolidate** — Merge duplicates, convert relative dates to absolute, delete contradicted facts, promote repeated patterns into concise rules
4. **Prune and Index** — Update MEMORY.md to stay under 200 lines, remove stale pointers, resolve contradictions

You can find the original source at:
https://github.com/Piebald-AI/Claude-code-system-prompts/blob/main/system-prompts/agent-prompt-dream-memory-consolidation.md

**Step 3: Verify installation**

In Claude Code, type:

```
/dream
```

Claude should begin the memory consolidation process and return a summary of what was consolidated, updated, or pruned.

#### When to Use It

- **After long sessions** — especially sessions where many decisions were made
- **When Claude seems confused** about project state — memories may be contradicting each other
- **Periodically** — once a week or whenever the MEMORY.md index feels bloated
- **Before starting a new milestone** — clean slate for clean planning

#### What It Does (and Doesn't Do)

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

#### Source

- **GitHub:** https://github.com/Piebald-AI/Claude-code-system-prompts
- **Original concept:** Anthropic's upcoming dream memory feature (adapted for current Claude Code)
- **License:** Open source

---

### 13.3 Installing Impeccable Design Skills (21 Skills)

#### What This Is

A collection of 21 design-focused skills created by Paul Bakaus (pbakaus) that give Claude the ability to systematically audit and improve UI/UX quality. Instead of making vague "make it look better" requests, each skill targets a specific design dimension — typography, color, layout, animation, accessibility, and more. Think of them as a team of specialized design reviewers you can invoke by name.

These skills were built for frontend work and are particularly effective when run in sequence after implementing a new feature. They catch design inconsistencies that generalist code review misses.

#### The 21 Skills

| Command | What It Does | When to Use |
|---------|-------------|-------------|
| `/typeset` | Fix font choices, hierarchy, sizing, weight, readability | Text looks inconsistent, fonts feel wrong |
| `/arrange` | Fix layout, spacing, visual rhythm, grid balance | Spacing feels off, crowded UI, weak hierarchy |
| `/colorize` | Add strategic color using 60/30/10 ratio | Design looks gray, dull, monochromatic |
| `/polish` | Final quality pass — alignment, spacing, consistency | Pre-launch, "something feels off" |
| `/normalize` | Align UI to design system tokens and patterns | Design drift, mismatched styles |
| `/harden` | Add error handling, overflow, i18n, edge cases | Make it production-ready, handle edge cases |
| `/animate` | Add purposeful animations and micro-interactions | Transitions feel abrupt, needs motion |
| `/delight` | Add moments of joy, personality, unexpected touches | Functional but forgettable, needs personality |
| `/overdrive` | Push past limits — shaders, spring physics, 60fps | Want to wow, go all-out, impress |
| `/critique` | UX evaluation with scoring and persona testing | Want honest design assessment |
| `/audit` | Technical checks — a11y, performance, responsive, anti-patterns | Want a scored quality report |
| `/optimize` | Fix performance — loading, rendering, bundle size, images | Slow, laggy, janky |
| `/adapt` | Make responsive across screen sizes and devices | Mobile layouts, breakpoints, viewport |
| `/extract` | Pull reusable components into design system | Repeated patterns, component library |
| `/distill` | Strip to essence, remove unnecessary complexity | Cluttered, too much going on |
| `/clarify` | Fix unclear copy, labels, error messages, instructions | Confusing text, bad error messages |
| `/bolder` | Amplify safe designs to be more visually impactful | Looks bland, generic, too safe |
| `/quieter` | Tone down overstimulating or aggressive designs | Too loud, overwhelming, garish |
| `/onboard` | Design first-run experiences and empty states | New user flows, activation |
| `/frontend-design` | Build distinctive production-grade interfaces | Building new UI from scratch |
| `/visual-preview` | Preview visual changes in external tools | Working with Figma, Luma, design tools |

#### How to Install

The skills are available as a Claude Code plugin:

**Step 1: Install the plugin**

In Claude Code, type:

```
/install-plugin pbakaus/impeccable
```

Or manually clone and install:

```bash
cd /tmp
git clone https://github.com/pbakaus/impeccable.git
cp -r /tmp/impeccable/skills/* ~/.claude/skills/
```

**Step 2: Verify installation**

In Claude Code, type any skill name (e.g., `/typeset`) and Claude should load the skill instructions.

**Step 3 (Optional): Run the one-time setup**

```
/teach-impeccable
```

This gathers your project's design context (colors, fonts, components) and saves it to your AI config file so all future skill invocations have your design system as baseline context.

#### How to Use Them Effectively

**Single skill for a focused fix:**

> "The typography on the dashboard cards is inconsistent. Run `/typeset` on it."

**Sequential pass for comprehensive quality:**

A typical post-feature sequence:
1. `/normalize` — align to design system first
2. `/typeset` — fix type hierarchy
3. `/arrange` — fix layout and spacing
4. `/colorize` — fix color balance
5. `/harden` — handle overflow, edge cases
6. `/polish` — final pass

**Full audit with scoring:**

> "Run `/audit` on the onboarding flow and give me a scored report."

#### What Makes These Different from Generic Prompts

Each skill carries a specific methodology:
- **Structured output** — they produce categorized findings, not vague suggestions
- **Design system awareness** — they check against your tokens, not arbitrary values
- **Anti-pattern detection** — they flag specific known problems (e.g., purple monotone, inconsistent border-radius)
- **Severity classification** — P0 (critical) through P3 (nice-to-have)

#### Where Things Live After Installation

| What | Location |
|------|----------|
| Skill files | `~/.claude/skills/{skill-name}/SKILL.md` |
| Design context (if using teach-impeccable) | Saved to CLAUDE.md or project config |
| Design system docs (if using /design-system) | `DESIGN.md`, `COMPONENTS.md`, `UI-SYSTEM.md` in project root |

#### Source

- **GitHub:** https://github.com/pbakaus/impeccable
- **Author:** Paul Bakaus
- **License:** Open source
- **Installed:** April 2026

---

## Quick Reference: All Commands at a Glance

A single-page reference for every command you will use regularly. Bookmark this page.

### GSD Commands (run inside Claude Code / Warp)

| Command | Alias | What It Does |
|---------|-------|-------------|
| `/gsd:init` | | Initialize GSD on a new or existing project. Creates CLAUDE.md and project scaffolding. |
| `/gsd:resume-work` | `/gsd:progress` | Resume a previous session. Reads STATE.md and picks up exactly where you left off. |
| `/gsd:plan` | | Break a feature or task into a structured plan with phases and steps. |
| `/gsd:execute` | | Execute the current plan step-by-step. GSD tracks progress automatically. |
| `/gsd:status` | | Show where you are in the current plan — what's done, what's next. |
| `/gsd:new` | | Start a new task or sub-project within the current GSD session. |
| `/gsd:create` | | Generate a new file, component, or module as part of the current plan. |
| `/gsd:add` | | Add a step or task to the current plan. |
| `/gsd:complete` | | Mark the current step as done and advance to the next. |
| `/gsd:research` | | Ask GSD to research a topic or codebase before planning. |
| `/gsd:codebase` | | Map and summarize the current codebase structure. |
| `/gsd:map` | | Generate a visual or text map of your project structure. |
| `/gsd:define` | | Define a concept, component, or requirement in project context. |
| `/gsd:insert` | | Insert generated code or content into a specific location. |
| `/gsd:remove` | | Remove a step, file, or component from the plan. |
| `/gsd:quick` | | Run a quick one-off task without creating a full plan. |
| `/gsd:settings` | | View or change GSD configuration for the current project. |
| `/gsd:help` | | List all available GSD commands with descriptions. |
| `/gsd:whats` | | Ask GSD what it is currently working on or what comes next. |

### Claude Code Commands (Warp terminal)

| Command | Flag / Option | What It Does |
|---------|--------------|-------------|
| `claude` | | Start an interactive Claude Code session in the current directory. |
| `claude --version` | | Check which version of Claude Code is installed. |
| `claude --global` | `--global` | Apply a setting or MCP globally across all projects. |
| `claude --local` | `--local` | Apply a setting or MCP to the current project only. |
| `claude --dangerously-skip-permissions` | | Skip permission prompts (use with caution in trusted environments). |
| `claude doctor` | | Run a health check on your Claude Code installation. |
| `claude mcp add --transport stdio` | | Register a new MCP server (e.g. Netlify, Sequential Thinking). |

### Key Phrases That Trigger Skills (Cowork / Claude)

| Phrase / Trigger | Skill | What Happens |
|-----------------|-------|-------------|
| "checkpoint" | session-handoff | Updates CLAUDE.md with session progress. Done in ~2 minutes. |
| "don't lose this" | session-handoff | Full handoff — updates CLAUDE.md + generates a handoff document with opening prompt for next session. |
| "save our progress" | session-handoff | Same as Full Handoff above. |
| "make a Word doc" | docx | Creates a formatted .docx file. |
| "make a presentation" | pptx | Creates or edits a .pptx slide deck. |
| "create a PDF" | pdf | Creates, merges, or extracts content from PDF files. |
| "make a poster / design" | canvas-design | Generates visual art and design as .png or .pdf. |
| "install sequential thinking MCP" | Claude Code AI | Installs the Sequential Thinking MCP server automatically. |

### Obsidian Vault Skills (Claude Code only)

| Command | What It Does |
|---------|-------------|
| `/vault-context` | Load life/work state at session start |
| `/vault-today` | Morning planning from daily notes |
| `/vault-trace [topic]` | Track idea evolution over time |
| `/vault-connect [A] [B]` | Find links between two topics |
| `/vault-ghost [question]` | Answer in your voice from your writing |
| `/vault-challenge [topic]` | Pressure-test beliefs, find contradictions |
| `/vault-ideas` | Generate ideas from vault patterns |
| `/vault-graduate` | Promote daily note ideas to standalone notes |
| `/vault-closeday` | End-of-day capture + carryover |
| `/vault-drift` | Surface recurring themes |
| `/vault-emerge` | Find idea clusters ready to become projects |
| `/vault-schedule` | Map priorities to time blocks |

### Impeccable Design Skills (run inside Claude Code)

| Command | What It Does |
|---------|-------------|
| `/typeset` | Fix font hierarchy, sizing, weight, readability |
| `/arrange` | Fix layout, spacing, visual rhythm, grid balance |
| `/colorize` | Add strategic color using 60/30/10 ratio |
| `/polish` | Final quality pass — alignment, spacing, consistency |
| `/normalize` | Align UI to design system tokens and patterns |
| `/harden` | Error handling, overflow, i18n, edge cases |
| `/animate` | Purposeful animations and micro-interactions |
| `/delight` | Moments of joy, personality, unexpected touches |
| `/overdrive` | Shaders, spring physics, 60fps — go all-out |
| `/critique` | UX evaluation with scoring and persona testing |
| `/audit` | Technical quality checks — a11y, perf, responsive |
| `/optimize` | Fix loading speed, rendering, bundle size |
| `/adapt` | Responsive design across screen sizes and devices |
| `/extract` | Pull reusable components into design system |
| `/distill` | Strip to essence, remove unnecessary complexity |
| `/clarify` | Fix unclear copy, labels, error messages |
| `/bolder` | Amplify safe designs for more visual impact |
| `/quieter` | Tone down overstimulating designs |
| `/onboard` | Design first-run experiences and empty states |
| `/frontend-design` | Build distinctive production-grade interfaces |
| `/visual-preview` | Preview visual changes in external tools |

### Additional Skills

| Tool | Command / Trigger | What It Does |
|------|-------------------|-------------|
| Codex Experts | (automatic — Claude invokes when needed) | 136 specialist sub-agents for expert tasks |
| Dream | `/dream` | Memory consolidation — merge, prune, deduplicate |
| Obsidian MCP | (automatic — for Co-Work web sessions) | Read, search, write notes via MCP |
| Obsidian CLI | (automatic — for Claude Code sessions) | 100+ vault commands via terminal |

### MCP Install Cheat Sheet

For full installation instructions and descriptions of each tool, see Part 6: Skills, Plugins, and MCPs.

| MCP / Tool | How to Install | Where to Get It |
|-----------|---------------|----------------|
| Sequential Thinking | Tell Claude: "please install sequential thinking MCP server" | Installed automatically by Claude Code |
| Figma | Tell Claude: "please install the Figma MCP" + paste your API token | figma.com/developers |
| Gamma | Tell Claude: "please install the Gamma MCP" + paste your API key | gamma.app |
| Netlify | `claude mcp add --transport stdio netlify -- npx -y @netlify/mcp` | netlify.com |
| OpenRouter | Tell Claude your API key and ask it to use OpenRouter | openrouter.ai |
| ACE Data Cloud | git clone + pip install per service (see Part 6) | platform.acedata.cloud |
| Context7 | `/plugins` in Claude Code — search "Context7" and install | Plugin directory |
| Honcho | `/plugins` in Claude Code — search "Honcho" and install | Plugin directory |

All skills installed globally at `~/.claude/skills/` — available across all projects.
Obsidian CLI registered to system PATH — available from any terminal.
Obsidian MCP configured in `~/.claude.json` — available in Claude Code and Co-Work.

---

## Addendum: Session Handoff Skill

The Session Handoff skill protects your work from context loss and session crashes. Copy the content below in its entirety and save it as a file named `session-handoff.skill`. Then install it by opening the Cowork desktop app, going to Settings > Skills, and importing the file.

Once installed, just say "checkpoint" or "don't lose this" at any point during a session and Claude will update your CLAUDE.md and generate a handoff document. Use it aggressively.

```yaml
---
name: session-handoff
description: "Preserves session context and prevents work loss by updating CLAUDE.md and generating handoff documents. Trigger this skill immediately whenever the user says 'checkpoint', 'handoff', 'save our progress', 'update the notes', 'session summary', 'save this', 'don't lose this', or expresses any worry about losing context or the session crashing. Also trigger proactively after any major deliverable is completed. Two modes: Checkpoint (quick mid-session CLAUDE.md update, 2 minutes) and Full Handoff (complete CLAUDE.md update + handoff document for the next session)."
---
```

### Session Handoff Skill

This skill preserves work by keeping CLAUDE.md current and generating handoff documents when needed.

#### Determine Mode

**Checkpoint** (default for "checkpoint", "save this", mid-session saves):
- Read CLAUDE.md, identify what's new or changed, make targeted updates
- Confirm what was updated in 2-3 sentences. Done in under 2 minutes.

**Full Handoff** (for "handoff", "session summary", end-of-session):
- Everything in Checkpoint, plus generate a `Session_Handoff_[Date].md` document
- Provide a `computer://` link to the file

#### Step 1: Read Current State

Read CLAUDE.md completely before making any changes.

#### Step 2: Scan the Conversation

Look for changes across: Projects & Products, People & Contacts, Documents & Deliverables, Decisions Made, Pending Tasks.

#### Step 3: Update CLAUDE.md

Make targeted, surgical updates only. Add new Recent Session Work entries at the TOP of that section.

#### Step 4: Full Handoff Document (Full Handoff mode only)

Generate `Session_Handoff_[MonthDay_Year].md` in the workspace root with:

- Opening Prompt for Next Session (paste this to resume)
- What Was Accomplished
- Where Things Stand (table)
- Pending Tasks (prioritized)
- Key File Locations

#### Step 5: Confirm

- **Checkpoint:** "Checkpoint saved. Updated CLAUDE.md: [2-3 specific things]. Nothing lost."
- **Full Handoff:** "Session captured." + `computer://` link to handoff file.
