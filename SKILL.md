# Token Tracker

Simple local token counter for AI agents. Tracks input/output tokens per agent with JSON-based storage.

## Installation

```bash
clawhub install token-tracker
```

Or manually:
```bash
cd ~/.openclaw/workspace/skills/token-tracker
npm link
```

## Usage

### Log tokens from an agent run
```bash
token-log <agent> <input> <output> [model]

# Examples
token-log research-agent 1500 3200 gpt-4
token-log main-session 23000 355 ollama/kimi-k2.5
```

### View stats
```bash
token-stats              # All agents, all time
token-stats --today      # Today's usage only
token-stats research     # Specific agent
```

## Data Storage

JSON file at `~/.openclaw/token-tracker.json`

## Schema

- **sessions**: id, session_uuid, agent_name, model, started_at
- **usage**: id, session_id, input_tokens, output_tokens, logged_at

## Output Format

```
🤖 main: 2× | 23.0k📥 | 355📤
🤖 research: 1× | 1.5k📥 | 3.2k📤
🤖 architect: 1× | 800📥 | 1.2k📤
```

Legend:
- 🤖 Agent name
- × Number of sessions/runs
- 📥 Input tokens
- 📤 Output tokens
