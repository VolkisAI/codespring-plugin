# CodeSpring CLI Quick Reference

## First-Time Setup (4 Steps)

If the user needs to install from scratch:

```bash
# 1. Install the CLI (may need sudo)
npm i -g @codespring-app/cli
# or: sudo npm i -g @codespring-app/cli

# 2. Login (opens browser)
codespring auth login

# 3. Install Claude Code skills
npx skills add CodeSpringApp/codespring-skills

# 4. Link to a project
codespring init
```

## Auth
```bash
codespring auth status          # Check if logged in + token expiry
codespring auth login           # Login via browser (interactive)
codespring auth logout          # Clear credentials
```

## Project Setup
```bash
codespring init                             # Interactive project linking
codespring init --project <id> --force      # Direct link to specific project
codespring status                           # Show linked project info
codespring projects                         # List all projects
codespring project create --name "Name" --description "Desc"   # Create new project
```

IMPORTANT: After `project create`, always run `codespring init --project <id> --force` to link to the new project. The CLI does NOT auto-link.

## Features
```bash
codespring features                                    # List features
codespring feature create --title "Title" --description "Desc"  # Create feature
```

## Tasks
```bash
codespring tasks                           # List all tasks
codespring tasks --status todo             # Filter by status
codespring tasks --feature <id>            # Filter by feature
codespring task create --title "Title" --priority high --feature <id>
codespring task start <id>                 # Mark in_progress
codespring task done <id>                  # Mark done
codespring task update <id> --status <s>   # Update status
```

## Mind Map
```bash
codespring mindmap                         # Get full mindmap
codespring mindmap set-info --title "T" --description "D"
codespring mindmap tech-stack --add '[{"id":"tech-x","title":"X","description":"Y"}]'
codespring mindmap features --add '[{"title":"X","description":"Y"}]'
codespring mindmap note <featureId> --text "Notes here"
```

IMPORTANT: Tech stack items MUST have `id`, `title`, and `description` fields.

## PRDs
```bash
codespring prds                            # List PRDs
codespring prd <id>                        # Get PRD content
codespring prd sync <id> --file <path>     # Update PRD from file
```

PRDs can only be GENERATED in the web app. CLI can read and update them.

## Output Flags
```bash
--json      # Force JSON output
--pretty    # Pretty-print JSON
--md        # Force markdown output
```

## Known Issues
- `--project` flag on commands is unreliable. Always use `codespring init` to switch projects.
- Auth tokens expire. Check with `codespring auth status`.
- No delete commands exist. Clean up via web UI if needed.
- 502 errors can occur. Retry after a few seconds.
