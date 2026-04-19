---
name: atlas-setup
version: 1.2.0
description: Guided wizard to install the complete Atlas toolchain on a fresh Claude Code installation. Use when setting up a new machine, onboarding a team member, reinstalling after a reset, or when the user says "set up Atlas", "install everything", "fresh install", "bootstrap my tools", or "atlas-setup". Also use when checking what's installed or verifying the toolchain is complete.
---

# Atlas Setup — Full Toolchain Wizard

**Version:** 1.2.0 | **Repo:** The-Pleroma/playbooks/gsd/atlas-setup/

A guided, step-by-step installer for the Atlas development environment. Checks what's already installed, walks users through each tool category, handles account setup, and verifies everything works. Self-improving — captures fixes and checks for updates.

## What Changed in v1.2.0

The install order was restructured to put the **memory layer before the skills cohort**. Reason: every skill that reads the vault (`vault-today`, `vault-closeday`, the 12 Vault Skills, dream consolidation) fails silently if the vault + MCP + 6-AI-Memory scaffolding isn't in place first. v1.1.0 installed 21+ skills before Obsidian was wired up, so first-run experience was broken.

New structure:

- **Phase A — Base:** prereqs, runtimes, Claude Code, Claude Desktop + Honcho
- **Phase B — Memory foundation:** Obsidian, core MCPs, second-brain-bridge, graphify
- **Phase C — Everything else:** GSD, skills cohort, atlas-setup self-check, per-project

