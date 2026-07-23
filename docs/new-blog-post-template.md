# New Blog Post Template

This is a **fill-in-the-blanks template** for adding a news post to nimbusproject.org.
Copy it, replace the parts in `[[ SQUARE BRACKETS ]]`, and you have a finished post — no
web-development knowledge required.

If anything here is unclear, the longer [How to Update the Website](updating-the-website.md)
guide explains the same steps in more detail.

> **You can do all of this in your web browser.** Everything below is just editing a text
> file on GitHub. You do **not** need to install anything or use the command line.

---

## Before you start: two things to decide

1. **The date** of the post — usually today. Write it as `YYYY-MM-DD` (e.g. `2026-07-23`).
2. **A short "slug"** — a few words from the headline, in lowercase, joined by hyphens.
   - Headline: *"See Us at PEARC26 in Minneapolis"*
   - Slug: `see-us-at-pearc26-in-minneapolis`

You'll use both in the **file name** and again inside the post.

---

## Step 1 — Create the file

1. Go to the repository on GitHub and open the **`content/news/`** folder.
2. Click **Add file → Create new file**.
3. Name the file using your date and slug, ending in `.md`:

   ```
   [[ YYYY-MM-DD ]]-[[ your-slug ]].md
   ```

   Example: `2026-07-23-nimbus-team-welcomes-new-engineer.md`

---

## Step 2 — Paste in the template and fill it out

Copy everything in the box below into the file, then replace each `[[ … ]]` placeholder.
Keep the `---` lines and the `<p>` tags exactly as they are.

```
---
title: "[[ Your Headline Here ]]"
date: [[ YYYY-MM-DD ]]
draft: true
aliases: ["/[[ YYYY ]]/[[ MM ]]/[[ DD ]]/[[ your-slug ]]/"]
---

<p>[[ Write your first paragraph here. ]]</p>

<p>[[ Write another paragraph here. Add as many as you like. ]]</p>
```

### What each front-matter line does

| Line | What to put there |
| --- | --- |
| `title` | The headline, in quotation marks. |
| `date` | The post's date as `YYYY-MM-DD`. This controls the ordering on the news page. |
| `draft` | Leave as `true` while writing. Removing it later is what **publishes** the post. |
| `aliases` | The old-style web address. Just fill in the same date and slug you already chose. |

---

## Step 3 — Write the body

Write whatever you want between the `<p>` and `</p>` tags. A few formatting notes:

- Each paragraph goes between `<p>` and `</p>`. Add as many paragraphs as you need.
- To add a link, wrap the words you want to link like this:

  ```
  <p>The team presented at
  <a href="https://pearc.acm.org/" target="_blank" rel="noopener">PEARC26</a>.</p>
  ```

  (`target="_blank" rel="noopener"` just makes the link open in a new tab — keep it.)
- Need a bulleted list? Use this pattern:

  ```
  <ul class="wp-block-list">
  <li><strong>Name</strong> &mdash; short description.</li>
  <li><strong>Name</strong> &mdash; short description.</li>
  </ul>
  ```
- Special characters: write `&mdash;` for an em dash (—), `&ndash;` for a range dash (–),
  and `&rsquo;` for a curly apostrophe (’). Plain straight quotes are fine too.

---

## Step 4 (optional) — Add a thumbnail image

If you skip this, the post automatically uses the Nimbus logo.

1. Put your image in the **`static/images/news/`** folder (Add file → Upload files).
2. Add this line to the front matter, just below the `aliases` line:

   ```
   image: "images/news/[[ your-image-file.jpg ]]"
   ```

---

## Step 5 — Publish

While `draft: true` is in the front matter, the post is **saved but not visible** on the
live site. That's the review stage.

1. When you're happy with the post, **delete the `draft: true` line** (or change it to
   `draft: false`).
2. Commit the change (the green **Commit changes** button in GitHub). Commit to `main` to
   publish immediately, or choose "Create a new branch and start a pull request" if you'd
   like someone to review it first.
3. The site rebuilds automatically and your post appears within a couple of minutes.

To keep it hidden a bit longer, just leave the `draft: true` line in place and commit —
you can come back and remove it whenever you're ready.

---

## A fully filled-in example

This is what a finished file looks like — file name
`2026-07-23-nimbus-team-welcomes-new-engineer.md`:

```
---
title: "Nimbus Team Welcomes New Research Software Engineer"
date: 2026-07-23
draft: true
aliases: ["/2026/07/23/nimbus-team-welcomes-new-engineer/"]
image: "images/news/team-2026.jpg"
---

<p>We&rsquo;re excited to welcome <strong>Jordan Lee</strong> to the Nimbus team as a
Research Software Engineer. Jordan will work on
<a href="https://chameleoncloud.org/" target="_blank" rel="noopener">Chameleon</a>,
focusing on tools that make experiments easier to reproduce.</p>

<p>Jordan joins us from the University of Example, where they built data pipelines for
climate research. You can read more about the team on our
<a href="https://nimbusproject.org/team/" target="_blank" rel="noopener">team page</a>.</p>

<p>Welcome aboard, Jordan!</p>
```

When this is ready to go live, remove the `draft: true` line and commit. That's it.

---

## Quick checklist

- [ ] File is in `content/news/` and named `YYYY-MM-DD-your-slug.md`
- [ ] `title`, `date`, and `aliases` are filled in
- [ ] Every `[[ … ]]` placeholder has been replaced
- [ ] Links are worked into the text and open correctly
- [ ] (Optional) thumbnail uploaded and `image:` line added
- [ ] `draft: true` removed when you're ready to publish
- [ ] Changes committed to `main`
