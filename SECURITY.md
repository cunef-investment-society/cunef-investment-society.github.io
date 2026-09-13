# Security — how this site is protected

Read this before worrying about security. It explains what protects the site,
what doesn't apply, and the few rules that actually matter.

## The one-paragraph version

This is a public, read-only website. There is no login, no database, no user
accounts and no private data on it — everything on the page is meant to be seen
by everyone. That means there is almost nothing to attack. The real security is
on the GitHub accounts that can *edit* the site, not on the site itself. Keep
two-factor authentication on those accounts and never put private information in
this repository, and you have done the part that counts.

## What protects the site

**Only Owners can change it.** Nobody can edit a single character of this site
unless they are signed in to GitHub as an Owner of the `cunef-investment-society`
organization. Editing is gated entirely by GitHub accounts. Nothing in the HTML
grants or restricts that — the file could say anything and it would make no
difference to who can change it.

**HTTPS.** All traffic is encrypted. GitHub provides this automatically. Confirm
it stays on: repo → Settings → Pages → "Enforce HTTPS" ticked.

**No attack surface.** The usual ways websites get hacked — WordPress plugins,
databases, login forms, server-side code — none of them exist here. A folder of
static files cannot be SQL-injected or have an admin password guessed, because
there is no database and no admin password. This is genuinely more secure than
most conventional sites, not less.

**Full version history.** Every past version of every file is saved. If the site
is ever broken or vandalised by someone with access, restore the last good
version in two clicks: open the file → History → pick a version → restore.

**Content-Security-Policy.** A meta tag in index.html tells the browser it may
only load code, styles, images and fonts from a short approved list. Even in the
unlikely event that stray content were ever introduced, the browser refuses to
run anything from an unapproved source. This is the main thing that "hardens the
HTML" — and it is already in place.

## What does NOT apply, and why

- **Login / member authentication** — there is nothing private to sign in to.
  Adding a login would be protecting an empty room.
- **Clickjacking headers (X-Frame-Options / frame-ancestors)** — these only work
  as real HTTP headers, which GitHub Pages does not let you set. They are
  silently ignored inside a meta tag, so they are deliberately not included; a
  tag that does nothing is worse than no tag, because it looks like protection.
- **Intrusion monitoring / firewalls** — these guard servers. There is no server
  here; GitHub runs the infrastructure.

## The rules that actually matter

1. **Two-factor authentication on every Owner account.** This is the single most
   important control. It stops someone editing the site even if a password leaks.
   Require it before adding anyone as an Owner.
   GitHub → profile → Settings → Password and authentication → enable 2FA.

2. **Never put private data in this repository.** It is public — anyone on earth
   can read every file in it, including files not linked from the page. Member
   lists, personal phone numbers, anything internal: those live in a restricted
   Google Drive, never here. The contact details on the page are only there
   because the co-heads chose to make them public.

3. **Keep the Owner list short.** Only current co-heads. Remove people the moment
   they hand over. Fewer keys, fewer ways in.

4. **Optional: protect the main branch.** Repo → Settings → Branches → add a rule
   for `main` with "Restrict deletions" and "Block force pushes". Guards against
   the history being wiped. A nice-to-have, not an exposure.

## Handover security checklist

When passing the society to the next co-head:

- [ ] They have enabled 2FA on their GitHub account.
- [ ] They are added as an **Owner** of the organization (not just a Member).
- [ ] They have confirmed they can edit the site (change a word, commit, see it).
- [ ] The document store (Drive shared drive or society account) has been passed
      to them too — see HANDOVER.md.
- [ ] The outgoing head is removed from the organization once the above is done.
