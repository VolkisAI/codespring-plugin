# CodeSpring Plugin for Claude Code

Your AI business co-pilot. This plugin makes Claude Code remember your business, plan your app, and track your progress across every session.

## What You Get

- **Persistent memory** - Claude remembers your business and project across sessions
- **Visual mind map** - See your entire app plan as connected features at a glance
- **Production-ready boilerplate** - Start with a real Next.js app skeleton, not an empty folder
- **Build guide** - Step-by-step guidance that stops you going in circles
- **Progress tracking** - Always know how far along you are
- **Developer handoff** - Everything you plan becomes a spec you can share

## Installation

### Step 1: Install the CodeSpring CLI

```bash
npm i -g @codespring-app/cli
```

If that fails, try with sudo:
```bash
sudo npm i -g @codespring-app/cli
```

### Step 2: Install this plugin

**Option A - From marketplace (recommended):**
```
/plugin marketplace add VolkisAI/codespring-plugin
/plugin install codespring
```

**Option B - Local install (for testing):**
```bash
claude --plugin-dir ./path-to-this-folder
```

### Step 3: Open Claude Code

The plugin auto-activates. It will:
1. Ask you about your business (takes 3 minutes)
2. Set up your CodeSpring account and project
3. Create a visual mind map of your app plan
4. Give you a link to see it all: https://v2.codespring.app/project/[your-project-id]?el=plugin

## How It Works

**First time**: The plugin interviews you about your business and what you're building. It creates a CodeSpring project, populates the mind map, and sets up Claude to remember everything.

**Every session after**: Claude loads your project state automatically. It knows your tasks, features, and progress. It briefs you: "You were working on the checkout flow. 2 tasks left. Want to continue?"

**As you build**: The plugin syncs your progress to CodeSpring and shows you the mind map link. Every sync is a visual update of your project.

## Plugin Skills

| Skill | What it does |
|-------|-------------|
| `/codespring:onboarding` | Business interview + full setup |
| `/codespring:sync` | Load project state + sync progress |
| `/codespring:build-guide` | Step-by-step build guidance for beginners |
| `/codespring:product-info` | CodeSpring plans, pricing, and features |

## CodeSpring Plans

| | Hobby | Starter | Pro | Business |
|---|---|---|---|---|
| Price | Free | £14/mo | £49/mo | £187/mo |
| Projects | Limited | 5 | 30 | Unlimited |
| AI Credits | Limited | 5,000 | 20,000 | 100,000 |
| Kanban | - | - | Yes | Yes |
| Codebase Import | - | - | Yes | Yes |
| Team Workspace | - | - | - | Yes |

Sign up at https://app.codespring.app/login?el=plugin

## Support

- Priority support and 1-1 calls available on Pro and Business plans
- WhatsApp support on Business plan
- Visit https://codespring.app for more info
