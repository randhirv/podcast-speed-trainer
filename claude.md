# Claude Code - FastCast Project Guidelines

## Cost Optimization Strategy

**IMPORTANT:** This project uses Anthropic API credits. Always optimize for cost by choosing the right model for each task.

### Model Selection Guide

| Model | Cost | Best For | Avoid For |
|-------|------|----------|-----------|
| **Haiku** | $0.25/MTok input, $1.25/MTok output | File reads, simple edits, git operations, basic debugging | Complex reasoning, architecture decisions |
| **Sonnet 4.5** | $3/MTok input, $15/MTok output | Feature development, refactoring, moderate debugging | Simple file operations, repetitive tasks |
| **Opus** | $15/MTok input, $75/MTok output | Architecture decisions, complex problem-solving, multi-perspective analysis | Anything that Haiku or Sonnet can handle |

### Default Rules

1. **Start with Haiku** unless the task requires complex reasoning
2. **Escalate to Sonnet** only when Haiku struggles
3. **Use Opus sparingly** - only for critical architectural decisions
4. **Always ask before running expensive agents** (e.g., "This will cost ~$5, proceed?")

---

## Task-Specific Model Recommendations

### ✅ Use Haiku For:

- **File operations:** Read, simple edits, renames
- **Git operations:** Commits, pushes, status checks
- **Text updates:** Copy changes, link updates, typo fixes
- **Simple bug fixes:** Obvious logic errors, syntax fixes
- **Configuration changes:** Update version numbers, settings
- **Documentation updates:** README edits, comment additions

**Example prompts:**
```
"Quick task with Haiku: update the TestFlight link in index.html"
"Use Haiku: fix typo in line 45 of AudioPlayerViewModel.swift"
"Haiku only: read the first 50 lines of journey.html"
```

### ⚡ Use Sonnet For:

- **New features:** Adding capabilities, UI components
- **Refactoring:** Code restructuring, optimization
- **Moderate debugging:** Non-obvious bugs, state issues
- **UI/UX improvements:** Design changes, animations
- **API integration:** External service connections
- **Testing:** Writing tests, test debugging

**Example prompts:**
```
"Use Sonnet: add crash reporting to AudioPlayerService"
"With Sonnet: refactor the speed progression algorithm for better UX"
"Sonnet task: debug why background audio stops on iPhone 12"
```

### 🧠 Use Opus Only For:

- **Architecture decisions:** Major structural changes
- **Multi-agent analysis:** Running multiple specialized agents
- **Complex problem-solving:** Issues requiring deep reasoning
- **Strategic planning:** Product direction, feature prioritization
- **Performance optimization:** System-wide improvements

**Example prompts:**
```
"Use Opus: analyze the entire app architecture and recommend improvements"
"Opus needed: multi-agent evaluation of our monetization strategy"
"Complex problem - use Opus: redesign audio system to support audiobooks"
```

---

## Cost-Saving Best Practices

### 1. Read Files Selectively

❌ **Expensive:**
```
"Read AudioPlayerViewModel.swift"
```

✅ **Cheap:**
```
"Read AudioPlayerViewModel.swift lines 100-150"
"Show just the init() method from AudioPlayerViewModel.swift"
"Check if line 45 in index.html contains 'TestFlight'"
```

### 2. Request Concise Responses

❌ **Expensive:**
```
"Analyze the landing page" (might get 2000 word response)
```

✅ **Cheap:**
```
"Analyze the landing page - top 3 issues only"
"Brief summary: what's wrong with the FAQ section?"
"Quick answer: is the CTA button properly styled?"
```

### 3. Batch Simple Operations

❌ **Expensive (3 separate conversations):**
```
1. "Update version to 1.1"
2. "Fix typo in README"
3. "Push to GitHub"
```

✅ **Cheap (1 conversation):**
```
"Use Haiku to batch these:
1. Update version to 1.1
2. Fix typo in README
3. Push to GitHub"
```

### 4. Minimize Agent Usage

❌ **Expensive:**
```
"Run through all 3 agents (user researcher, executive, engineer)"
```

