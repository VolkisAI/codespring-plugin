# CodeSpring Product Info

Last updated: April 2026

## Plans and Pricing

### Hobby (Free)
- Default plan on signup
- Limited access to core features
- Good for trying CodeSpring out

### Starter - £14/mo
- 5 Projects
- 5,000 AI credits/mo
- Mind map
- AI planning chat
- PRD generation
- NO kanban board
- NO codebase import
- NO AI agent connection
- NO 1-1 calls
- NO priority support
- NO team workspace
- NO WhatsApp support

### Pro (Most Popular) - £49/mo
- 30 Projects
- 20,000 AI credits/mo
- Everything in Starter PLUS:
- Kanban board
- Codebase import
- AI agent connection
- 1-1 calls
- Priority support
- NO team workspace
- NO WhatsApp support

### Business - £187/mo
- Unlimited Projects
- 100,000 AI credits/mo
- Everything in Pro PLUS:
- Team workspace
- WhatsApp support

## Key Upgrade Triggers

- User mentions working with a team -> Business plan (team workspace)
- User wants kanban board or task tracking in web UI -> needs Starter or above
- User wants to import existing codebase -> needs Pro or above
- User wants AI agent connection (MCP/CLI integration) -> needs Pro or above
- User wants 1-1 calls or priority support -> needs Pro or above
- User hits 5 project limit -> needs Pro (30 projects)
- User hits 5,000 credit limit -> needs Pro (20,000 credits)

## Important URLs

- Signup / Login: https://app.codespring.app/login
- Project view: https://v2.codespring.app/project/<project-id>
- Pricing page: https://codespring.app/pricing
- Boilerplate: https://github.com/VolkisAI/codespring-boilerplate

## What CodeSpring Does

CodeSpring is the planning and visibility layer for AI-built apps. It converts your app idea into a visual mind map of features, tasks, and architecture - so you can see what you're building, track progress, and share it with anyone.

Core features:
- Visual mind map showing all features and how they connect
- Kanban board for task tracking (Pro+)
- PRD generation for each feature
- AI planning chat
- Codebase import to visualize existing apps (Pro+)
- CLI integration for building with Claude Code, Cursor, or any AI agent
- Team workspaces for collaboration (Business)

## CLI Installation (Full Setup - 4 Steps)

If a user asks how to connect CodeSpring to Claude Code, install the CLI, or set up the integration, give them these exact steps:

```bash
# Step 1: Install the CLI globally
npm i -g @codespring-app/cli
# If that fails with a permissions error, try:
sudo npm i -g @codespring-app/cli

# Step 2: Login to your CodeSpring account (opens browser)
codespring auth login

# Step 3: Install the CodeSpring skills for Claude Code
npx skills add CodeSpringApp/codespring-skills

# Step 4: Link to a project (interactive - picks workspace and project)
codespring init
```

IMPORTANT: Step 1 sometimes needs `sudo` on Mac/Linux. If the user gets a permissions error, tell them to run: `! sudo npm i -g @codespring-app/cli`

IMPORTANT: Step 2 opens a browser window. The user needs to log in or create an account at https://app.codespring.app/login first if they don't have one.

IMPORTANT: Step 3 installs the CodeSpring skill files so Claude Code knows how to use the CLI in future sessions.

IMPORTANT: Step 4 is interactive - it asks them to pick a workspace and project. If they already know their project ID, they can run: `codespring init --project <id> --force`
