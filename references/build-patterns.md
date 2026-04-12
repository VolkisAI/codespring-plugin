# Build Patterns for Beginners

When helping users build apps with Claude Code, follow these patterns.

## The Plan-Then-Build Workflow

1. **Define what you're building** - One sentence. "A booking system for my salon."
2. **Break into features** - 5-8 major features. Auth, booking calendar, notifications, payments, admin dashboard.
3. **Pick one feature** - Start with the most important or the simplest.
4. **Break that feature into tasks** - 2-4 specific tasks. "Create user table", "Build signup form", "Add login flow".
5. **Build one task at a time** - Don't jump between tasks. Finish one, mark it done, move to the next.
6. **Sync to CodeSpring** - After completing a feature, sync it so the mind map stays current.

## Common Beginner Mistakes

### Going in circles
Signs: Same file edited 10+ times. Error messages repeating. "Let me try a different approach" more than twice.
Fix: Stop. Read the error message properly. Break the problem into smaller pieces. Ask Claude to explain what's wrong before trying to fix it.

### Building everything at once
Signs: Multiple features being worked on simultaneously. No clear structure. Files scattered everywhere.
Fix: Pick ONE feature. Build it completely. Test it. Then move to the next one.

### Vague prompts
Signs: "Build me an app that does X" with no specifics. "Make it better." "Fix everything."
Fix: Be specific. "Create a PostgreSQL table called 'bookings' with columns for date, time, customer_id, and status." The more specific the prompt, the better the result.

### Not testing
Signs: Building feature after feature without checking if any of them work.
Fix: After each task, run the app and verify it works. Don't build on a broken foundation.

## When To Intervene

The plugin should step in when it detects:
- **Vague request with no project structure**: "I want to build an app" -> Interview them, create a plan
- **Death loop**: Same file, 20+ messages, no progress -> Stop and diagnose
- **Feature jumping**: Working on auth, then suddenly payments, then UI -> Refocus on one thing
- **No planning**: Diving straight into code without any structure -> Suggest breaking it down first

## How To Intervene

Don't lecture. Do it WITH them:

"Looks like you're trying to build [X]. Before we dive in, let me break this into steps so we don't go in circles:
1. [Specific task]
2. [Specific task]
3. [Specific task]

I'll add these as tasks in CodeSpring. Want to start with #1?"

Then actually add the tasks to CodeSpring and start working on the first one.
