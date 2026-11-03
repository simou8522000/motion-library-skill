# قاموس الموشن — Motion Library skill

A Claude skill with 68 named motion-graphics effects for vertical talking-head reels (Instagram Reels, TikTok, Shorts). Each effect has a short description in Moroccan Darija, what it is good for, and how to make it.

- 45 effects run on real footage with the [claude-video-effects](https://github.com/Vibha-Ramprakash/claude-video-effects) skill (`/effects`).
- 23 classics (jump-cut, whip-pan, karaoke captions, picture-in-picture, motion path…) come with a Remotion recipe.

## Files

- `SKILL.md` — instructions for Claude.
- `references/effects.md` — the 68 effects by category.
- `effects.json` — the same data, machine-readable.
- `demo/motion-library.html` — open it in a browser: a looping demo per effect, filters, and a button that copies the picked names to send to Claude.

## Install

```bash
git clone https://github.com/simou8522000/motion-library-skill ~/.claude/skills/motion-library
```

Then in Claude Code: «بغيت هاد الحركات: orbit, lean-in, comment-box» or "which motion fits my hook?".

Made by Web Astra (@wb.astra).
