---
name: atlas-setup
description: Guided wizard to install the complete Atlas toolchain on a fresh Claude Code installation. Use when setting up a new machine, onboarding a team member, reinstalling after a reset, or when the user says "set up Atlas", "install everything", "fresh install", "bootstrap my tools", or "atlas-setup". Also use when checking what's installed or verifying the toolchain is complete.
---

# Atlas Setup — Full Toolchain Wizard

A guided, step-by-step installer for the Atlas development environment. Checks what's already installed, walks users through each tool category, handles account setup, and verifies everything works.

## Philosophy

- **Check before installing** — never reinstall what's already there
- **Group by category** — let users opt into what they need
- **Active vs Staged** — some tools install now, others install but wait for configuration
- **Step-by-step for accounts** — when a tool needs an API key or account, walk through the signup process
- **Verify each install** — confirm it works before moving on
- **Obsidian must be running** — warn users before the Knowledge Tools section

## How to Run

When the user invokes this skill, follow these phases in order:

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

### Phase 1: Core Tools (Recommended for Everyone)

These are the foundation. Present them as a group and ask which to install.

**1.1 GSD (Get Shit Done)**
- What: AI project management workflow — phases, plans, execution, state tracking
- Check: `ls ~/.claude/get-shit-done/VERSION 2>/dev/null`
- Install: `npx get-shit-done-cc@latest --claude --global`
- Verify: Skill list includes `gsd-help`

**1.2 Honcho Memory**
- What: Cross-session memory that persists user preferences and behavioral patterns in the cloud
- Check: `grep -q "honcho" ~/.claude/settings.json 2>/dev/null`
- Install:
  1. `/plugin marketplace add plastic-labs/claude-honcho`
  2. `/plugin install honcho@honcho`
  3. `/reload-plugins`
  4. Run `/honcho:setup` to configure API key
- Account needed: Sign up at honcho.dev for API key
- Verify: `/honcho:status` returns connected

**1.3 Superpowers Plugin**
- What: Workflow skills — brainstorming, plan writing, plan execution, code review, debugging, git worktrees
- Check: `grep -q "superpowers" ~/.claude/settings.json 2>/dev/null`
- Install: Available in `/plugins` — search "superpowers" and install
- Verify: Skill list includes `superpowers:brainstorming`

**1.4 Context7**
- What: Fetches current documentation for any library/framework/SDK — always up-to-date API docs
- Check: `grep -q "context7" ~/.claude/settings.json 2>/dev/null`
- Install: `/plugins` → search "Context7" → install
- Verify: MCP tools include `mcp__plugin_context7_context7__resolve-library-id`

**1.5 Performance Tuning**
- What: Prevents Claude from being lazy — disables adaptive thinking and sets max effort
- No install needed — environment variable + session command
- Setup:
  ```bash
  # Add to shell profile (zsh on Mac, bash on Linux)
  echo 'export claude_code_disable_adaptive_thinking=1' >> ~/.zshrc  # or ~/.bashrc
  source ~/.zshrc
  ```
- Explain: "Adaptive thinking lets Claude decide to think less on 'simple' tasks, which causes it to skip work and report success without actually doing anything. Disabling it forces full reasoning on every request. Also run `/effort max` at the start of each session."

**1.6 Skill Creator**
- What: Create, test, and iterate on custom Claude Code skills with eval framework
- Check: `grep -q "skill-creator" ~/.claude/settings.json 2>/dev/null`
- Install: `/plugins` → search "skill-creator" → install
- Verify: Skill list includes `skill-creator:skill-creator`

**1.7 Claude MD Management**
- What: Audit and improve CLAUDE.md files — quality checks, template comparison, targeted updates
- Check: `grep -q "claude-md-management" ~/.claude/settings.json 2>/dev/null`
- Install: `/plugins` → search "claude-md-management" → install
- Verify: Skill list includes `claude-md-management:revise-claude-md`

**1.8 Security Guidance**
- What: Security best practices and vulnerability detection guidance
- Check: `grep -q "security-guidance" ~/.claude/settings.json 2>/dev/null`
- Install: `/plugins` → search "security-guidance" → install

**1.9 Playground**
- What: Create interactive HTML playgrounds with live controls for visual tuning
- Check: `grep -q "playground" ~/.claude/settings.json 2>/dev/null`
- Install: `/plugins` → search "playground" → install
- Verify: Skill list includes `playground:playground`

