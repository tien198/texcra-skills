# Codex

- Historical chat sessions: /home/tien/.codex/sessions/
- Archived sessions: /home/tien/.codex/archived_sessions/
- History indexes: /home/tien/.codex/history.jsonl and /home/tien/.codex/session_index.jsonl

# spreadsheets plugin
cd ~/.codex/plugins/cache/openai-primary-runtime/spreadsheets/



  ### 1. Đường dẫn thư mục chính

  • Thư mục ứng dụng Antigravity:
      • ~/.gemini/antigravity-cli/
      • (Đường dẫn tuyệt đối: /home/tien/.gemini/antigravity-cli/)

  ──────
  ### 2. Đường dẫn quản lý lịch sử và Logs

  • Thư mục chứa logs và artifacts của các phiên:
      • ~/.gemini/antigravity-cli/brain/
      • (Đường dẫn tuyệt đối: /home/tien/.gemini/antigravity-cli/brain/)
  • File log chi tiết theo từng phiên (<conversation-id>):
      • ~/.gemini/antigravity-cli/brain/<conversation-id>/.system_generated/logs/transcript.jsonl
      • ~/.gemini/antigravity-cli/brain/<conversation-id>/.system_generated/logs/transcript_full.jsonl
  • Thư mục artifacts của từng phiên:
      • ~/.gemini/antigravity-cli/brain/<conversation-id>/

  ──────
  ### 3. Đường dẫn Database lưu trữ

  • Thư mục database SQLite của từng phiên:
      • ~/.gemini/antigravity-cli/conversations/
      • (File từng phiên: ~/.gemini/antigravity-cli/conversations/<conversation-id>.db)
  • File database tóm tắt/index danh sách các phiên:
      • ~/.gemini/antigravity-cli/conversation_summaries.db
      • (Đường dẫn tuyệt đối: /home/tien/.gemini/antigravity-cli/conversation_summaries.db)


