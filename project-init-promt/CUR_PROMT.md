convert all color relevant into variable, free to change values of the current css variaboles in theme to align with the intended UX/UI design, preserve the current variable names, only add new if neccessary and list it to markdown reported file.

~/.gemini/antigravity-cli/brain/9b73e33a-6c73-4f02-bad4-acc69390c44b/.system_generated/steps/61/output.txt) (ctrl+o to expand)

Now I have everything I need. Let me plan the color variable mapping:

Existing brand variables I'll map to:

• #141210, #1A1714 → $coal-dark (foreground/dark text)
• #0D0D0D → $coal-black (deepest dark)
• #C8922A → $ember-gold (primary CTA color)
• #A67218 → needs $ember-dark (darker gold for eyebrows/labels/icons) — NEW
• #F0EBE2 → $text-on-dark (nav text on dark bg)
• #D4C9B8 → $cream-dark (dividers, muted)
• #F7F5F0, #F7F5F0 → $cream (section backgrounds)
• #EFECE6 → needs $surface-alt or $cream-mid — actually close to cream, NEW: surface-muted
• #FFFFFF → $white (cards)
• #333333 → nav dark bg, NEW: nav-bg or map to $coal-mid+
• #E5E0D8, #E0D9CD → border/divider colors, need $border aligned
• #5C554E → $text-muted (body descriptions)
• #6E665E → close to $text-muted, slightly different — can map to $text-muted
• #3D3731 → dark body text — can map to $coal-dark
• #FF6000 → logo flame icon — brand color, NEW: brand-flame

Now update all variables and replace hardcoded colors in one comprehensive execute:
