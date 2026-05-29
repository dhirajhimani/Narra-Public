# 📖 Narra — Project Vision

> **Turn a dead text file into a living tutor.**

---

## The Core Idea

Narra is an **offline-first, AI-powered e-reader** built with Kotlin Multiplatform.
It takes any standard text and rebuilds it in real-time as an interactive, bilingual learning experience — entirely on the device, with no cloud, no subscription, and no data leaving the user's hands.

The problem it solves is simple: reading in a foreign language is exhausting. Every unknown word forces the reader to break flow, open a dictionary, lose context, and slowly lose the will to continue. Narra eliminates that friction entirely by making translation and comprehension aids a first-class part of the reading surface itself.

---

## The Four Pillars

### 1. 🔤 Intelligent Bilingual Layout
Every original paragraph is immediately followed by its translation in the reader's target language. No tab-switching. No lookups. The two languages live side by side on the same page, letting the brain absorb the foreign text in its natural rhythm while the translation acts as a safety net just beneath it.

### 2. 🧠 Local AI Brain — 100% On-Device
All generative tasks — consecutive translation, glossary extraction, grammar-tip generation, and animation script creation — run on the phone's own hardware using a quantized Small Language Model.

**What this means for the user:**
- Works on a plane, in a tunnel, anywhere — zero internet required.
- No API keys, no monthly cost, no rate limits.
- The user's books and reading habits never touch a server.

### 3. 🎬 Visual Chapter Recaps *(planned)*
At the end of each chapter, the AI will analyze the chapter's emotional arc, key events, and character states, then output a structured script that drives a real-time GPU-accelerated animation. The reader will watch a cinematic recap that cements what they just read as a visual memory, not just text.

> 🚧 Chapter recaps are currently disabled while we iterate on the animation engine.

### 4. 📦 Dual Export System

| Format | Container | Use Case |
|---|---|---|
| `.mlbk` | SQLite database | Full native experience — animations, interactive glossary, grammar tips |
| `.epub` | ZIP / XHTML | Portable bilingual read on Kindle, Kobo, or any e-ink device |

---

## The Value Proposition

| Old Way | Narra Way |
|---|---|
| Read a sentence → hit an unknown word → open dictionary → lose context → try to re-engage | Read with the translation already there — never lose the thread |
| Finish a chapter → vague memory of what happened | Finish a chapter → watch a visual recap that locks it in |
| Sign up for a cloud AI translation service → pay monthly → trust them with your data | Everything runs locally — one-time app, permanent capability |
| EPUB is either original language or translated — never both | EPUB exports are bilingual by default |

---

## What Narra Is Not

- It is **not a streaming service** — no subscription, no server bills.
- It is **not a translation app** — translation is a feature in service of *reading*, not the product itself.
- It is **not an audiobook player** — the medium is text and animation, not audio.
- It is **not a cloud AI wrapper** — the model runs on the chip in the user's pocket.

---

## Target User

A motivated language learner who already reads books and wants to use that habit as the vehicle for acquisition. They are frustrated by the constant interruption of dictionary lookups and want a tool that keeps them in the story while still teaching them the language.

Secondary users: educators building bilingual curricula, and travellers who need offline reading in a foreign language without relying on connectivity.

---

## Platform Delivery Strategy

Mobile is the primary reading device. Desktop is the power workstation. They share the same codebase but have different capability ceilings.

| Feature | Android | iOS | Desktop (JVM) |
|---|---|---|---|
| Bilingual reading | ✅ Full | ✅ Full | ✅ Full |
| On-device AI translation (SLM) | ✅ | ✅ | ✅ |
| Glossary + Grammar tips | ✅ | ✅ | ✅ |
| `.mlbk` + `.epub` export | ✅ | ✅ | ✅ |
| Chapter visual recaps | 🚧 | 🚧 | 🚧 |
| Chapter visuals — LGI image gen | ❌ | ❌ | ✅ via LGI |
| Chapter video — LGI video gen | ❌ | ❌ | ✅ via LGI |

**LGI (Local Generative AI)** is a separate locally-running Python service. The desktop Narra app connects to it over localhost REST. When LGI is not running the app degrades gracefully — chapter recaps fall back to Canvas animation on all platforms.