✅ **Cheap:**
```
"Just the user researcher's take on the FAQ section"
"Quick engineer review: is this technically sound?"
```

### 5. Cache Common Patterns

When repeatedly doing similar tasks, provide a template:

```
"For all future TestFlight link updates, use Haiku and:
1. Find YOUR_TESTFLIGHT_LINK_HERE
2. Replace with provided link
3. Commit with message 'Update TestFlight link'
4. Push to main"
```

---

## FastCast-Specific Guidelines

### Common Cheap Tasks (Haiku)

- Update TestFlight link in `index.html`
- Edit copy on landing page
- Update version/build numbers in `project.pbxproj`
- Add/remove screenshots from landing page
- Update privacy policy text
- Simple git operations (status, log, push)
- Read specific sections of code files

### Common Medium Tasks (Sonnet)

- Add new features to the iOS app
- Refactor existing Swift code
- Debug app-specific issues
- Update UI components
- Modify speed progression algorithm
- Add new statistics tracking
- Implement new settings options

### Common Expensive Tasks (Opus - Use Sparingly)

- Full app architecture review
- Multi-agent landing page evaluation
- Strategic product direction planning
- Major refactoring decisions
- Monetization strategy analysis

---

## Example Cost Estimates

Based on typical token usage:

| Task | Model | Estimated Cost |
|------|-------|----------------|
| Update TestFlight link | Haiku | $0.01-0.05 |
| Fix typo | Haiku | $0.01-0.03 |
| Read 100 lines of code | Haiku | $0.02-0.05 |
| Add new feature | Sonnet | $0.50-2.00 |
| Debug complex issue | Sonnet | $0.30-1.50 |
| Refactor large file | Sonnet | $1.00-3.00 |
| Multi-agent analysis | Opus | $5.00-15.00 |
| Architecture review | Opus | $3.00-10.00 |

---

## Session Cost Tracking

To track costs, estimate tokens used:
- **1 page of text ≈ 500-800 tokens**
- **1 Swift file (300 lines) ≈ 1500-2500 tokens**
- **Agent evaluation ≈ 10,000-30,000 tokens**

Ask Claude: "Estimate the cost of this session based on tokens used"

---

## Model Override Examples

### How to Explicitly Request a Model

**Haiku:**
```
"Quick Haiku task: update line 45"
"Use Haiku for this simple operation"
"Haiku only: read and summarize this file"
```

**Sonnet:**
```
"Use Sonnet: add crash reporting"
"Sonnet task: refactor the audio service"
"With Sonnet model: debug this complex issue"
```

**Opus:**
```
"This needs Opus: redesign the entire architecture"
"Use Opus: multi-perspective product analysis"
"Opus required: complex system-wide optimization"
```

### When to Let Claude Choose

If you're unsure, ask Claude:
```
"Should we use Haiku, Sonnet, or Opus for: [task description]?"
"Estimate cost and suggest model for: [task]"
```

---

## Emergency Cost Reduction

If costs are getting too high:

1. **Pause and batch:** Collect multiple small tasks, run them together
2. **Switch to Haiku:** Explicitly request Haiku for all tasks
3. **Limit agent usage:** Only use agents when critical
4. **Shorter context:** Ask for summaries instead of full analyses
5. **Async work:** Save complex tasks for when budget allows

---

## Quick Reference Card

**Before starting any task, ask:**
1. Is this a simple file operation? → **Haiku**
2. Is this feature development or debugging? → **Sonnet**
3. Is this architecture or multi-agent analysis? → **Opus** (ask first!)

**Default assumption:** Use Haiku unless there's a reason not to.

---

## Notes

- These guidelines were created after a session that cost ~$15-25 in credits
- Following these rules could reduce costs by 50-70%
- The FastCast app was built in 5 days with primarily Sonnet
- Future maintenance should heavily favor Haiku
- Agent evaluations are powerful but expensive - use strategically

---

Last updated: 2026-01-29
Project: FastCast iOS App
Repository: https://github.com/randhirv/fastcast-speed-trainer
