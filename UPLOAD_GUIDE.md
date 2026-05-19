# Upload guide — Habitat Cinema Atlas prototype

Everything you need to start a fresh GitHub repo and get the live site running. No terminal, no git commands.

## What's in this folder

```
habitat-starter-pack/
├── index.html        ← the prototype (single file)
├── README.md         ← repo description shown on GitHub
├── .gitignore        ← ignores OS clutter (hidden in Finder)
├── UPLOAD_GUIDE.md   ← this file
└── photo-batches/
    ├── 01_event_queensgate.zip   62 files
    ├── 02_embassy.zip            88 files
    ├── 03_reading_porirua.zip    18 files
    ├── 04_roxy_part1.zip         78 files
    ├── 05_roxy_part2.zip         78 files
    ├── 06_roxy_part3.zip         78 files
    └── 07_roxy_part4.zip         76 files
                                ─────────
                                  478 files (all ≤100 per batch)
```

## Step 1 — create the repo

1. Go to <https://github.com/new>.
2. Repository name: `habitat-cinema-atlas` (or anything you like).
3. Public or Private — your choice.
4. **Don't** tick "Add a README" or "Add .gitignore" — yours are better.
5. Click **Create repository**.
6. On the empty repo page, click the small **"uploading an existing file"** link mid-page.

## Step 2 — upload the three root files

In Finder:
- Open the `habitat-starter-pack` folder.
- Press **⌘ + Shift + .** to reveal the hidden `.gitignore` file.
- Drag **`index.html`**, **`README.md`**, and **`.gitignore`** into the GitHub upload area.

Commit message: `Initial commit`. Click **Commit changes**.

## Step 3 — create the photos folder

You can't make an empty folder on GitHub directly — folders are created when you upload files into them. So instead of clicking around, we'll upload the first photo batch with a folder prefix:

1. Click **Add file → Upload files** from your repo's main page.
2. In Finder, **double-click `01_event_queensgate.zip`** to extract it (creates a folder of `.jpg` files).
3. Open that extracted folder, **⌘+A** to select all 62 files.
4. **Drag the files into GitHub's upload area.**
5. In the commit-message area, type a destination path **`photos/`** in the "Or choose your files" → there should be no extra step — GitHub will just upload them to the root.
6. **Important:** to put them inside a `photos/` folder, do this after dragging — in the commit message form there should NOT be a folder prompt. The simpler approach: drag in the files, then in the top of the upload page where it shows the path, type `photos` so the path reads `photos/`. *(If you can't see this, just commit normally — see the fix at the bottom.)*

Commit message: `Add Event Queensgate photos`. Click **Commit changes**.

**Easier alternative:** if GitHub's path prompt confuses you, just drag the files in at the repo root, commit, then move them all into `photos/` afterwards using GitHub's file manager. Or use **GitHub Desktop** instead — see "Easiest option" below.

## Step 4 — upload the remaining 6 batches

For each of `02_embassy.zip` through `07_roxy_part4.zip`:

1. **On GitHub**, click into the `photos/` folder.
2. Click **Add file → Upload files**.
3. **On your Mac**, double-click the zip to extract it.
4. Open the extracted folder, **⌘+A**, drag into GitHub's upload area.
5. Wait for the upload to finish (~10–30 seconds depending on batch size).
6. Commit with a message like `Add Embassy photos` or `Add Roxy photos (part 1/4)`.
7. Move to the next zip.

When all 7 are done you'll have all 478 photos in `photos/` on GitHub.

## Step 5 — turn on GitHub Pages (optional, makes the site live)

1. In your repo: **Settings → Pages**.
2. **Source**: Deploy from a branch.
3. **Branch**: `main`, folder `/ (root)`.
4. Click **Save**.
5. Wait ~30 seconds. Your live site will be at `https://<your-username>.github.io/habitat-cinema-atlas/`.

---

## Easiest option (if you'll do this more than once)

Install **GitHub Desktop** ([desktop.github.com](https://desktop.github.com/), free, ~3 min download). Then:

1. Open GitHub Desktop → **File → Clone repository** → pick your empty `habitat-cinema-atlas` repo.
2. In Finder, copy `index.html`, `README.md`, `.gitignore` into the cloned folder.
3. Inside the cloned folder, create a `photos/` subfolder.
4. Extract all 7 zips on your Mac, copy all 478 photos into `photos/`.
5. Open GitHub Desktop — it'll show all 481 files as new.
6. Add a commit message, click **Commit to main**, click **Push origin**.

One push, done. Takes about 2 minutes once GitHub Desktop is installed.

---

## Troubleshooting

**Site loads but photos are missing.** Make sure the `photos/` folder is at the repo root (not inside another folder) and the file names start with `event_`, `embassy_`, `roxy_`, or `reading_`. The `index.html` references them by exact name; GitHub Pages is case-sensitive.

**Some photos look upside down.** They've been rotated using EXIF data when I processed them, so they should display correctly. If one doesn't, just replace it.

**GitHub web upload hangs at 100+ files.** Use the GitHub Desktop path above, or split the batch further (extract the zip, drag half, commit, then drag the other half).

**Want to push more photos for Luxe or United later?** Same pattern: name them `luxe_<descriptor>_thumb.jpg` and `luxe_<descriptor>_full.jpg`, then add entries to `PHOTO_TAGS` in `index.html` and update the relevant Site record's `cover` and `photoCount` properties.
