---
marp: true
theme: default
paginate: false
style: |
  @import url('https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@200;300;400;500;600;700;800&display=swap');

  :root {
    --blue: #2563eb;
    --purple: #7c3aed;
    --teal: #0d9488;
    --orange: #ea580c;
    --pink: #db2777;
    --green: #16a34a;
    --gold: #d97706;
    --slate: #334155;
    --light: #f8fafc;
    --card: #ffffff;
    --border: #e2e8f0;
    --muted: #94a3b8;
    --body: #475569;
  }

  section {
    background: var(--light);
    color: var(--slate);
    font-family: 'Plus Jakarta Sans', sans-serif;
    font-weight: 400;
    padding: 40px 56px;
    line-height: 1.4;
  }

  h1 {
    font-family: 'Plus Jakarta Sans';
    font-weight: 800;
    font-size: 2.6em;
    color: var(--slate);
    letter-spacing: -0.02em;
    line-height: 1.05;
    margin: 0 0 4px;
  }

  h2 {
    font-family: 'Plus Jakarta Sans';
    font-weight: 600;
    font-size: 1.1em;
    color: var(--muted);
    margin: 0 0 12px;
  }

  h3 {
    font-family: 'Plus Jakarta Sans';
    font-weight: 700;
    font-size: 0.55em;
    color: var(--blue);
    text-transform: uppercase;
    letter-spacing: 0.18em;
    margin: 0 0 6px;
  }

  strong { color: var(--blue); font-weight: 700; }

  .tag {
    font-family: 'Plus Jakarta Sans';
    font-weight: 700;
    font-size: 0.5em;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    padding: 3px 10px;
    border-radius: 20px;
    display: inline-block;
  }

  .grid2 { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; }
  .grid3 { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 12px; }
  .grid4 { display: grid; grid-template-columns: 1fr 1fr 1fr 1fr; gap: 10px; }

  .card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 14px 16px;
    position: relative;
    overflow: hidden;
  }

  .card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 3px;
  }

  .card-blue::before { background: linear-gradient(90deg, var(--blue), #60a5fa); }
  .card-purple::before { background: linear-gradient(90deg, var(--purple), #a78bfa); }
  .card-teal::before { background: linear-gradient(90deg, var(--teal), #5eead4); }
  .card-orange::before { background: linear-gradient(90deg, var(--orange), #fb923c); }
  .card-pink::before { background: linear-gradient(90deg, var(--pink), #f472b6); }
  .card-green::before { background: linear-gradient(90deg, var(--green), #4ade80); }
  .card-gold::before { background: linear-gradient(90deg, var(--gold), #fbbf24); }

  .card h4 {
    font-family: 'Plus Jakarta Sans';
    font-weight: 700;
    font-size: 0.72em;
    margin: 0 0 4px;
    color: var(--slate);
  }

  .card p, .card li {
    font-size: 0.58em;
    color: var(--body);
    margin: 2px 0;
    line-height: 1.35;
  }

  .card ul { padding-left: 14px; margin: 4px 0; }

  .pill {
    display: inline-block;
    font-size: 0.48em;
    font-weight: 600;
    padding: 2px 8px;
    border-radius: 10px;
    margin: 1px 2px;
  }

  .pill-blue { background: #dbeafe; color: var(--blue); }
  .pill-purple { background: #ede9fe; color: var(--purple); }
  .pill-teal { background: #ccfbf1; color: var(--teal); }
  .pill-orange { background: #ffedd5; color: var(--orange); }
  .pill-pink { background: #fce7f3; color: var(--pink); }
  .pill-green { background: #dcfce7; color: var(--green); }
  .pill-gold { background: #fef3c7; color: var(--gold); }

  .subtitle { font-size: 0.65em; color: var(--muted); font-weight: 300; }
  .note { font-size: 0.52em; color: var(--muted); font-style: italic; margin-top: 8px; }
  .footer-bar { position: absolute; bottom: 20px; left: 56px; right: 56px; font-size: 0.45em; color: var(--muted); display: flex; justify-content: space-between; }
---

<!-- Slide 1: Title -->

<div style="display:flex; flex-direction:column; justify-content:center; align-items:center; height:100%; text-align:center;">

<div style="margin-bottom: 16px;">
<svg width="64" height="64" viewBox="0 0 24 24" fill="none" stroke="#2563eb" stroke-width="1.5">
<circle cx="12" cy="12" r="10"/>
<path d="M12 2a14.5 14.5 0 0 0 0 20 14.5 14.5 0 0 0 0-20"/>
<path d="M2 12h20"/>
</svg>
</div>

# Atlas Toolchain
## The Complete Cheat Sheet

<div style="margin-top: 20px; display:flex; gap:8px; justify-content:center; flex-wrap:wrap;">
<span class="pill pill-blue">14 Plugins</span>
<span class="pill pill-purple">168 Agents</span>
<span class="pill pill-teal">5 MCPs</span>
<span class="pill pill-orange">21 Design Skills</span>
<span class="pill pill-pink">12 Vault Skills</span>
<span class="pill pill-green">68 GSD Workflows</span>
</div>

<p class="subtitle" style="margin-top:24px;">v1.1.0 &mdash; April 2026 &mdash; <code>/atlas-setup</code> to install everything</p>

</div>

<div class="footer-bar">
<span>The-Pleroma/playbooks</span>
<span>Built by Seph &amp; Atlas</span>
</div>

---

<!-- Slide 2: Core Plugins -->

### Core Plugins

# The Foundation
## 14 plugins that power every session

<div class="grid3">

<div class="card card-blue">
<h4>GSD (Get Shit Done)</h4>
<p>AI project management — phases, plans, execution, state tracking. 68 workflow commands.</p>
<p><span class="pill pill-blue">/gsd-plan-phase</span> <span class="pill pill-blue">/gsd-execute-phase</span> <span class="pill pill-blue">/gsd-resume-work</span></p>
</div>

<div class="card card-purple">
<h4>Superpowers</h4>
<p>Brainstorming, plan writing, code review, debugging, git worktrees, parallel agents.</p>
<p><span class="pill pill-purple">/brainstorming</span> <span class="pill pill-purple">/writing-plans</span> <span class="pill pill-purple">/systematic-debugging</span></p>
</div>

<div class="card card-teal">
<h4>Honcho Memory</h4>
<p>Cross-session cloud memory. Persists preferences, behavioral patterns, user model.</p>
<p><span class="pill pill-teal">/honcho:setup</span> <span class="pill pill-teal">/honcho:status</span> <span class="pill pill-teal">/honcho:interview</span></p>
</div>

<div class="card card-green">
<h4>Context7</h4>
<p>Always up-to-date docs for any library, framework, or SDK. Never rely on stale training data.</p>
<p><span class="pill pill-green">Auto-triggers on library questions</span></p>
</div>

<div class="card card-orange">
<h4>Codex (OpenAI)</h4>
<p>Second AI runtime for rescue tasks, code review, and diagnosis when Claude gets stuck.</p>
<p><span class="pill pill-orange">/codex:rescue</span> <span class="pill pill-orange">/codex:setup</span></p>
</div>

<div class="card card-pink">
<h4>Skill Creator</h4>
<p>Build, test, and iterate custom skills with eval framework and description optimization.</p>
<p><span class="pill pill-pink">/skill-creator</span></p>
</div>

<div class="card card-gold">
<h4>Playground</h4>
<p>Interactive HTML playgrounds with live controls for visual tuning — sliders, pickers, preview.</p>
<p><span class="pill pill-gold">/playground</span></p>
</div>

<div class="card card-blue">
<h4>Claude MD Management</h4>
<p>Audit and improve CLAUDE.md files. Quality checks against templates.</p>
<p><span class="pill pill-blue">/revise-claude-md</span> <span class="pill pill-blue">/claude-md-improver</span></p>
</div>

<div class="card card-purple">
<h4>+ More</h4>
<ul>
<li>Security Guidance</li>
<li>HuggingFace Skills (ML)</li>
<li>Swift LSP (iOS)</li>
<li>Figma, Frontend Design</li>
<li>Supabase</li>
</ul>
</div>

</div>

---

<!-- Slide 3: Design Skills -->

### Impeccable Design Skills

# 21 Skills for UI Quality
## Run in sequence: normalize → typeset → arrange → colorize → harden → polish

<div class="grid4">

<div class="card card-blue">
<h4><svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="#2563eb" stroke-width="2" style="vertical-align:-2px;"><path d="M4 7V4h16v3"/><path d="M9 20h6"/><path d="M12 4v16"/></svg> /typeset</h4>
<p>Fix font hierarchy, sizing, weight, readability</p>
</div>

<div class="card card-purple">
<h4><svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="#7c3aed" stroke-width="2" style="vertical-align:-2px;"><rect x="3" y="3" width="7" height="7"/><rect x="14" y="3" width="7" height="7"/><rect x="3" y="14" width="7" height="7"/><rect x="14" y="14" width="7" height="7"/></svg> /arrange</h4>
<p>Layout, spacing, visual rhythm, grid balance</p>
</div>

<div class="card card-teal">
<h4><svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="#0d9488" stroke-width="2" style="vertical-align:-2px;"><circle cx="12" cy="12" r="10"/></svg> /colorize</h4>
<p>Strategic color using 60/30/10 ratio</p>
</div>

<div class="card card-gold">
<h4><svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="#d97706" stroke-width="2" style="vertical-align:-2px;"><path d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z"/></svg> /polish</h4>
<p>Final pass — alignment, spacing, consistency</p>
</div>

<div class="card card-orange">
<h4>/normalize</h4>
<p>Align to design system tokens</p>
</div>

<div class="card card-pink">
<h4>/harden</h4>
<p>Overflow, i18n, edge cases</p>
</div>

<div class="card card-green">
<h4>/animate</h4>
<p>Micro-interactions, motion</p>
</div>

<div class="card card-blue">
<h4>/delight</h4>
<p>Joy, personality, surprises</p>
</div>

<div class="card card-purple">
<h4>/overdrive</h4>
<p>Shaders, physics, 60fps</p>
</div>

<div class="card card-teal">
<h4>/critique</h4>
<p>UX eval with scoring</p>
</div>

<div class="card card-gold">
<h4>/audit</h4>
<p>A11y, perf, responsive</p>
</div>

<div class="card card-orange">
<h4>/optimize</h4>
<p>Speed, rendering, bundle</p>
</div>

<div class="card card-pink">
<h4>/adapt</h4>
<p>Responsive, breakpoints</p>
</div>

<div class="card card-green">
<h4>/extract</h4>
<p>Pull reusable components</p>
</div>

<div class="card card-blue">
<h4>/distill</h4>
<p>Strip to essence</p>
</div>

<div class="card card-purple">
<h4>/clarify</h4>
<p>Fix unclear UX copy</p>
</div>

<div class="card card-teal">
<h4>/bolder</h4>
<p>Amplify safe designs</p>
</div>

<div class="card card-gold">
<h4>/quieter</h4>
<p>Tone down intensity</p>
</div>

<div class="card card-orange">
<h4>/onboard</h4>
<p>First-run experiences</p>
</div>

<div class="card card-pink">
<h4>/frontend-design</h4>
<p>Build production UI</p>
</div>

<div class="card card-green">
<h4>/visual-preview</h4>
<p>See external tools</p>
</div>

</div>

---

<!-- Slide 4: MCP Servers + Knowledge -->

### Connections & Knowledge

# 5 MCPs + 12 Vault Skills
## MCP servers work in both Claude Code CLI and Co-Work

<div class="grid2">

<div>

<div class="card card-blue" style="margin-bottom:10px;">
<h4><svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="#2563eb" stroke-width="2" style="vertical-align:-2px;"><circle cx="12" cy="12" r="10"/><path d="M2 12h20"/></svg> MCP Servers (Global)</h4>
<div style="display:flex; flex-wrap:wrap; gap:4px; margin-top:6px;">
<span class="pill pill-purple">Obsidian</span>
<span class="pill pill-orange">Firecrawl</span>
<span class="pill pill-pink">Figma</span>
<span class="pill pill-gold">Gamma</span>
<span class="pill pill-teal">Context7</span>
</div>
<p style="margin-top:8px;">All registered at user level — available across every project and in Co-Work.</p>
<p style="color:#ea580c; font-weight:600;">&#9888; Obsidian must be running for vault tools to work</p>
</div>

<div class="card card-green" style="margin-bottom:10px;">
<h4><svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="#16a34a" stroke-width="2" style="vertical-align:-2px;"><path d="M13 2L3 14h9l-1 8 10-12h-9l1-8z"/></svg> Performance Tuning</h4>
<ul>
<li><strong>Adaptive Thinking OFF</strong> — prevents lazy shortcuts</li>
<li><strong>/effort max</strong> — full reasoning every request</li>
<li><strong>Read-guard hook</strong> — forces file reads before edits</li>
</ul>
</div>

<div class="card card-orange">
<h4><svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="#ea580c" stroke-width="2" style="vertical-align:-2px;"><circle cx="11" cy="11" r="8"/><line x1="21" y1="21" x2="16.65" y2="16.65"/></svg> Firecrawl (Web Scraping)</h4>
<ul>
<li>Scrape, crawl, search, interact with pages</li>
<li>AI-driven form filling and navigation</li>
<li>Free tier: 500 credits</li>
</ul>
<p><span class="pill pill-orange">/firecrawl-scrape</span> <span class="pill pill-orange">/firecrawl-search</span> <span class="pill pill-orange">/firecrawl-interact</span></p>
</div>

</div>

<div>

<div class="card card-purple" style="margin-bottom:10px;">
<h4><svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="#7c3aed" stroke-width="2" style="vertical-align:-2px;"><path d="M2 3h6a4 4 0 0 1 4 4v14a3 3 0 0 0-3-3H2z"/><path d="M22 3h-6a4 4 0 0 0-4 4v14a3 3 0 0 1 3-3h7z"/></svg> 12 Vault Skills (Obsidian)</h4>
<div style="display:grid; grid-template-columns: 1fr 1fr; gap: 3px; margin-top:6px;">
<span class="pill pill-purple">/vault-today</span>
<span class="pill pill-purple">/vault-closeday</span>
<span class="pill pill-purple">/vault-context</span>
<span class="pill pill-purple">/vault-ideas</span>
<span class="pill pill-purple">/vault-connect</span>
<span class="pill pill-purple">/vault-trace</span>
<span class="pill pill-purple">/vault-ghost</span>
<span class="pill pill-purple">/vault-challenge</span>
<span class="pill pill-purple">/vault-graduate</span>
<span class="pill pill-purple">/vault-drift</span>
<span class="pill pill-purple">/vault-emerge</span>
<span class="pill pill-purple">/vault-schedule</span>
</div>
<p style="margin-top:6px;">Plus <span class="pill pill-blue">/dream</span> for memory consolidation</p>
</div>

<div class="card card-teal" style="margin-bottom:10px;">
<h4>Memory Stack</h4>
<div style="font-size:0.58em; color: var(--body);">
<div style="display:flex; align-items:center; gap:8px; margin:4px 0;"><span class="pill pill-blue">L0</span> Auto-memory — working rules, snapshots</div>
<div style="display:flex; align-items:center; gap:8px; margin:4px 0;"><span class="pill pill-teal">L1</span> Honcho — stable preferences, user model</div>
<div style="display:flex; align-items:center; gap:8px; margin:4px 0;"><span class="pill pill-purple">L2</span> Obsidian — decisions, research, ideas</div>
<div style="display:flex; align-items:center; gap:8px; margin:4px 0;"><span class="pill pill-gold">L3</span> MemPalace — verbatim recall (optional)</div>
</div>
</div>

<div class="card card-gold">
<h4>Dev Tools</h4>
<div style="display:flex; flex-wrap:wrap; gap:4px; margin-top:4px;">
<span class="pill pill-gold">Playwright CLI</span>
<span class="pill pill-gold">Chromium + WebKit</span>
<span class="pill pill-gold">Python 3.12</span>
<span class="pill pill-gold">MARP Slides</span>
<span class="pill pill-gold">awesome-design-md (59 brands)</span>
</div>
</div>

</div>

</div>

---

<!-- Slide 5: 168 Expert Agents -->

### 168 Expert Sub-Agents

# Delegate, Don't Hero
## Claude routes to the right specialist automatically

<div class="grid3">

<div class="card card-blue">
<h4>Core Development (12)</h4>
<p>backend-developer, frontend-developer, mobile-developer, api-designer, fullstack-developer</p>
</div>

<div class="card card-purple">
<h4>Language Specialists (27)</h4>
<p>react-specialist, typescript-pro, python-pro, swift-expert, rust-engineer, golang-pro, vue-expert</p>
</div>

<div class="card card-teal">
<h4>Infrastructure (16)</h4>
<p>devops-engineer, docker-expert, kubernetes-specialist, terraform-engineer, cloud-architect</p>
</div>

<div class="card card-orange">
<h4>Quality & Security (16)</h4>
<p>code-reviewer, security-auditor, debugger, penetration-tester, qa-expert, accessibility-tester</p>
</div>

<div class="card card-pink">
<h4>Data & AI (12)</h4>
<p>prompt-engineer, llm-architect, postgres-pro, ml-engineer, data-scientist, ai-engineer</p>
</div>

<div class="card card-green">
<h4>Developer Experience (13)</h4>
<p>refactoring-specialist, mcp-developer, documentation-engineer, build-engineer, dx-optimizer</p>
</div>

<div class="card card-gold">
<h4>Business & Product (11)</h4>
<p>product-manager, ux-researcher, legal-advisor, technical-writer, sales-engineer</p>
</div>

<div class="card card-blue">
<h4>Orchestration (12)</h4>
<p>task-distributor, multi-agent-coordinator, workflow-orchestrator, error-coordinator</p>
</div>

<div class="card card-purple">
<h4>Research (7) + Specialized (12)</h4>
<p>competitive-analyst, market-researcher, game-developer, fintech-engineer, payment-integration</p>
</div>

</div>

<p class="note">Two-Pass Rule: if an approach fails twice, delegate to a specialist. Never guess a third time.</p>

---

<!-- Slide 6: Quick Start -->

### Getting Started

# Install in One Command
## Then type /atlas-setup in Claude Code

<div class="grid2">

<div>

<div class="card card-blue" style="margin-bottom:10px;">
<h4>Step 1: Install the Skill</h4>
<div style="background:#1e293b; border-radius:8px; padding:12px 16px; margin-top:8px; font-family:monospace; font-size:0.55em; color:#e2e8f0; line-height:1.6;">
mkdir -p ~/.claude/skills/atlas-setup && \<br>
curl -s https://raw.githubusercontent.com/<br>
The-Pleroma/playbooks/main/gsd/<br>
atlas-setup/SKILL.md > \<br>
~/.claude/skills/atlas-setup/SKILL.md
</div>
</div>

<div class="card card-purple" style="margin-bottom:10px;">
<h4>Step 2: Run the Wizard</h4>
<div style="background:#1e293b; border-radius:8px; padding:12px 16px; margin-top:8px; font-family:monospace; font-size:0.6em; color:#e2e8f0;">
claude<br>
/atlas-setup
</div>
<p>The wizard detects what you have, asks what you want, installs step by step.</p>
</div>

<div class="card card-green">
<h4>Step 3: Daily Workflow</h4>
<ul>
<li><strong>/effort max</strong> — start of each session</li>
<li><strong>/vault-today</strong> — morning planning</li>
<li><strong>/gsd-resume-work</strong> — pick up where you left off</li>
<li><strong>/dream</strong> — weekly memory cleanup</li>
<li><strong>/vault-closeday</strong> — end of day capture</li>
</ul>
</div>

</div>

<div>

<div class="card card-teal" style="margin-bottom:10px;">
<h4>What Works Where</h4>
<div style="font-size:0.56em; color:var(--body); margin-top:6px;">
<div style="display:flex; justify-content:space-between; padding:3px 0; border-bottom:1px solid var(--border);"><span><strong>Feature</strong></span><span><strong>CLI</strong> &nbsp; <strong>Co-Work</strong></span></div>
<div style="display:flex; justify-content:space-between; padding:3px 0; border-bottom:1px solid var(--border);"><span>MCP Servers</span><span style="color:var(--green);">&#10003; &nbsp;&nbsp;&nbsp; &#10003;</span></div>
<div style="display:flex; justify-content:space-between; padding:3px 0; border-bottom:1px solid var(--border);"><span>Plugins</span><span><span style="color:var(--green);">&#10003;</span> &nbsp;&nbsp;&nbsp; <span style="color:#ef4444;">&#10007;</span></span></div>
<div style="display:flex; justify-content:space-between; padding:3px 0; border-bottom:1px solid var(--border);"><span>Skills (/commands)</span><span><span style="color:var(--green);">&#10003;</span> &nbsp;&nbsp;&nbsp; <span style="color:#ef4444;">&#10007;</span></span></div>
<div style="display:flex; justify-content:space-between; padding:3px 0; border-bottom:1px solid var(--border);"><span>Sub-agents</span><span><span style="color:var(--green);">&#10003;</span> &nbsp;&nbsp;&nbsp; <span style="color:#ef4444;">&#10007;</span></span></div>
<div style="display:flex; justify-content:space-between; padding:3px 0; border-bottom:1px solid var(--border);"><span>GSD Workflows</span><span><span style="color:var(--green);">&#10003;</span> &nbsp;&nbsp;&nbsp; <span style="color:#ef4444;">&#10007;</span></span></div>
<div style="display:flex; justify-content:space-between; padding:3px 0;"><span>Honcho Memory</span><span style="color:var(--green);">&#10003; &nbsp;&nbsp;&nbsp; &#10003;</span></div>
</div>
</div>

<div class="card card-gold" style="margin-bottom:10px;">
<h4>Staged Tools (Configure Later)</h4>
<ul>
<li><strong>LightRAG</strong> — knowledge graph RAG. Needs API credits.</li>
<li><strong>MemPalace</strong> — verbatim conversation storage. Optional.</li>
<li><strong>AutoResearch</strong> — autonomous ML training. Needs NVIDIA GPU.</li>
</ul>
</div>

<div class="card card-orange">
<h4>Self-Improving</h4>
<p>The skill checks for updates, captures post-run feedback, and patches itself. Every run makes it better for the next person.</p>
<p><span class="pill pill-orange">v1.1.0</span> <span class="pill pill-blue">The-Pleroma/playbooks</span></p>
</div>

</div>

</div>
