# How to Update the Nimbus Project Website

This site (nimbusproject.org) is a static website built with [Hugo](https://gohugo.io/)
and published automatically to GitHub Pages. This guide covers the everyday edits:
adding news, updating publications, editing projects, changing the jobs page, and
adding gallery photos.

> **Non-technical shortcut:** every task below is just editing a text file in this
> repository. You can do it entirely in the GitHub web editor (pencil icon on any file)
> without installing anything — see [Publishing your changes](#publishing-your-changes).

---

## The basics

- **Content lives in two places:**
  - `content/` — Markdown files for pages and news posts (this is where most edits go).
  - `layouts/` — HTML templates. A few pages (Projects, Team gallery) are built directly
    into templates rather than Markdown; those are noted below.
- **Images** go in `static/images/` (e.g. `static/images/news/`, `static/images/gallery/`,
  `static/images/projects/`). Reference them by path, e.g. `images/news/my-photo.jpg`.
- **The body of a content file is just HTML** wrapped in some front matter at the top
  (the block between the `---` lines). You can use plain HTML tags like `<p>`, `<a>`, `<ul>`.

### Front matter cheat sheet

```
---
title: "The headline of the post or page"
date: 2026-05-25          # news posts only; controls ordering
draft: true               # if present and true, the item is NOT published (see below)
aliases: ["/2026/05/25/some-slug/"]   # optional old-style URL
image: "images/news/thumb.jpg"        # optional thumbnail; falls back to the Nimbus logo
---
```

### Drafts — the review workflow

Set `draft: true` in the front matter to keep something **out of the live site** while
it is being reviewed. Remove that line (or set it to `false`) to publish it. To preview
drafts locally, run `hugo server -D` (the `-D` includes drafts).

---

## Adding a news post

1. Create a new file in `content/news/` named `YYYY-MM-DD-short-slug.md`
   (e.g. `2026-07-20-see-us-at-pearc26-in-minneapolis.md`). The date in the filename should
   match the `date` in the front matter.
2. Use this template:

   ```
   ---
   title: "Your Headline"
   date: 2026-07-20
   draft: true
   aliases: ["/2026/07/20/your-headline-slug/"]
   ---

   <p>First paragraph. Integrate links inline like
   <a href="https://example.org/" target="_blank" rel="noopener">this</a>.</p>

   <p>Second paragraph.</p>
   ```
3. Write a couple of short paragraphs. **Integrate links into the text** rather than
   listing bare URLs, and include links to any resources, papers, deliverables, project
   sites, and student work you mention.
4. To add a thumbnail, drop the image in `static/images/news/` and add
   `image: "images/news/your-image.jpg"` to the front matter. If you omit it, the post
   uses the Nimbus logo automatically.
5. Leave `draft: true` until it has been reviewed, then remove that line to publish.

---

## Updating publications

- File: `content/publications/index.md`.
- Papers are grouped under year headings (`<h4 class="wp-block-heading">2025</h4>`) inside
  `<ul class="wp-block-list">` lists. Add the newest papers to the top of the correct year,
  or add a new year heading above the others.
- Each entry follows this pattern:

  ```
  <li><strong>Paper Title</strong>. Authors. <em>Venue</em>, Date. DOI/notes.
  (<a href="https://link-to-pdf">pdf</a>)</li>
  ```
- Hosted PDFs can live in `static/files/papers/` and be linked as
  `/files/papers/filename.pdf`, or you can link to an external DOI/publisher/arXiv URL.

---

## Editing the Projects page

- File: `layouts/projects/single.html` (this page is a template, **not** a Markdown file).
- It has two sections: `<h2>Active Projects</h2>` and `<h2>Past Projects</h2>`.
- Each project is a `<div class="project-item">` block with a logo, a description, and a
  links row. To **move** a project between Active and Past, cut its block and paste it into
  the other section. To **add** one, copy an existing block and edit it.
- Logos live in `static/images/projects/` (e.g. `chameleon.png`). If a project has no logo
  yet, you can omit the `<img class="project-logo" ...>` line until one is added.

---

## Editing the Jobs page

- File: `content/jobs/index.md`.
- When there is **no open posting**, the page shows a short "watch this space" message
  (its current state).
- **Archived postings** are kept in `drafts/jobs/` at the repository root. This folder is
  outside Hugo's `content/` tree, so nothing in it is ever published — it is a version-
  controlled history of past postings you can reuse.
- **To post a new job:** open the most relevant file in `drafts/jobs/`, copy its HTML body
  into `content/jobs/index.md` (keep that file's front matter), then update the title, the
  "Posted" date, and the **Apply Here** link, and adjust the text as needed.
- **To take a posting down:** save a copy of the current body into `drafts/jobs/` (name it
  `YYYY-MM-DD-role.md`) so it can be restored later, then replace `content/jobs/index.md`
  with the "watch this space" message.

---

## Adding gallery photos

- File: `layouts/team/single.html` (the gallery is a template, at the bottom, under
  `<h2>Picture Gallery</h2>`).
- Photos are grouped **by year**, newest first, each in an `<h3>YEAR</h3>` heading followed
  by a `<div class="gallery-grid"> ... </div>`.
- To add a photo:
  1. Put the image file in `static/images/gallery/`.
  2. Add a `<figure>` inside the right year's grid:
     ```
     <figure>
       <img src='{{ "images/gallery/your-photo.jpg" | relURL }}' alt="short description">
       <figcaption>Names of people shown (note team member vs. collaborator),
       event, and date.</figcaption>
     </figure>
     ```
- To add a **new year**, copy an existing `<h3>YEAR</h3>` + grid block and place it above
  the others.
- Captions should name the people, say whether they are **team members or collaborators**,
  and give the event and date.

---

## Publishing your changes

Publishing = committing your changes to the `main` branch. GitHub then rebuilds and
deploys the site automatically (via `.github/workflows/hugo.yml`), usually within a couple
of minutes.

- **In the GitHub web editor:** edit the file, then use "Commit changes" (commit to `main`,
  or open a pull request if you want review first).
- **From a local clone:**
  ```
  hugo server -D        # preview locally at http://localhost:1313 (includes drafts)
  git add -A
  git commit -m "Describe your change"
  git push origin main  # this triggers the deploy
  ```
- Remember: anything with `draft: true` will **not** appear on the live site until you
  remove that flag.

---

## Questions / handoff notes

- If something doesn't show up after publishing, check that `draft: true` was removed and
  that the file is in the right folder.
- For anything template-related (Projects, gallery, overall layout) that you're unsure
  about, ask the team's website maintainer before pushing to `main`.
