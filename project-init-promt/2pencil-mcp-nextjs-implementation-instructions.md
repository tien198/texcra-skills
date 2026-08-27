# Pencil MCP → Next.js Implementation Instructions

## 1. Transcribe Localized Copy

### English

Transcribe all English copy from the English design into:

```text
messages/en.json
```

### Vietnamese

Transcribe all Vietnamese copy from the Vietnamese design into:

```text
messages/vi.json
```

### Localization Requirements

- Use identical message keys across both locale files.
- Use the generated messages from `/paraglide/messages.js` in the UI.
- Keep all user-visible text localized.
- Preserve unrelated existing and uncommitted work.
- Do not restore deleted files.
- Do not replace locale or configuration files wholesale.

---

## 2. Add Design Fonts to the Next.js Layout

Using Pencil MCP, inspect the entire design and list every font family used.

Add all required fonts to:

```text
app/layout.tsx
```

Use `next/font/google` where applicable.

Reference pattern:

```typescript
import { Alumni_Sans } from "next/font/google";

const alumniSans = Alumni_Sans({
  variable: "--font-alumni-sans",
  subsets: ["latin"],
  weight: "400",
});
```
