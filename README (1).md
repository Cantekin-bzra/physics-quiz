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

## 2. Add your videos

Upload each clip to YouTube as **Unlisted** (not Private — private videos cannot be
embedded). Copy the ID from the URL: in `https://www.youtube.com/watch?v=dQw4w9WgXcQ`
the ID is `dQw4w9WgXcQ`.

Then open `index.html` and fill in the `VIDEOS` object near the top of the `<script>` section:

```js
const VIDEOS = {
  "q1b":"dQw4w9WgXcQ", "q1c":"", "q1d":"",
  ...
};
```

Until an ID is filled in, that slot shows the written explanation instead, so the quiz
never breaks while you are still filming. The written explanation stays visible under
every video anyway — it doubles as a transcript and means the quiz still teaches if
someone has no sound.

`video-scripts.md` contains all 18 scripts in filming order, with the slot name
(`q1b`, `q1c`, …) as the heading, so you always know which clip goes where.

### Timing

18 scripts, 1481 words in total. At about **130 words per minute** — a normal,
unhurried explaining pace — that is roughly **38 seconds per clip and 11.4 minutes
in total**, which sits inside both requirements (30–45 s each, 10–12 min total).
Time yourselves on the first clip and adjust your pace from there. Rushing at
160 wpm would drop the total below 10 minutes.

---

## 3. Before you submit — things only you can do

- [ ] **Fill in the sources.** Open the *Sources* section at the bottom of the page.
      Three entries are marked in orange and need the real details: the textbook title,
      authors, edition and year; the formulary; and any external material used in the videos.
      Leaving those markers in place would cost you marks for the formal criteria.
- [ ] **Write Samuel's full surname** in the byline (line beginning `<p class="byline">`)
      and in the sources.
- [ ] **Check every number yourselves.** Recompute 42.5 N, 24.5 N, 56.6 N, 1766 J and 180 J
      against your own notes and calculator. Do not submit a figure you have not verified.
- [ ] **Read all 18 explanations aloud** and change any wording that does not sound like
      you. You will be asked to defend this work; it has to be yours. Rewriting the
      scripts in your own words is the single best protection against the
      *unreflektiertes KI-Produkt* deduction.
- [ ] **Ask Mr. Pröbsting about the video count.** The brief says 10–12 minutes total at
      30–45 seconds each, which needs roughly 18 clips, but only 6 questions. This quiz
      solves that with one video per wrong option. Confirm that is what he expects.
- [ ] **Test on a phone.** Most classmates will revise on one.
- [ ] **Send the link** to Mr. Pröbsting, Mr. Fannenböck and Ms. Marti before
      18 September 2026, 14:45.

---

## 4. How the file is organised

Everything lives in `index.html`, in four labelled blocks inside `<script>`:

| Block | What it holds |
|---|---|
| 1. `VIDEOS` | the YouTube IDs you paste in |
| 2. `SKETCH` | the six situation sketches, drawn as SVG |
| 3. `QUESTIONS` | the questions, options, misconception names and scripts |
| 4. Application logic | rendering, scoring and navigation |

To change a question, edit block 3 only. Each option is either
`correct:true` with a `why` (shown when the answer is right) or a wrong option with
`vid`, `name` and `script`.

The colours mean something and are used consistently: **green** is the normal force
and a correct answer, **magenta** is the weight and a wrong answer, **blue** is
velocity or friction, **amber** is an applied force. That is the same colour code
used in our physics notes.

---

## 5. Design notes (useful if you are asked about it)

- The background is squared paper, the same paper the subject is normally done on.
- The bar under the title is a **vector arrow** rather than a progress bar: it grows
  along an axis and each tick takes the colour of the answer you gave, so it also
  works as a score summary.
- Type: Archivo for headings, IBM Plex Sans for reading, IBM Plex Mono for anything
  numerical — units, given data and labels — so numbers always look like numbers.
- Every question opens with a *Situationsskizze*, the same first step we are taught
  to draw before solving any mechanics problem.