**1.10 HuggingFace Skills**
- What: ML model training, datasets, Gradio apps, model evaluation, Hub CLI
- Check: `grep -q "huggingface-skills" ~/.claude/settings.json 2>/dev/null`
- Install: `/plugins` → search "huggingface-skills" → install
- Verify: Skill list includes `huggingface-skills:hf-cli`

**1.11 Swift LSP (If Doing iOS Development)**
- What: Swift language server for type checking and autocomplete in iOS/macOS projects
- Check: `grep -q "swift-lsp" ~/.claude/settings.json 2>/dev/null`
- Install: `/plugins` → search "swift-lsp" → install
- Note: Only needed if building native iOS/macOS apps

**1.12 Codex Experts (136 Sub-Agents)**
- What: 136 specialist AI agents Claude can delegate to — backend dev, security audit, React, PostgreSQL, etc.
- Check: `ls ~/.claude/agents/codex-experts/ 2>/dev/null | wc -l`
- Install: Follow the process in the GSD manual — clone awesome-codex-subagents, convert, create router skill
- Verify: Ask Claude "What expert sub-agents do you have available?"

---

### Phase 2: Design Tools (If Doing UI/Frontend Work)

Ask: "Do you do frontend or UI work? These tools help with design quality."

**2.1 Impeccable Skills (21 Design Skills)**
- What: Systematic design quality — typography, color, layout, animation, accessibility audits
- Check: `ls ~/.claude/skills/typeset/ 2>/dev/null`
- Install: `/install-plugin pbakaus/impeccable` or manually clone and copy
- Post-install: Run `/teach-impeccable` once per project to establish design context
- Verify: Skill list includes `typeset`, `arrange`, `polish`, `colorize`

**2.2 Figma Plugin**
- What: Read/write Figma designs, implement designs as code, build design systems
- Check: `grep -q "figma" ~/.claude/settings.json 2>/dev/null`
- Install: `/plugins` → search "Figma" → install
- Account needed: Figma account + API token from figma.com/developers
- Verify: Skill list includes `figma:figma-use`

**2.3 Frontend Design Plugin**
- What: Build distinctive, production-grade frontend interfaces
- Check: `grep -q "frontend-design" ~/.claude/settings.json 2>/dev/null`
- Install: `/plugins` → search "frontend-design" → install
- Verify: Skill list includes `frontend-design`

**2.4 Design Reference Library (awesome-design-md)**
- What: 59 pre-built DESIGN.md files from top brands (Stripe, Apple, Tesla, etc.)
- Check: Look for the cloned repo
- Install: `git clone https://github.com/VoltAgent/awesome-design-md.git` to preferred location
- Usage: Copy a brand's DESIGN.md into your project, tell Claude "build UI matching this"

---

### Phase 3: Knowledge Tools (If Using Obsidian)

**IMPORTANT: Obsidian must be running for MCP tools to work. If Obsidian is not installed or the user doesn't use it, skip this entire section.**

Ask: "Do you use Obsidian for notes? If so, open it now — it needs to be running for setup."

**3.1 Obsidian MCP Server**
- What: Lets Claude read, search, create, and edit notes in your Obsidian vault
- Prerequisites:
  1. Obsidian installed (obsidian.md — free)
  2. A vault created and open
  3. "Local REST API" community plugin installed and enabled in Obsidian
- Check: `grep -q "obsidian" ~/.claude.json 2>/dev/null`
- Install:
  ```bash
  claude mcp add obsidian --transport stdio --scope user -- npx -y @zethictech/obsidian-mcp
  ```
  Then set the vault name: add `"env": {"OBSIDIAN_VAULT": "Your_Vault_Name"}` to the MCP config
- Verify: Restart Claude Code session, then test with `mcp__obsidian__get_vault_info`

**3.2 Obsidian Skills Plugin (kepano)**
- What: CLI interaction, markdown formatting, canvas files, bases — from Obsidian's creator
- Check: `grep -q "obsidian-skills" ~/.claude/settings.json 2>/dev/null`
- Install:
  1. `/plugin marketplace add kepano/obsidian-skills`
  2. `/plugin install obsidian@obsidian-skills`
  3. `/reload-plugins`
