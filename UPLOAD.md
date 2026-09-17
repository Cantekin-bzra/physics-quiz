# How to upload — step by step

Everything is finished and tested. This is the last job.

You already have the repository at `github.com/Cantekin-bzra/physics-quiz` with Pages
switched on, so you are only replacing what is in it.

---

## 1. Unzip

Download `physics-quiz-site.zip` and unzip it. Inside you get a folder called `site`
containing four things:

```
index.html      the quiz itself
README.md       notes for you two
videos/         18 mp4 files
posters/        18 jpg files
```

Open `index.html` by double-clicking it and play through the quiz once on your own
computer before uploading anything. Everything should work offline exactly as it will
online.

---

## 2. Delete the old index.html

Your repository already has an `index.html` from the first upload, and you cannot upload
a file over one that already exists through the web interface.

1. Open `github.com/Cantekin-bzra/physics-quiz`
2. Click `index.html`
3. Click the three dots at the top right of the file view, then **Delete file**
4. Scroll down and click **Commit changes**

Leave `README.md` and `video-scripts.md` alone for now; you will replace the README in
the next step the same way, or simply upload over it later.

---

## 3. Upload everything

1. On the repository's main page, click **Add file**, then **Upload files**
2. Open the `site` folder on your computer
3. Select all four items — `index.html`, `README.md`, and the two folders `videos` and
   `posters` — and drag them into the dashed box
4. Wait. It is 19 MB, so the upload bar will take a minute or two. Do not close the tab.
5. In the commit message box write something real, such as
   `Add all 18 explanation videos and finished sources`
6. Make sure **Commit directly to the main branch** is selected
7. Click **Commit changes**

Dragging the folders keeps the folder structure, which is what the page expects. If your
file manager will not let you drag folders, open `videos`, select all 18 files, and drag
those in — then repeat for `posters`. GitHub will ask for a path; type `videos` or
`posters` accordingly.

---

## 4. Check it worked

Wait two minutes for GitHub Pages to rebuild, then open:

**https://cantekin-bzra.github.io/physics-quiz/**

Go through this list:

- [ ] The quiz loads and the title reads *Force & Motion*
- [ ] Answer question 1 wrongly — a video player appears with a still image
- [ ] Press play. The clip plays and you can hear both voices
- [ ] The written explanation is underneath the video
- [ ] Finish all six questions and check the result screen appears
- [ ] Open **Sources** at the bottom and confirm there are no orange markers left
- [ ] Do all of the above again on a phone

If a video shows "VIDEO UNAVAILABLE", the file did not upload or landed in the wrong
folder. Check that `videos/q1b.mp4` exists in the repository at that exact path.

---

## 5. Send the link

To Mr. Pröbsting, Mr. Fannenböck and Ms. Marti, before **18 September 2026, 14:45**.

Say in the email that it is a browser quiz that needs no installation and works on a
phone, and that every wrong answer plays a short explanatory video.

---

## If something goes wrong

**The page looks unstyled.** The browser cached the old version. Press Ctrl+Shift+R
(Cmd+Shift+R on a Mac) to force a reload.

**Videos do not play on iPhone.** They are standard H.264 mp4, which every iPhone
supports. If nothing plays, the files are missing rather than incompatible.

**The upload fails halfway.** Do it in two goes: first `index.html` and `README.md`, then
the two folders. Each commit is independent.

**You need to swap a video later.** Upload a file with the same name into `videos/` and
GitHub will offer to replace it. No code changes needed.
