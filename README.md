# NetBuddy AI — Rift Hackathon Submission (Problem Statement 1)

**One-liner:** ChatGPT, if it had launched in 2006 — as an AIM-style desktop
buddy inspired by the real-life chatbot "SmarterChild" that a generation of
kids actually talked to on AOL Instant Messenger. Same nostalgic shell,
except this time the buddy is genuinely, actually intelligent.

## How to run it
1. Open `netbuddy-ai.html` in any browser (double-click it — no install, no build step).
2. Sign on with any screen name.
3. **Network Key field:** this is your Anthropic API key (get a free one at
   console.anthropic.com). You can leave it blank and hit Sign On — if the
   app can't connect automatically, a "Connection Problem" window will pop
   up in-theme asking you to paste a key. This is deliberate: it mirrors how
   2000s software really did ask you for a registration/network key.
4. Double-click "NetBuddy AI" in the buddy list to open the chat window and talk.

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
| Technical execution | Single dependency-free HTML/CSS/JS file, no build tooling, clean structure |
| Presentation | One-line pitch: "SmarterChild, but it's actually smart now" |
| AI integration (bonus) | The entire product *is* the AI integration |

## 3-sentence pitch for your demo
"In the 2000s, millions of kids chatted with SmarterChild, an AIM bot that
was basically a glorified magic 8-ball. I rebuilt that exact experience —
dial-up boot screen, buddy list, XP window chrome — but wired a real AI
brain behind it, so the nostalgic shell you remember now actually thinks."

## Notes for you before you submit
- If you want this fully self-contained with zero setup for judges, the
  cleanest option is to deploy it (e.g. Netlify/Vercel drag-and-drop) and
  point it at a tiny serverless proxy that holds your API key server-side —
  avoids asking judges for their own key at all. Say the word and I'll build
  that proxy version too; it's a ~15-minute add-on.
- Everything is in one file (`netbuddy-ai.html`) on purpose — easiest to zip,
  easiest to host anywhere, easiest for a judge to just double-click.
