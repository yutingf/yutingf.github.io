# Updating this website

This site is built with Hugo + Hugo Blox and deploys automatically to GitHub Pages
on every push to `main`. You edit plain Markdown; GitHub builds and publishes it.
No need to run anything locally for routine edits.

## Add a publication (paper, report, book chapter, brief)

1. In `content/publication/`, create a new folder. **The folder name is the permanent
   URL slug** — use lowercase words with hyphens, e.g. `my-new-paper`. Never rename it later.
2. Inside, create `index.md`:

   ```yaml
   ---
   title: "Full Paper Title"
   date: 2026-01-01
   authors: ["Rachel Yuting Fan", "Co Author"]
   publication_types: ["journal_article"]   # see list below
   publication: "Journal or Venue, Vol(Issue), Pages"
   abstract: "Optional short abstract."
   tags: ["artificial intelligence", "development"]
   links:
     - name: "Paper (PDF)"
       url: "files/my-new-paper.pdf"        # PDF goes in static/files/
     - name: "Publisher's Version"
       url: "https://doi.org/..."
   ---
   ```
3. Put the PDF in `static/files/` with a matching name.
4. Commit and push. The paper appears on the Writings page, the right tab, the homepage
   research areas (by `tags`), and gets automatic "See Also" links.

**`publication_types` values → Writings tab:** `journal_article` → Articles · `working_paper`
→ Working Papers · `report` → Reports · `policy_brief` → Briefs & Columns ·
`book` / `book_chapter` → Books · `presentation` → Presentations.

## Turn on visitor analytics (visits + countries)

1. Create a free Cloudflare account → **Web Analytics** → "Add a site" → enter
   `yutingf.github.io` → copy the **beacon token**.
2. In `hugo.yaml`, set `cloudflare_analytics_token: "YOUR_TOKEN"`. Push. Done.

## Swap the homepage photo

Replace `static/images/profile.jpg` with a square photo (about 480×480). Keep the same name.

## Edit the homepage intro / published-in / peer-review lines

All in `content/_index.md`.

## The People page — REVIEW THE LINKS

The People page is generated automatically from the co-authors listed on your
publications. Their external links were **guessed by web search** and live in
`data/coauthors.json`. **Some may point to the wrong person or a stale page — review
each one.** To fix or add a link, edit `data/coauthors.json` (key = the author's exact
name). Co-authors with no entry there show as a name without a link.

## Preview locally (optional)

```bash
cd yutingf.github.io
npm install            # first time only
hugo server
```
Open http://localhost:1313/ .