- Verify: Skill list includes `obsidian:obsidian-cli`

**3.3 Vault Skills (12 Thinking Tools)**
- What: Daily planning, idea generation, connection finding, memory consolidation
- These are standalone skill files, not a plugin
- Check: `ls ~/.claude/skills/vault-context/ 2>/dev/null`
- Install: Create each skill directory under `~/.claude/skills/` with a SKILL.md file
- Skills: vault-context, vault-today, vault-closeday, vault-trace, vault-connect, vault-ghost, vault-challenge, vault-ideas, vault-graduate, vault-drift, vault-emerge, vault-schedule
- Verify: Skill list includes `vault-today`

**3.4 Dream (Memory Consolidation)**
- What: Periodic memory cleanup — merge duplicates, fix stale facts, prune index
- Check: `ls ~/.claude/skills/dream/ 2>/dev/null`
- Install: Create `~/.claude/skills/dream/SKILL.md` with consolidation instructions
- Verify: `/dream` triggers the consolidation process

---

### Phase 4: AI Services (Account-Dependent)

Ask: "Which of these services do you have accounts with?" Present as a checklist.

**4.1 Supabase**
- What: Database, auth, edge functions, storage — your backend
- Check: `grep -q "supabase" ~/.claude/settings.json 2>/dev/null`
- Install: `/plugins` → search "Supabase" → install
- Account needed: supabase.com account, then link project via Supabase CLI
- Verify: Can run `mcp__plugin_supabase_supabase__list_projects`

**4.2 OpenAI Codex**
- What: Second AI runtime for rescue tasks, code review, diagnosis when Claude gets stuck
- Check: `which codex 2>/dev/null`
- Install:
  1. `/plugin marketplace add openai/codex-plugin-cc`
  2. `/plugin install codex@openai-codex`
  3. `/reload-plugins`
  4. `npm install -g @openai/codex`
  5. Run `! codex login` to authenticate
- Account needed: OpenAI account (ChatGPT Plus or API)
- Verify: `/codex:setup` shows ready=true

**4.3 Firecrawl**
- What: Web scraping, crawling, search, page interaction — converts websites to LLM-ready data
- Check: `which firecrawl 2>/dev/null`
- Install:
  1. Sign up at firecrawl.dev for API key
  2. `npx -y firecrawl-cli@latest init --all --browser` (authenticates via browser)
  3. `claude mcp add firecrawl --transport stdio --scope user -- npx -y firecrawl-mcp`
- Account needed: firecrawl.dev account (free tier: 500 credits)
- Verify: `firecrawl --version` and MCP tools include firecrawl

**4.4 Gamma**
- What: AI-powered presentations, documents, webpages
- Check: `grep -q "gamma" ~/.claude.json 2>/dev/null`
- Install: `claude mcp add gamma --transport stdio --scope user -- npx -y @raydeck/gamma-app-mcp`
- Account needed: gamma.app API key
- Verify: MCP tools include `mcp__claude_ai_Gamma__generate`

**4.5 AceDataCloud**
- What: Unified API for 50+ AI services — image gen, video gen, music, TTS, search
- Check: Look for acedatacloud skills
- Install: Skills come pre-installed with impeccable/GSD. Need API key from platform.acedata.cloud
- Account needed: AceDataCloud account + API key
- Services: Seedance, Suno, Midjourney, Flux, Luma, Veo, ElevenLabs (via Fish Audio), Google Search

---

### Phase 5: Dev Tools

**5.1 Playwright (Browser Automation)**
- What: Headless browser control — screenshots, form filling, visual testing
- Check: `which playwright 2>/dev/null`
- Install:
  ```bash
  npm install -g playwright
  npx playwright install chromium   # ~92MB
  npx playwright install webkit     # ~75MB (Safari/DuckDuckGo engine)
  ```
- Note: Firefox available but optional (`npx playwright install firefox`)
- Verify: `playwright --version`

**5.2 Python 3.12**
- What: Modern Python for tools that need 3.10+ (LightRAG, data science, ML)
- Check: `python3 --version` (need 3.10+)
- Install (macOS): `brew install python@3.12`
- Install (Linux): `sudo apt install python3.12 python3.12-venv`
- Verify: `/opt/homebrew/bin/python3.12 --version` (macOS) or `python3.12 --version` (Linux)

