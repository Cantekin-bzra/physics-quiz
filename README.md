# Force & Motion — IDAF physics revision quiz

Kenan Cantekin & Samuel P. · Class IMST24a · Submission 18 September 2026, 14:45

`index.html` is the whole quiz: one file, no build step, no dependencies except the
Google Fonts link. Open it in any browser to test it locally.

---

## 1. Put it online (GitHub Pages, free)

1. Create a GitHub account each, then create a repository — call it something like `physics-quiz`.
   Make it **public**, and add both of you as collaborators so the commit history shows
   two people working on it. That history is your evidence of teamwork.
2. Upload `index.html` to the root of the repository.
3. Go to **Settings → Pages**. Under *Source* choose **Deploy from a branch**, pick
   `main` and the folder `/ (root)`, then press Save.
4. Wait about a minute. Your link appears at the top of that page and looks like
   `https://<username>.github.io/physics-quiz/`.
5. Open the link on a phone as well as a laptop before you send it.

Netlify works too: drag the folder onto <https://app.netlify.com/drop> and you get a
link instantly, but it gives you no commit history, so GitHub Pages is the better choice here.

---

## 2. The videos

All 18 explanation clips are already in the repository and already wired up. Nothing to configure.

```
index.html
videos/    q1b.mp4 … q6d.mp4    (18 clips, 1080p, about 19 MB in total)
posters/   q1b.jpg … q6d.jpg    (the still shown before each clip plays)
```

Each clip is named after its slot: the wrong option B of question 1 is `q1b.mp4`. To replace
a clip, overwrite the file of the same name and commit — no code changes needed. If a file is
ever missing, the page falls back to the written explanation rather than breaking.

The originals were 4K and 290 MB in total, which is far too heavy to serve from GitHub Pages.
They are published at 1080p and 19 MB, which looks the same on a laptop or phone and loads in
a second. Keep the 4K originals somewhere safe in case you need to re-export.

Clips load only when someone actually gets an answer wrong (`preload="none"`), so opening the
quiz does not download 19 MB.

**Running time:** 18 clips, 11 minutes 18 seconds in total, every clip between 34.5 and 41.6
seconds. That satisfies both the per-clip rule of 30–45 seconds and the total of 10–12 minutes.

## 3. Before you submit

Done already: the quiz, all 18 videos, the posters, the glossary and the full sources list.

Three things left, and only you can do them.

- [ ] **Replace "Samuel P." with Samuel's full surname.** It appears twice in `index.html`:
      once in the byline near the top (search for `class="byline"`) and once in the Sources
      section under *Explanatory videos*.
- [ ] **Check the textbook edition.** The sources cite *Physik anwenden und verstehen*
      (DPK, Orell Füssli, 8th edition 2021, ISBN 978-3-280-04010-2) and *Formeln, Tabellen,
      Begriffe* (7th edition). Compare those against the copies you actually use and correct
      the edition or year if they differ.
- [ ] **Recompute the five numbers.** 42.5 N, 24.5 N and 56.6 N in question 3, and 1766 J
      and 180 J in question 6. Check each on your own calculator against your notes. Never
      submit a figure you have not verified yourself.

Optional, if you have time:

- [ ] **Re-do `q5c`, `q5d` and `q3d`.** In `q5c` and `q5d` the ball is drawn flying straight
      outwards from the centre instead of along the tangent — that is the misconception those
      clips exist to correct, and it contradicts `q5b`. In `q3d` the normal force arrow points
      downwards instead of away from the surface. Replacement prompts are in the production
      pack; overwrite the file of the same name in `videos/` to swap a clip in.
- [ ] **Ask Mr. Pröbsting about the video count.** The brief asks for 10–12 minutes at
      30–45 seconds each, which needs about 18 clips but there are only 6 questions. This quiz
      solves that with one video per wrong option. Worth confirming that is what he expects.

## 4. How the file is organised

Everything lives in `index.html`, in four labelled blocks inside `<script>`:

| Block | What it holds |
|---|---|
| 1. Video configuration | the two folder names, `videos` and `posters` |
| 2. `SKETCH` | the six situation sketches, drawn as SVG |
| 3. `QUESTIONS` | the questions, options, misconception names and written explanations |
| 4. Application logic | rendering, scoring and navigation |

To change a question, edit block 3 only. Each option is either `correct:true` with a `why`
(shown when the answer is right) or a wrong option with `vid`, `name` and `script`. The `vid`
value is what links an option to its video file: `vid:"q1b"` plays `videos/q1b.mp4`.

The written explanation stays visible under every clip. It doubles as a transcript, it means
the quiz still teaches with the sound off, and it is what appears if a video fails to load.

The colours mean something and are used consistently: **green** is the normal force and a
correct answer, **magenta** is the weight and a wrong answer, **blue** is velocity or
friction, **amber** is an applied force. That is the same colour code used in our physics
notes and in the videos.

## 5. Design notes (useful if you are asked about it)

- The background is squared paper, the same paper the subject is normally done on.
- The bar under the title is a **vector arrow** rather than a progress bar: it grows
  along an axis and each tick takes the colour of the answer you gave, so it also
  works as a score summary.
- Type: Archivo for headings, IBM Plex Sans for reading, IBM Plex Mono for anything
  numerical — units, given data and labels — so numbers always look like numbers.
- Every question opens with a *Situationsskizze*, the same first step we are taught
  to draw before solving any mechanics problem.
