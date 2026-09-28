# 🎈 Happy Birthday Madiha

A ridiculous, gorgeous, pink-and-blue birthday website built for Madiha — by siductify.

**Live:** https://siductify.github.io/happy-birthday/

---

## What's inside

| Section | What happens |
| --- | --- |
| 🎈 **Hero** | Seven floating balloons. Pop them all and **HAPPY BIRTHDAY MADIHA** explodes onto the screen, letter by letter, with confetti. There's a lazy-mode button if you can't be bothered. |
| 📸 **The pics** | Every photo in `photos/` becomes a tilted polaroid with washi tape, lazy-loaded, with a parallax slide inside the frame. Click one to open the lightbox (arrow keys work). |
| 💗 **How much she means to me** | A big paragraph that lights up word by word as you scroll. |
| 🪦 **One year closer to your grave** | Fully sarcastic. Death notice, tombstone, ghost emojis, zero remorse. |
| ✨ **NAH SERIOUSLY** | The real message, revealed word by word, plus an opening "last present". |
| 🎈 Footer + extras | Scroll progress bar, drifting background shapes, cursor sparkles, balloon-sound toggle, back-to-top. |

## Tech

Single self-contained `index.html` — no build step, no framework, no npm.
Confetti is a hand-written canvas particle system, balloon pops are synthesised
with the Web Audio API (no audio files), and all the parallax runs off one
`requestAnimationFrame` loop. Fonts come from Google Fonts.

## Adding your photos

1. Drop image files into `photos/` (`.jpg`, `.jpeg`, `.png`, `.webp`, `.gif`, `.avif`).
2. Optional caption: name the file `something__your caption here.jpg`
   — everything after the `__` becomes the handwritten caption.
3. Rebuild the list:
   ```bash
   python3 photos/build-manifest.py
   ```
4. Refresh / redeploy. Done.

Photos appear in filename order, so prefix with `01-`, `02-` if order matters.
Files named `placeholder-*` are ignored as soon as at least one real photo exists.

See [`photos/README.md`](photos/README.md) for details.

## Customising the words

Everything is in `index.html` (plain HTML/CSS/JS — just find & replace):

| What | Where |
| --- | --- |
| The name | `MADIHA` / `Madiha` appears **8 times** — the `<title>`, two `<meta>` tags, the hero word (`data-text="MADIHA"`), the big watermark behind the meaning section, the "happy birthday, Madiha" line, the marquee text at the bottom of the script, and the closing paragraph. |
| The big headline | `<h1 class="mega">` — three `<span class="word" data-text="...">` elements. Change the `data-text` and it rebuilds itself. |
| Meaning section | `<div class="scrolly" id="meaningText">` |
| The grave joke | `<section class="grave">` — headline, "death notice" list, tombstone text |
| The serious message | `<span class="big-words" id="seriousText">` plus the paragraph below it |
| The "last present" popup | `.present-card` — swap in your own gift/reveal |
| Signature | search for `your favourite menace` |

The exact line requested was *"NAH SERIOUSLY. YOU ARE ONE OF THE BEST THING THAT HAS
HAPPEND TO ME."* — it's live with the spelling tidied up ("THINGS THAT HAS HAPPENED").
Prefer it verbatim? Just edit `#seriousText`.

## Running it locally

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

(Any static server works — it's just files.)

## Deploying

Pushing to `main` triggers `.github/workflows/pages.yml`, which publishes the
repo root to GitHub Pages. If the deploy job ever fails with a "Pages not
enabled" error, go to **Settings → Pages → Build and deployment → Source** and
pick **GitHub Actions**.

---

Made with too much pink, an unreasonable amount of parallax, and zero self-control. 💗
