# NetBuddy AI — Rift Hackathon Submission (Problem Statement 1)

**One-liner:** ChatGPT, if it had launched in 2006 — as an AIM-style desktop
buddy inspired by the real-life chatbot "SmarterChild" that a generation of
kids actually talked to on AOL Instant Messenger. Same nostalgic shell,
except this time the buddy is genuinely, actually intelligent.

## How to run it
1. Open the live link — no install, no build step, no API key, nothing to set up.
2. Sign on with any screen name.
3. Double-click "NetBuddy AI" in the buddy list to open the chat window and talk.

The AI is powered by Gemini through a small serverless proxy (Cloudflare Worker)
that holds the API key server-side, so anyone opening the link can use it
immediately with zero setup.

## What's authentically 2006 here
- Dial-up boot sequence ("Negotiating handshake at 33.6k...")
- AIM-style sign-on screen, Buddy List, and draggable IM windows
- Windows XP "Luna" blue titlebar chrome, beveled buttons, Tahoma UI font
- Buzz/nudge button that shakes the window
- Away status toggle
- Bottom taskbar with clock and running task items, just like XP

## What's real underneath
The AI persona is a live system prompt that keeps the *style* early-2000s
(casual, short, emoticon-flecked) while the *substance* is a fully capable
modern model with **real tool use (agentic workflow)** — it can decide to
call a calculator tool for math or check its own live session status
instead of guessing, execute the tool, then respond with the real result.
You'll see this happen live in the chat window as a "*** using Calculator... ***"
note whenever it kicks in. The twist: "the dumb-looking chatbot from 2006
was secretly this smart — and this capable — the whole time."

## Mapping to judging criteria
| Criterion | How this hits it |
|---|---|
| Creativity & originality | Specific, real piece of internet history (AIM chatbots) rather than a generic reskin |
| 2000s UI/UX authenticity | AIM + XP Luna chrome recreated in detail, not just a color filter |
| Functionality | Real working chat, not a static mockup |
| Technical execution | Single-file frontend + a real serverless proxy backend (Cloudflare Worker) holding the AI key securely, with agentic tool-calling |
| Presentation | One-line pitch: "SmarterChild, but it's actually smart now" |
| AI integration (bonus) | The entire product *is* the AI integration |

## 3-sentence pitch for your demo
"In the 2000s, millions of kids chatted with SmarterChild, an AIM bot that
was basically a glorified magic 8-ball. I rebuilt that exact experience —
dial-up boot screen, buddy list, XP window chrome — but wired a real AI
brain behind it, so the nostalgic shell you remember now actually thinks."

## Architecture note
`index.html` is the entire frontend — no build step. It talks to a Cloudflare
Worker (`netbuddy-proxy`) that holds the Gemini API key as a secret and proxies
requests to Gemini's `generateContent` endpoint. This keeps the key off the
client entirely and means anyone opening the live link can use the app with
zero setup — no signup, no key, nothing to configure.
