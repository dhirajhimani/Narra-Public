# 📖 The Narra User Journey

> From importing a book to reading, translating, and exporting — the complete flow.

---

## 1️⃣ First Launch — Model Onboarding

Before anything else, the app checks if the AI model is available:
- **Mobile:** Downloads Qwen3-4B (~2.6 GB) to app-private storage automatically (or user imports manually)
- **Desktop:** User can browse to an existing `.gguf` file OR download the default
- **Web:** Skips this entirely (no on-device AI — read-only companion)

---

## 2️⃣ Library Screen — Empty State

User lands on the **Library** — a grid of book cards. On first launch it shows an empty state: *"Import your first book"* with an import button.

---

## 3️⃣ Book Import

User taps the **Import** button → a file picker slides up:
- **Mobile:** System file picker filtered to `.epub`
- **Desktop:** Drag-and-drop zone + file picker alternative

The EPUB is parsed and converted to an `.mlbk` (SQLite database) — chapters, paragraphs, and metadata are stored for instant access.

---

## 4️⃣ Reader — Bilingual Mode

Opening a book takes the user to the **Reader Screen**:
- Original paragraph in the source language
- AI-translated paragraph immediately below, in a softer style
- Tap any word → inline glossary popup with definition + grammar note

Translation happens **on-demand** — only the visible page + 1 page look-ahead. Never the full book upfront.

---

## 5️⃣ Glossary & Grammar *(requires AI model)*

When the on-device AI model is downloaded, the AI extracts:
- **Glossary terms:** key vocabulary with translations and example sentences
- **Grammar tips:** brief notes on patterns encountered (verb conjugations, case usage, etc.)

Accessible via a slide-out panel from the reader.

---

## 6️⃣ Chapter Recap — Visual Animation *(planned)*

> 🚧 Chapter recaps are currently disabled while we iterate on the animation engine.

When enabled, at the end of each chapter the user will tap **"Watch Recap"**:
- The AI generates a Director's Script (mood, characters, key events, intensity)
- A Compose Canvas animation renders the recap in real-time
- Gradient palettes reflect the chapter's mood, text reveals key moments
- On Desktop with LGI: optional AI-generated chapter artwork as backdrop

---

## 7️⃣ Export

Users can export their processed book at any time:
- **`.mlbk`** — Share the full Narra experience with another Narra user
- **`.epub`** — Bilingual EPUB for Kindle, Kobo, or any standard e-reader

Partially translated books export with bilingual sections for translated content and original text with markers for the rest.

---

## 8️⃣ For Educators

1. **Prepare a book** — Import EPUB into Narra Desktop
2. **Pre-translate** — Let the AI translate all chapters (throttled, thermal-aware)
3. **Export .mlbk** — Students open in Narra mobile (no AI download needed for pre-translated books)
4. **Share via** — Google Drive, AirDrop, USB, email (it's just a file)