**5.3 MARP Slides**
- What: Generate professional presentations from markdown — charts, dashboards, dark/light themes
- Check: `ls ~/.claude/skills/marp-slides/ 2>/dev/null`
- Install:
  ```bash
  git clone https://github.com/robonuggets/marp-slides.git /tmp/marp-slides
  cp -r /tmp/marp-slides ~/.claude/skills/marp-slides
  ```
- Verify: Skill list includes `marp-slides`

---

### Phase 6: Staged Tools (Install Now, Configure Later)

Explain: "These tools are installed but dormant. They need either API credits or specific data before they're useful. I'll note when to activate each one."

**6.1 LightRAG (Knowledge Graph + RAG)**
- What: Builds knowledge graphs from documents for intelligent retrieval. 2x better than standard RAG.
- When to activate: When you have documents to index AND API credits loaded (Anthropic or OpenAI)
- Check: `ls ~/lightrag-env/ 2>/dev/null`
- Install:
  ```bash
  # Requires Python 3.10+
  python3.12 -m venv ~/lightrag-env
  source ~/lightrag-env/bin/activate
  pip install "lightrag-hku[api]"
  ```
- Status: Installed but not connected to any LLM. Load ~$10 of API credits when ready.
- To run: `source ~/lightrag-env/bin/activate && lightrag-server`

**6.2 MemPalace (Verbatim Conversation Storage)**
- What: Stores full conversation history locally with semantic search. Complements Honcho (which stores distilled conclusions).
- When to activate: When Honcho's distilled memory feels insufficient and you need exact conversation recall
- Install: `pip install mempalace` or plugin install
- Status: Optional. Honcho + auto-memory + Obsidian covers most needs.

---

### Phase 7: Final Summary

After all installations, present a summary:

```
╔══════════════════════════════════════════════════════════════╗
║  ATLAS TOOLCHAIN — SETUP COMPLETE                            ║
╠══════════════════════════════════════════════════════════════╣
║                                                              ║
║  Core:                                                       ║
║    ✓ GSD v1.34.2          ✓ Honcho                          ║
║    ✓ Superpowers          ✓ Context7                        ║
║    ✓ Performance tuning   ✓ 136 Expert agents               ║
║                                                              ║
║  Design:                                                     ║
║    ✓ Impeccable (21)      ✓ Figma                           ║
║    ✓ Frontend Design      ✓ Design Library (59 brands)      ║
║                                                              ║
║  Knowledge:                                                  ║
║    ✓ Obsidian MCP         ✓ Obsidian Skills                 ║
║    ✓ 12 Vault Skills      ✓ Dream                           ║
║    ⚠ Obsidian must be running for MCP tools to work          ║
║                                                              ║
║  Services:                                                   ║
║    ✓ Supabase             ✓ Codex                           ║
║    ✓ Firecrawl            ✓ Gamma                           ║
║                                                              ║
║  Dev:                                                        ║
║    ✓ Playwright           ✓ Python 3.12                     ║
║    ✓ MARP Slides                                            ║
║                                                              ║
║  Staged (installed, configure when ready):                   ║
║    ○ LightRAG — needs API credits                           ║
║    ○ MemPalace — optional                                   ║
║                                                              ║
╚══════════════════════════════════════════════════════════════╝

Next steps:
1. Restart Claude Code to pick up all new plugins and MCP servers
2. Run /effort max at the start of each session
3. Run /teach-impeccable in each project to set up design context
4. Run /dream periodically to keep memory clean
```

Use ✓ for installed, ✗ for skipped, ⚠ for warnings, ○ for staged.

---

## Important Notes

- **Never install something without asking first.** Always present the category, explain what each tool does, and let the user choose.
- **API keys are sensitive.** Never log, display, or store API keys in plain text in files. Use environment variables or secure config.
- **Some tools cost money.** Flag any tool that uses paid API credits (LightRAG, AceDataCloud services, Firecrawl beyond free tier). Get confirmation before proceeding.
- **Obsidian must be running.** Say this before Phase 3 and in the final summary. The MCP server connects to Obsidian's Local REST API — if Obsidian is closed, all vault tools fail silently.
- **Restart required.** After installing plugins and MCP servers, a Claude Code restart is needed to pick them up. Mention this at the end.
