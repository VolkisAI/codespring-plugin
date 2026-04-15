---
name: codespring-plugin
description: >
  Use when Sebastian asks about the CodeSpring plugin - building features,
  analysing usage data, checking install stats, debugging issues, updating
  the plugin, or planning what to add next. Also use when he says "plugin",
  "tripwire", "plugin analytics", or "how's the plugin doing".
allowed-tools:
  - Bash
  - Read
  - Write
  - Edit
  - Glob
  - Grep
  - Agent
  - WebSearch
  - WebFetch
---

# CodeSpring Plugin - Admin & Development Skill

This skill is for Sebastian (the plugin creator) to manage, analyse, and improve the CodeSpring plugin tripwire product.

## Plugin Location

- **Source code**: `/Users/sebsatian/App Builds/fb-ads-analyser/codespring-brain/v2/codespring-plugin/`
- **GitHub repo**: https://github.com/VolkisAI/codespring-plugin
- **Plan doc**: `/Users/sebsatian/App Builds/fb-ads-analyser/codespring-brain/v2/marketing/mrr-funnel/plugin-tripwire/README.md`
- **Dogfooding log**: `/Users/sebsatian/App Builds/fb-ads-analyser/codespring-brain/v2/marketing/mrr-funnel/plugin-tripwire/dogfooding-log.md`
- **CodeSpring project**: Plugin Tripwire Funnel (ID: 371602e8-b4d7-4da0-bfe5-ff67c266f5ec)

## Plugin Structure

```
codespring-plugin/
  .claude-plugin/
    marketplace.json     # Marketplace manifest
    plugin.json          # Plugin manifest
  skills/
    onboarding/SKILL.md  # Business interview + full setup
    sync/SKILL.md        # Session memory + auto-sync
    build-guide/SKILL.md # Teaching mode for beginners
    product-info/SKILL.md # Pricing + sales knowledge
    codespring-plugin/SKILL.md # This file (admin)
  hooks/
    hooks.json           # Empty (no hooks needed)
  references/
    product-info.md      # Pricing table
    cli-reference.md     # CLI commands
    objection-handling.md # Markdown objection etc
    build-patterns.md    # How to build apps
    project-templates.md # 9 business type templates
```

## PostHog Analytics

Events are tracked via PostHog capture API (EU instance).
- **Project API key**: phc_jRnh77duwOoaku2h8xltfsL3OLUibXCiFbvGu2IyklL
- **Host**: https://eu.i.posthog.com
- **Distinct ID**: Persistent UUID stored at `~/.codespring/analytics_id` (generated on first run, survives across sessions)
- **Properties on every event**: source: "plugin", plugin_version: "1.0.0", $os, $os_version
- **User properties set via $set**: onboarding_started, interview_completed, onboarding_completed, team_size, business_type, last_session_date
- **User properties set via $set_once**: first_seen_date, initial_plugin_version, acquisition_source

### Events Tracked

**Onboarding funnel:**
- `plugin_onboarding_started` - skill loads
- `plugin_cli_installed` / `plugin_cli_install_failed`
- `plugin_auth_connected` / `plugin_auth_failed`
- `plugin_interview_completed`
- `plugin_project_created`
- `plugin_features_added`
- `plugin_wow_moment` - project URL shown
- `plugin_boilerplate_installed` / `plugin_boilerplate_declined`
- `plugin_claudemd_updated` / `plugin_claudemd_declined`

**Ongoing usage:**
- `plugin_session_resume` - returning user
- `plugin_sync` - feature synced

### How to Check Analytics

Ask Sebastian to open PostHog (posthog-marketing MCP) and query for events with `source: "plugin"`. Or check directly in the PostHog dashboard.

Key questions to answer:
- How many people started onboarding vs completed it?
- Where do people drop off? (CLI install? Auth? Interview?)
- How many return for a second session? (plugin_session_resume)
- How many actively sync features? (plugin_sync count)

## What Sebastian Might Ask

### "How's the plugin doing?" / "Plugin analytics"
Check PostHog for plugin events. Build a funnel:
```
plugin_onboarding_started -> plugin_cli_installed -> plugin_auth_connected 
-> plugin_interview_completed -> plugin_project_created -> plugin_wow_moment
```
Report: total starts, completion rate, biggest drop-off point.

### "I want to add a feature to the plugin"
1. Read the current skill files to understand what exists
2. Discuss what the feature should do
3. Build it into the appropriate skill file
4. Push to GitHub: `cd codespring-brain/v2/codespring-plugin && git add -A && git commit -m "message" && git push`
5. Clear cache: `rm -rf ~/.claude/plugins/cache/codespring-plugins/`
6. Update the CodeSpring project (371602e8-b4d7-4da0-bfe5-ff67c266f5ec) with the new feature

### "Someone's having trouble installing"
Common issues:
1. **"plugin not found"** - They need full format: `/plugin install codespring@codespring-plugins`
2. **npm permissions** - They need `! sudo npm i -g @codespring-app/cli`
3. **Auth not working** - They need to run `! codespring auth login` (with the `!`)
4. **Plugin not activating** - They need `/reload-plugins` after install
5. **Old cached version** - Clear cache: `rm -rf ~/.claude/plugins/cache/codespring-plugins/`

### "Update the plugin" / "Push changes"
```bash
cd "/Users/sebsatian/App Builds/fb-ads-analyser/codespring-brain/v2/codespring-plugin"
rm -rf ~/.claude/plugins/cache/codespring-plugins/
git add -A
git commit -m "description of changes"
git push
```

### "What's left to build?"
Check the CodeSpring project for remaining tasks:
```bash
codespring init --project 371602e8-b4d7-4da0-bfe5-ff67c266f5ec --force
codespring tasks --status todo
```

### "How do users install it?"
Thank you page steps:
1. Create account at app.codespring.app/login?el=plugin
2. Open terminal, type `claude`
3. Paste into Claude Code chat:
   - `/plugin marketplace add VolkisAI/codespring-plugin`
   - `/plugin install codespring@codespring-plugins`
   - `/reload-plugins`
4. Type `/codespring:onboarding`

### "Can we get user emails?"
Not currently. The CLI doesn't expose user profile data. Need Harsh to add a `codespring whoami` command that returns email. Worth requesting as a CLI feature.

## Pricing (Current)

- **Plugin**: $2 tripwire (paid ads -> landing page -> Stripe)
- **CodeSpring Hobby**: Free (default on signup)
- **CodeSpring Starter**: £14/mo (5 projects, 5k credits)
- **CodeSpring Pro**: £49/mo (30 projects, 20k credits, kanban, import, support)
- **CodeSpring Business**: £187/mo (unlimited, team workspace, WhatsApp)

## Key Decisions Made

- Plugin is NOT on the Anthropic marketplace - distributed via own landing page
- No activation key validation (v1) - gated on having a CodeSpring account
- PostHog tracking uses public capture API (safe to expose phc_ key)
- CLAUDE.md update requires user consent (opt-in)
- All CodeSpring URLs include ?el=plugin for tracking
- CLI install asks user to run manually (sudo doesn't work inside Claude Code)