Honcho moved up to Phase A (it's a Claude Desktop plugin, so it belongs with Desktop install). The entire memory scaffold now installs via one command: `~/Developer/second-brain-bridge/bin/install.sh`. No more hand-rolling vault skills or hooks.

Backward compatibility: anyone running atlas-setup v1.1.0 is still fine — the old flow installed everything that v1.2.0 installs, just in a worse order. v1.2.0 is the recommended path for fresh installs.

## Philosophy

- **Check before installing** — never reinstall what's already there
- **Memory layer before skills cohort** — skills that read the vault fail if the vault isn't wired up
- **One command per system** — delegate to `install.sh` scripts where they exist, don't re-implement
- **Group by category** — let users opt into what they need
- **Step-by-step for accounts** — when a tool needs an API key or account, walk through the signup process
- **Verify each install** — confirm it works before moving on
- **Obsidian must be running** — warn users before Phase B

## How to Run

When the user invokes this skill, follow these phases in order. **Do not reorder** — Phase B depends on Phase A outputs (Claude Code auth, Honcho credentials), and Phase C depends on Phase B (vault + MCPs registered).

---

### Phase 0: System Check

Before anything else, detect the environment:

```bash
# Check OS
uname -s  # Darwin = macOS, Linux = Linux

# Check package managers
which brew && brew --version  # macOS
which apt && apt --version    # Linux (Debian/Ubuntu)

# Check Node.js and npm
node --version
npm --version

# Check Python
python3 --version
which python3

# Check existing Claude Code config
cat ~/.claude/settings.json 2>/dev/null | head -5
ls ~/.claude/skills/ 2>/dev/null | wc -l
```

Report what's detected:

```
System: macOS / Linux
Node: vX.X.X / not installed
npm: vX.X.X / not installed
Python: 3.X.X / needs upgrade / not installed
Existing skills: N installed
```

If Node.js is missing, stop and help install it first — everything depends on it.

---

## Phase A — Base (prereqs, runtimes, Claude Code, Desktop + Honcho)

This is the foundation. Nothing in Phase B or C will work until all four of these are in place.

### A.1 macOS prereqs — Homebrew, Warp, zsh baseline

- **Homebrew** — macOS package manager.
  - Check: `which brew && brew --version`
  - Install: `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`
  - Add to PATH (Apple Silicon): `echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zprofile && eval "$(/opt/homebrew/bin/brew shellenv)"`
- **Warp terminal** — modern terminal with AI autocomplete and block-based output.
  - Check: `ls /Applications/Warp.app 2>/dev/null`
  - Install: download from `warp.dev/download`, open the `.dmg`, drag to Applications
  - Set as default: Warp → Settings → General → "Set Warp as default terminal"
- **zsh baseline** — macOS default since Catalina. Confirm with `echo $SHELL` (should be `/bin/zsh`).

### A.2 Runtimes — Node.js, Bun, Python, git, gh

- **Node.js 18+**
  - Check: `node --version`
  - Install: `brew install node`
- **Bun** (optional, for fast JS tooling)
  - Check: `which bun`
  - Install: `brew install oven-sh/bun/bun`
- **Python 3.10+**
  - Check: `python3 --version`
  - Install: `brew install python@3.12 && brew install pipx && pipx ensurepath`
- **git**
  - Check: `git --version`
  - Install (if missing): `brew install git`
- **gh CLI**
  - Check: `which gh`
  - Install: `brew install gh`
  - Authenticate: `gh auth login` → GitHub.com → HTTPS → login via browser
  - Set Git identity: `git config --global user.name "Your Name" && git config --global user.email "you@example.com"`

### A.3 Claude Code CLI

- **What:** Anthropic's command-line AI coding tool.
- **Check:** `claude --version`
- **Install (recommended):** `curl -fsSL https://claude.ai/install.sh | bash && source ~/.zshrc`
- **Alternatives:** `brew install --cask claude-code` or `npm install -g @anthropic-ai/claude-code`
- **Authenticate:** launch `claude` once — it opens a browser login flow
- **Tip:** add `alias cc="claude --dangerously-skip-permissions"` to `~/.zshrc` for GSD workflow
- **Account needed:** Claude Pro or Max subscription, or Anthropic API key with billing

### A.4 Claude Desktop + Honcho

Honcho is a Claude Desktop plugin. Setup begins in Desktop; both Claude Code and Desktop pick up the same credentials.

- **Claude Desktop app**
  - Check: `ls /Applications/Claude.app 2>/dev/null`
  - Install: download from `claude.ai/download`
  - Sign in with the same account used for Claude Code
- **Honcho plugin**
  - What: cross-session memory that persists user preferences and behavioral patterns in the cloud
  - Check: `grep -q "honcho" ~/.claude/settings.json 2>/dev/null`
  - Install (in Claude Desktop or Code):
    1. `/plugin marketplace add plastic-labs/claude-honcho`
    2. `/plugin install honcho@honcho`
    3. `/reload-plugins`
    4. `/honcho:setup` — enter your Honcho API key (get it from honcho.dev)
  - Verify: `/honcho:status` returns connected
  - Note: once configured in Desktop, Claude Code's Honcho plugin reads the same credentials

**Checkpoint — Phase A:** At this point you have: Homebrew, Node, Bun, Python, git, gh (authenticated), Claude Code (authenticated), Claude Desktop (signed in), Honcho (connected). Don't move to Phase B until all of these pass their verify step.

---

## Phase B — Memory foundation (Obsidian, core MCPs, second-brain-bridge, graphify)

**IMPORTANT: Obsidian must be running during this phase.** The MCP server connects to Obsidian's Local REST API — if Obsidian is closed, all vault tools fail silently.

### B.1 Obsidian + vault

- **Verify Obsidian is installed:**
  - `test -d /Applications/Obsidian.app || echo "INSTALL OBSIDIAN FIRST (see manual Part 7)"`
  - If not installed, halt and direct user back to the manual.
- **Create a vault**
  - Default name for new users: `MyVault`
  - For Seph specifically: `The_Pleroma` (already exists at `~/Documents/The_Pleroma/`)
  - Store at `~/Documents/<vault-name>/`
- **Enable Daily Notes core plugin**
  - Settings → Core plugins → Daily Notes → toggle on
  - Settings → Daily Notes → New file location: `Calendar/Daily/`
  - Date format: `YYYY-MM-DD`
- **Verify Obsidian built-in CLI is registered:**
  - `which obsidian` → expected: `/usr/local/bin/obsidian` → `/Applications/Obsidian.app/Contents/MacOS/obsidian-cli`
  - If not found, halt and direct user to manual Part 7 Step 4 (enable Register CLI in Obsidian settings).

### B.2 Core MCPs

Register MCPs at `--scope user` so both Claude Code and Claude Desktop see them.

- **Obsidian MCP** (required for Phase B)
  - Install: `claude mcp add obsidian --transport stdio --scope user -- npx -y @zethictech/obsidian-mcp`
  - Add env: edit `~/.claude.json` → find the obsidian MCP entry → add `"env": {"OBSIDIAN_VAULT": "MyVault"}` (use your actual vault name)
  - Verify: restart Claude Code, then call `mcp__obsidian__get_vault_info`
- **Context7** (always — no account)
  - Install: `claude mcp add context7 --transport stdio --scope user -- npx -y @upstash/context7-mcp`
  - Verify: MCP tool `mcp__context7__resolve-library-id` available
- **Supabase** (optional, if using Supabase for a project)
  - Install via `/plugins` → search "Supabase" → install
  - Account needed: supabase.com + project ref
- **Firecrawl** (optional, for web scraping)
  - Install: `claude mcp add firecrawl --transport stdio --scope user -- npx -y firecrawl-mcp`
  - Account needed: firecrawl.dev API key (free tier: 500 credits)
- **Gamma** (optional, for AI presentations)
  - Install: `claude mcp add gamma --transport stdio --scope user -e GAMMA_API_KEY=<key> -- npx -y @raydeck/gamma-app-mcp`
  - Account needed: gamma.app API key

### B.3 second-brain-bridge — one-command memory scaffold

This is the canonical installer for the Atlas memory layer. It scaffolds `6-AI-Memory/` in your vault, symlinks the `vault-session` and `vault-closeday` skills into `~/.claude/skills/`, installs the PostToolUse Obsidian MCP logger hook, installs the Honcho nightly launchd plist, and prints three paste-in templates (Desktop Profile, Cowork Global, Claude Code CLAUDE.md).

```bash
git clone https://github.com/Seph396/second-brain-bridge ~/Developer/second-brain-bridge
cd ~/Developer/second-brain-bridge
./bin/install.sh --vault-root "$HOME/Documents/MyVault"
```

(Replace `MyVault` with your actual vault name. For Seph: `$HOME/Documents/The_Pleroma`.)

After `install.sh` finishes, it prints three templates. Paste each where the script tells you:

1. **Desktop Profile** — into Claude Desktop → Settings → Profile
2. **Cowork Global** — into Cowork → Settings → Global instructions
3. **Claude Code CLAUDE.md** — append to `~/.claude/CLAUDE.md` (user-level, not project-level)

Repo: https://github.com/Seph396/second-brain-bridge (currently private — use the public URL once it ships publicly).

Verify:

```bash
ls "$HOME/Documents/MyVault/6-AI-Memory/"  # should show Daily/, _sessions/, Honcho/, Decisions/
ls ~/.claude/skills/vault-session/        # should be a symlink
ls ~/.claude/skills/vault-closeday/       # should be a symlink
launchctl list | grep honcho              # should show the nightly launchd job
```

### B.4 graphify — knowledge graph over the vault

- **What:** turns any input (code, docs, papers, images) into a clustered knowledge graph with HTML + JSON + audit report output.
- **Check:** `which graphify`
- **Install:**
  ```bash
  pipx install graphifyy==0.4.23
  graphify install
  ```
- **Verify:** `graphify --version` returns `0.4.23`

**Checkpoint — Phase B:** Vault exists with `6-AI-Memory/` scaffolded, Obsidian MCP registered at user scope, `vault-session` and `vault-closeday` skills symlinked, Honcho nightly job running, graphify installed. Only now move to Phase C.

---

## Phase C — Everything else (GSD, skills cohort, atlas-setup self-check, per-project)

### C.1 GSD workflow

- **What:** AI project management workflow — phases, plans, execution, state tracking.
- **Check:** `ls ~/.claude/get-shit-done/VERSION 2>/dev/null`
- **Install:** `npx get-shit-done-cc@latest --claude --global`
- **Verify:** inside Claude Code, run `/gsd:help` — should list all GSD commands
- **Scaffold a project:** `cd ~/Developer/<project> && mkdir -p .planning/{codebase,phases}` then run `/gsd:init` inside the project

### C.2 Skills cohort

These can install in any order — they have no interdependencies with each other (they all depend on Phases A and B being complete).

- **Superpowers plugin** — brainstorming, plan writing, execution, code review, debugging, git worktrees
  - `/plugins` → search "superpowers" → install
- **skill-creator** — create, test, iterate on custom skills
  - `/plugins` → search "skill-creator" → install
- **claude-md-management** — audit and improve CLAUDE.md files
  - `/plugins` → search "claude-md-management" → install
- **security-guidance** — security best practices and vuln detection
  - `/plugins` → search "security-guidance" → install
- **playground** — interactive HTML playgrounds with live controls for visual tuning
  - `/plugins` → search "playground" → install
- **huggingface-skills** — ML model training, datasets, Gradio apps
  - `/plugins` → search "huggingface-skills" → install
- **swift-lsp** (iOS/macOS work only) — Swift language server
  - `/plugins` → search "swift-lsp" → install
- **Codex Experts (136 specialist agents)**
  - Clone: `cd /tmp && git clone https://github.com/VoltAgent/awesome-codex-subagents.git`
  - Convert TOML → md files into `~/.claude/agents/codex-experts/{category}/{name}.md` (ask Claude to generate the Python conversion script)
  - Create router skill: `~/.claude/skills/codex-experts/SKILL.md`
  - Verify: ask Claude "What expert sub-agents do you have available?" — should list 136 across 10 categories
- **Impeccable Design Skills (21 skills)**
  - `/install-plugin pbakaus/impeccable`
  - Post-install: run `/teach-impeccable` once per project to capture design context
  - Skills: `typeset`, `arrange`, `colorize`, `polish`, `normalize`, `harden`, `animate`, `delight`, `overdrive`, `critique`, `audit`, `optimize`, `adapt`, `extract`, `distill`, `clarify`, `bolder`, `quieter`, `onboard`, `frontend-design`, `visual-preview`
- **Figma plugin** — read/write Figma designs, build design systems
  - `/plugins` → search "Figma" → install
  - Account needed: Figma API token from figma.com/developers
- **frontend-design plugin** — production-grade frontend interfaces
  - `/plugins` → search "frontend-design" → install
- **Dream memory consolidation** — shipped via second-brain-bridge (Phase B.3); also available standalone
  - Check: `ls ~/.claude/skills/dream/` — should exist after second-brain-bridge install
  - Verify: `/dream` triggers consolidation
- **12 Vault Skills** — shipped via second-brain-bridge (Phase B.3)
  - Skills: `vault-context`, `vault-today`, `vault-closeday`, `vault-trace`, `vault-connect`, `vault-ghost`, `vault-challenge`, `vault-ideas`, `vault-graduate`, `vault-drift`, `vault-emerge`, `vault-schedule`
  - Check: `ls ~/.claude/skills/vault-today/`
- **MARP Slides** — presentation decks from markdown
  - ```bash
    git clone https://github.com/robonuggets/marp-slides.git /tmp/marp-slides
    cp -r /tmp/marp-slides ~/.claude/skills/marp-slides
    ```
- **Playwright** — headless browser automation
  - ```bash
    npm install -g playwright
    npx playwright install chromium
    npx playwright install webkit
    ```
- **AceDataCloud** — unified API for 50+ AI services (image, video, music, TTS, search)
  - Skills ship pre-installed with impeccable/GSD
  - Account needed: platform.acedata.cloud API key per service

### C.3 atlas-setup self-check

Run this to verify everything registered correctly:

```
/atlas-setup
```

The skill scans `~/.claude/settings.json`, `~/.claude.json`, `~/.claude/skills/`, and `~/.claude/agents/` and reports missing or misconfigured pieces.

### C.4 Per-project setup

Each repo gets:

- **`CLAUDE.md`** at the project root — project-level instructions, tech stack, conventions, gotchas
- **`.claude/settings.json`** — project-scoped permissions, hooks, env vars
- **Worktree config** (optional) — `.claude/worktrees/` for parallel session isolation
- **`/teach-impeccable`** (optional) — captures design context for this project
- **`/dream` schedule** (optional) — periodic memory consolidation

---

## Deferred — Do Not Install

These were evaluated and are NOT part of the default Atlas stack. Skip them unless the user explicitly asks.

- **ruflo** — evaluated 2026-04-19. Not adding. (Conflict with existing second-brain-bridge scope; no unique value added on top of Honcho + vault-session.)
- **LightRAG** — keep as opt-in. Heavy Python dependency, needs API credits loaded. Install only when the user has documents to index AND approves the credit spend.
- **MemPalace** — keep as opt-in. Honcho + vault-session covers most needs. Install only if the user specifically wants verbatim conversation recall.

If the user asks about any of these, explain they're deferred and why. Don't push them.

---

### Final Summary

After all installations (Phases A, B, C), present a summary:

```
╔══════════════════════════════════════════════════════════════╗
║  ATLAS TOOLCHAIN v1.2.0 — SETUP COMPLETE                     ║
╠══════════════════════════════════════════════════════════════╣
║                                                              ║
║  Phase A — Base:                                             ║
║    ✓ Homebrew           ✓ Node / Bun / Python                ║
║    ✓ git / gh           ✓ Claude Code (authenticated)        ║
║    ✓ Claude Desktop     ✓ Honcho (connected)                 ║
║                                                              ║
║  Phase B — Memory foundation:                                ║
║    ✓ Obsidian + vault   ✓ Obsidian CLI                       ║
║    ✓ Core MCPs (user scope)                                  ║
║    ✓ second-brain-bridge (6-AI-Memory/ scaffolded)           ║
║    ✓ graphify                                                ║
║    ⚠ Obsidian must be running for vault tools to work        ║
║                                                              ║
║  Phase C — Everything else:                                  ║
║    ✓ GSD v1.34+         ✓ Superpowers + skill-creator        ║
║    ✓ Codex Experts (136 agents)                              ║
║    ✓ Impeccable (21 skills)                                  ║
║    ✓ 12 Vault Skills    ✓ Dream                              ║
║    ✓ Figma / frontend-design                                 ║
║    ✓ MARP / Playwright / AceDataCloud                        ║
║                                                              ║
║  Deferred (do not install by default):                       ║
║    ○ ruflo — evaluated, not adding                           ║
║    ○ LightRAG — opt-in, needs API credits                    ║
║    ○ MemPalace — opt-in, verbatim recall only                ║
║                                                              ║
╚══════════════════════════════════════════════════════════════╝

Next steps:
1. Restart Claude Code to pick up all new plugins and MCP servers
2. Run /effort max at the start of each session
3. Run /teach-impeccable in each project to set up design context
4. Run /vault-today at session start, /vault-closeday at session end
5. Run /dream weekly to keep memory clean
```

Use ✓ for installed, ✗ for skipped, ⚠ for warnings, ○ for deferred.

---

## Self-Improvement System

This skill is designed to get better with every run. Three mechanisms:

### Self-Update Check (Run at Start)

Before Phase 0, check if a newer version exists on GitHub:

```bash
REMOTE_VERSION=$(gh api repos/The-Pleroma/playbooks/contents/gsd/atlas-setup/SKILL.md -q '.content' 2>/dev/null | base64 -d | grep "^version:" | head -1 | awk '{print $2}')
LOCAL_VERSION="1.2.0"  # from this file's frontmatter

if [ "$REMOTE_VERSION" != "$LOCAL_VERSION" ] && [ -n "$REMOTE_VERSION" ]; then
  echo "Update available: $LOCAL_VERSION → $REMOTE_VERSION"
fi
```

If an update exists, ask the user: "A newer version of atlas-setup is available (vX.X.X). Update now?" If yes:

```bash
gh api repos/The-Pleroma/playbooks/contents/gsd/atlas-setup/SKILL.md -q '.content' | base64 -d > ~/.claude/skills/atlas-setup/SKILL.md
```

Then reload and continue with the updated version.

### Post-Run Feedback Capture (Run After Final Summary)

After the final summary, ask:

> "Did anything fail or need a workaround during setup? If so, describe what happened and how you fixed it. This helps improve the skill for future users."

If the user provides feedback:

1. **Log the run** — append to `~/.claude/skills/atlas-setup/run-history.json`:

```json
{
  "date": "2026-04-19",
  "os": "darwin",
  "installed": ["claude-code", "honcho", "obsidian", "second-brain-bridge", "graphify", "gsd"],
  "skipped": ["figma", "supabase"],
  "failed": [],
  "fixes": [],
  "feedback": "Everything worked smoothly"
}
```

2. **If something failed and was fixed** — update the relevant install step in SKILL.md with the workaround. Add it as a "Common fix:" note under that tool's entry. Then push the update:

```bash
cp ~/.claude/skills/atlas-setup/SKILL.md /tmp/atlas-setup-update.md
cd /tmp && gh api repos/The-Pleroma/playbooks/contents/gsd/atlas-setup/SKILL.md \
  -X PUT \
  -f message="fix(atlas-setup): add workaround for [tool] — [description]" \
  -f content="$(base64 < /tmp/atlas-setup-update.md)" \
  -f sha="$(gh api repos/The-Pleroma/playbooks/contents/gsd/atlas-setup/SKILL.md -q '.sha')"
```

3. **Bump the patch version** in the frontmatter (e.g., 1.2.0 → 1.2.1)

### Auto-Discovery (Optional — Run Anytime)

Check for new plugins or MCPs that aren't in the skill yet:

```bash
# List installed plugins
grep -o '"[^"]*@[^"]*"' ~/.claude/settings.json | sort

# Compare against skill's known list
# Flag any new ones not covered by the skill
```

If new tools are found, ask: "You have [X] installed that isn't in atlas-setup yet. Want to add it to the skill so future setups include it?"

If yes, add the new tool to the appropriate phase section, bump the minor version (e.g., 1.2.0 → 1.3.0), and push to the repo.

---

## Important Notes

- **Never install something without asking first.** Always present the category, explain what each tool does, and let the user choose.
- **API keys are sensitive.** Never log, display, or store API keys in plain text in files. Use environment variables or secure config.
- **Some tools cost money.** Flag any tool that uses paid API credits (LightRAG, AceDataCloud services, Firecrawl beyond free tier, Honcho beyond free tier). Get confirmation before proceeding.
- **Obsidian must be running during Phase B.** The MCP server connects to Obsidian's Local REST API — if Obsidian is closed, all vault tools fail silently.
- **Phases are ordered for a reason.** Don't let the user skip Phase B and jump to Phase C — the skills cohort will install successfully but half of them won't work at runtime because the vault isn't wired up.
- **Restart required.** After installing plugins and MCP servers, a Claude Code restart is needed to pick them up. Mention this at the end.
- **second-brain-bridge is the canonical memory installer.** Don't hand-roll the 6-AI-Memory scaffold, don't manually create vault-session/vault-closeday skills, don't install the Honcho launchd job separately — let `install.sh` do all of it.
