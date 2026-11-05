---
name: motion-library
description: The "قاموس الموشن" — a dictionary of 123 named motion-graphics effects for vertical reels (orbit, lean-in, backdrop-word, the-bill, place-in-grid, whip-pan, karaoke-captions, split-screen, live-chat, summary-to-ticket, one-shape, odometer, bar-chart-grow, myth-fact-swap…), each with what it looks like, what it is good for, and how to make it. Use it whenever the user sends effect names (often as «بغيت هاد الحركات: orbit, lean-in, …», copied from the library page), asks which motion fits a moment («شنو الحركة اللي تصلح ل…», "what effect for the hook / the CTA / a number"), wants to browse the motions, or asks to add named motions to a reel built with Remotion, the /effects skill, web-astra-reels or webastra-showreel.
---

# Motion library (قاموس الموشن)

123 named effects in 10 categories. The full list, with a Darija description, a "good for" hint and the way to build each one, is in `references/effects.md`. The same data is in `effects.json` (fields: `id`, `category`, `source`, `description_ar`, `good_for_ar`, `effects_options`, `how`). `demo/motion-library.html` is the visual page: a looping demo per effect, filters, and a "نسخ الأسماء" button that copies the picked names.

## Categories

| id | name | count |
|---|---|---|
| back | ورا الراس (behind the head) | 13 |
| cam | حركة الكاميرا (camera) | 9 |
| text | النص والعناوين (text, titles) | 13 |
| ui | كروت وواجهات (cards, UI) | 26 |
| frame | تكوين الكادر (framing) | 9 |
| trans | الانتقالات (transitions) | 11 |
| look | اللون والإضاءة (colour, light) | 4 |
| acc | لمسات (accents) | 10 |
| data | أرقام ومبيانات (numbers, charts) | 13 |
| explain | شرح الأفكار (explaining ideas) | 14 |

## Five kinds of effect

- **`/effects` (45)** — rendered on real footage by the effects skill (`claude-video-effects`). Face tracking and a person mask let them sit behind the head. One effect: `python scripts/fx.py <id> <video> <out.mp4> --start S --end E --text "..." --opt key=value`. Several: write a plan JSON and run `fx.py --plan`. Check stills first with `--still`.
- **classic (23)** — editing basics (jump-cut, whip-pan, karaoke-captions, picture-in-picture, motion-path…). Build them in Remotion with the recipe in `references/effects.md`.
- **showreel (17)** — components of the `webastra-showreel` template (reel-08, reel-26): live-chat, summary-to-ticket, face-travel, step-hud, agent-hub… Copy the component from `scenes.tsx` / `scenes26.tsx` and key it to spoken words with `say()`.
- **launch (11)** — `product-launch-motion` techniques: one-shape, blur-swap, brand-cursor, slide-to-confirm, stretch-toggle, odometer… Closed-form springs in a pure `seek(t)` (HTML) or the same maths in Remotion.
- **hyperframes (27)** — templates of `hyperframes-motion-library` for numbers and explaining ideas (bar-chart-grow, donut-progress, myth-fact-swap, three-step-flow, quote-card…). Render the template transparent and overlay it, or rebuild it in Remotion in the Web Astra colours.

## When the user sends names

1. Read each name's entry in `references/effects.md`. An unknown name: say so and offer the closest one in the same category.
2. Map each effect to the spoken line it belongs to (word timings from Whisper). Land the effect on the word, not on the sentence start.
3. Pick the route: `/effects` names on the raw footage, classic names in the Remotion composition. A reel can mix both: render the `/effects` pass first, then use that video as the face layer in Remotion.
4. Render, look at stills of each effect, then the full video.

## When the user asks what fits

Use the "good for" hint and these defaults:

- Hook (first 1–2 s): locked-on, lean-in, headline-box, backdrop-word, red-collage.
- Explaining steps: split-screen, lineup, todo, checklist, the-bill, motion-path.
- Numbers and proof: number-counter, odometer, big-number-card, before-after-stat, donut-progress, liquid-glass-graph, profile-wall.
- Product or bot demo: live-chat, stream-reply, brand-cursor, summary-to-ticket, slide-to-confirm, one-shape.
- Correcting a belief: myth-fact-swap, status-split, reject-stamp.
- Portfolio: noise, orbit, carousel-spin, phone-fan, place-in-grid.
- Twist or serious moment: spotlight, slow-push, moody, reject-stamp.
- CTA (end): comment-box, messages, tap, share-send, post-cta.

Give 2–3 options with one line each, then the one you recommend.

## Rules that came from real reels

- While the screen is split, the captions sit on the seam between the two halves.
- Keep a motion on screen long enough to read it; don't cut it away on the next word.
- Don't stack more than one big effect at a time; between effects, let the face breathe.
- Arabic text: reveal whole words, never cut letters (they change shape).
