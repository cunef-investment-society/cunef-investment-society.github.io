# Handover — running the CUNEF Investment Society site

Everything the next co-head needs, in one place. If you read only one file, read
this one.

## What this is

A public website for society members. Live at:

    https://cunef-investment-society.github.io

It is a single page (index.html) plus a logo, some photos, and downloadable
documents. It has no login and needs no maintenance to stay online — it runs on
GitHub's servers, not on anyone's computer.

## Where everything lives

- **The website** — this GitHub repository, `cunef-investment-society.github.io`,
  inside the `cunef-investment-society` organization.
- **The documents members download** — the `docs/` folder in this same repo.
- **Editable working files** (things the committee edits together) — Google Drive.
  Finished files that go on the site get uploaded to `docs/` here.

## The three things you'll actually do

### 1. Add or change a resource (the CV template, a guide, etc.)

1. Put the finished file (PDF, DOCX, XLSX) in the `docs/` folder: repo → `docs`
   → Add file → Upload files. Name it lowercase, hyphens, no spaces, no accents,
   e.g. `valuation-guide.pdf`.
2. Open `index.html`, click the pencil to edit.
3. Search (Cmd+F) for the resource in the settings block near the top, and put
   the file's path in its `url`, in quotes: `url: "docs/valuation-guide.pdf"`.
4. Commit. Wait a minute. The row goes live.

An empty `url: ""` shows the row as grey "Coming soon" — safe to leave.

### 2. Change contacts, join links, or any wording

Everything editable is in `index.html`, in the block marked **PART 1 — SETTINGS**
at the top. The comments there explain each field. Wording of the page sits in
**PART 3 — PAGE TEXT**, with a labelled banner over every section.

Three rules that prevent almost every breakage:
- text goes inside "double quotes"
- every item in a list ends with a comma
- never delete a { } or [ ] bracket

If the page ever goes blank after an edit, you removed a quote, comma or bracket.
Open the file → History → restore the last working version. Nothing is ever lost.

### 3. Hand it to the next person

1. Make sure they have a GitHub account with two-factor authentication on.
2. Organization → People → Invite member → set role to **Owner**.
3. They accept the invite.
4. They test it: change one word on the site, commit, confirm it appears.
5. Pass on the document store (Drive access) too.
6. Remove yourself from the organization.

The URL never changes and the site never goes down during handover.

## Accounts and access

- The site is owned by the **organization**, not by any one person. That is what
  lets it survive graduations.
- Keep the Owner list to the current co-heads only.
- See SECURITY.md for the full security posture. The short version: 2FA on every
  Owner account, and never put private data in this public repo.

## If something breaks

- **Site shows a 404** — usually a filename typo or the wrong case in a link, or
  Pages is still rebuilding (wait 2 minutes). Check the file exists in the repo at
  the exact path your link uses.
- **Page goes blank** — a broken quote/comma/bracket in index.html. Restore from
  History.
- **A photo shows as a broken icon** — the file isn't in `assets/`, or the name
  in the code doesn't match the file exactly (case included). The page falls back
  to initials if a photo is missing, so this won't break the layout.
- **HTTPS warning** — Settings → Pages → tick "Enforce HTTPS".

## Ideas for whoever comes next

Things the site was built to grow into but doesn't have yet:
- An archive section: past speakers, office visits, competition results, by year.
  This is what makes the society look established to new members and to firms.
- A custom domain (about €10/year) so the address belongs to the society forever.
- The technical guides, question bank and trackers — the resource rows are
  already there, waiting for the documents.
