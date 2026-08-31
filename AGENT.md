# Agent data map

## Codex

```text
~/.codex/
├── sessions/                 # Historical chat sessions
├── archived_sessions/        # Archived chat sessions
├── history.jsonl             # History index
└── session_index.jsonl       # Session index
```

## Spreadsheets plugin

```text
~/.codex/plugins/cache/openai-primary-runtime/spreadsheets/
```

## Antigravity CLI

### Overview

```text
~/.gemini/antigravity-cli/
├── brain/                              # Session logs and artifacts
│   └── <conversation-id>/              # Artifacts for one conversation
│       └── .system_generated/logs/
│           ├── transcript.jsonl        # Conversation transcript
│           └── transcript_full.jsonl   # Full conversation transcript
├── conversations/                      # Per-conversation SQLite databases
│   └── <conversation-id>.db            # Database for one conversation
└── conversation_summaries.db           # Conversation list/summary index
```

### Quick lookup

| Looking for | Location |
|---|---|
| Application directory | `~/.gemini/antigravity-cli/` |
| Logs and session artifacts | `~/.gemini/antigravity-cli/brain/` |
| Artifacts for one session | `~/.gemini/antigravity-cli/brain/<conversation-id>/` |
| Detailed session log | `~/.gemini/antigravity-cli/brain/<conversation-id>/.system_generated/logs/transcript.jsonl` |
| Full session log | `~/.gemini/antigravity-cli/brain/<conversation-id>/.system_generated/logs/transcript_full.jsonl` |
| Per-session databases | `~/.gemini/antigravity-cli/conversations/` |
| Database for one session | `~/.gemini/antigravity-cli/conversations/<conversation-id>.db` |
| Conversation summary index | `~/.gemini/antigravity-cli/conversation_summaries.db` |

Replace `<conversation-id>` with the ID of the conversation you want to inspect.
