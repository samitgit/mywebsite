# Samit K. Ghosh: personal website

Live site: https://samitgit.github.io/
Repository: https://github.com/samitgit/samitgit.github.io

A plain HTML + CSS site in a minimal academic style. There is nothing to install or build. Whatever files are in this repository is what the website shows.

## Folder layout

```
index.html      all the text and sections of the page
styles.css      colours, fonts, spacing
images/         photo, research-area thumbnails, simulation GIFs
images/pubs/    thumbnails for individual papers
files/          PDFs (CV.pdf, LTS_Estimator.pdf, Inverse_Bias.pdf)
README.md       this guide
```

## 1. Publish the site (new public repository)

GitHub Pages is free only for public repositories, which is why the site went offline when the old repository was made private. A repository named exactly `samitgit.github.io` gives you the short address https://samitgit.github.io/.

**Step 1: prepare the files on your computer**

1. Unzip the download. You get a folder with `index.html`, `styles.css`, `README.md`, `images` and `files`.
2. Put your three PDFs inside the `files` folder with exactly these names: `CV.pdf`, `LTS_Estimator.pdf`, `Inverse_Bias.pdf`. Use a version of the CV without your references' phone numbers and emails, because everything in a public repository is visible to everyone.

**Step 2: create the repository**

1. Sign in at https://github.com as `samitgit`.
2. Click the **+** at the top right, then **New repository**.
3. Repository name: `samitgit.github.io` (all lowercase, exactly this, no spaces).
4. Choose **Public**.
5. Tick **Add a README file**.
6. Click **Create repository**.

**Step 3: upload the files**

1. In the new repository, click **Add file**, then **Upload files**.
2. Open the unzipped folder, select everything inside it (`index.html`, `styles.css`, `README.md`, `images`, `files`) and drag it all into the browser window. Drag the contents, not the outer folder, so that `index.html` sits at the top level of the repository.
3. Wait until every file shows as uploaded. GitHub keeps the folder structure when you drop whole folders. If your browser will not accept folders, use Chrome, Edge or Firefox for this step. The uploaded list should include `images/pubs/group_dynamics.png` and your three PDFs under `files/`.
4. At the bottom, keep "Commit directly to the main branch" selected and click **Commit changes**.

**Step 4: turn on GitHub Pages**

1. In the repository, click **Settings**, then **Pages** in the left menu.
2. Under **Build and deployment**, set Source to **Deploy from a branch**.
3. Set Branch to **main** and the folder to **/ (root)**, then click **Save**.
4. Wait 1 to 3 minutes and refresh the Pages settings page. It will say "Your site is live at https://samitgit.github.io/".

**Step 5: check it**

Open https://samitgit.github.io/ and hard-refresh (Ctrl+Shift+R, or Cmd+Shift+R on Mac). Click the CV link and both working-note links to confirm the PDFs open.

**If something is wrong**

- 404 page: the repository name is not exactly `samitgit.github.io`, or `index.html` is inside a folder instead of at the top level.
- Page has no styling or images are missing: `styles.css` or the `images` folder was not uploaded, or the folder names differ in capital letters.
- A PDF link gives 404: the file is missing from `files/` or the name is different.
- Still nothing after 10 minutes: open the **Actions** tab and look at the latest "pages build and deployment" run for a red cross.

The old private repository can stay as it is. It no longer affects the new site.

## 2. How to edit later (in the browser)

1. Open the repository on GitHub and click the file you want to change (usually `index.html`).
2. Click the pencil icon (**Edit this file**).
3. Make your change, then click **Commit changes**.
4. Wait a minute or two and refresh the live site.

If you prefer to work on your computer, install GitHub Desktop, clone the repository, edit the files in any text editor (VS Code is good), then commit and push. Double-click `index.html` to preview before pushing.

## 3. Common edits

Each section in `index.html` starts with a comment such as `SECTION: News`. Use Ctrl+F to find it. In general, copy an existing item, paste it right below, and change the text.

**Add a news item** (put it at the top of the list):

```html
<li><span class="date">Nov 2026</span><span class="what">Your news sentence here.</span><span class="new-tag">New</span></li>
```

Delete the `<span class="new-tag">New</span>` part from older items. There is a ready-made commented template at the top of the list.

**Add a publication (for example, the new rainbow option paper):** in the Publications section there is a commented template marked `NEW RAINBOW OPTION PAPER`. Delete the `<!--` and `-->` around it and fill in the title, authors, venue and link. Copy any existing block for further papers. Use the next free ID (C3, J2, and so on).

**Add a thumbnail next to a paper:** put the image in `images/pubs/` (about 400 pixels wide is plenty). Then change the block from `<div class="pub no-thumb">` to `<div class="pub">` and add this as the first item inside it:

```html
<div class="thumb"><img src="images/pubs/my_figure.png" alt="Describe the figure"></div>
```

The block for paper W3 already does this, so copy it as an example.

**Add a paper link such as [paper] or [code]:** add this line inside the paper's block:

```html
<span class="actions">[<a href="https://...">paper</a>] [<a href="https://...">code</a>]</span>
```

**Add a course:** copy one `<tr>...</tr>` row in the Teaching tables.

**Add a working-note PDF:** put the file in `files/`, then copy one `<li>` in the Working notes list and change the name and the `href` (for example `files/MyNote.pdf`).

**Update the CV:** replace `files/CV.pdf` with the new file, keeping the same name. On GitHub, open the `files` folder, click **Add file > Upload files**, and upload the new file with the same name.

**Change the photo:** replace `images/Profile.jpg` with a new photo of the same name.

**Show ResearchGate:** in the link list next to the photo, find the commented-out ResearchGate line. Delete the `<!--` and `-->` around it and replace `PASTE_RESEARCHGATE_URL_HERE` with your profile link.

**Change colours or fonts:** at the top of `styles.css`, edit the values in the `:root` block (for example `--link` for link colour and `--tag` for the "New" tag).

**Hide something:** wrap it in `<!--` and `-->`, or delete it.

## 4. Things to keep in mind

- File names are case-sensitive on GitHub. `CV.pdf` and `cv.pdf` are different files.
- Do not put spaces in file names; use underscores.
- The simulation GIFs are large (3 to 5 MB each). Only the first one loads automatically; the others load when clicked.
- Everything in a public repository is visible to everyone, including older versions of files in the commit history. Do not upload anything private.
- If a change does not appear, hard-refresh the page. If it still does not, check the repository's **Actions** tab for a failed "pages build and deployment" run.
