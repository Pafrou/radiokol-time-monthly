# RADIOKOL — Session Time Converter

A static page that shows RADIOKOL session times (English/Français/Português),
set in Switzerland time, automatically converted to each visitor's own
timezone using their browser.  No backend, no manual per-country setup.

Live at: `https://<your-github-username>.github.io/<repo-name>/`
(set this up once via Settings → Pages → Deploy from branch → main)

## Monthly update (the only routine task)

1. Open `sessions.js` in this repo on GitHub.
2. Click the pencil icon (Edit this file).
3. Update the three `swissDateTime` values — always Switzerland time,
   format `"YYYY-MM-DDTHH:MM:00"`.
4. Commit directly to `main`. GitHub Pages redeploys automatically,
   usually within a minute.

Do not edit `index.html` for routine monthly updates — it never needs
to change unless you want to redesign the page itself.

## Linking from the HubSpot email

Each "See your time" button in the HubSpot email should link to:

```
https://<your-github-username>.github.io/<repo-name>/#en
https://<your-github-username>.github.io/<repo-name>/#fr
https://<your-github-username>.github.io/<repo-name>/#pt
```

The `#en` / `#fr` / `#pt` suffix matches the `id` field in `sessions.js`
for each session. Clicking it scrolls to and highlights that specific
event, and auto-opens its time details.

If you ever add or rename a session, just make sure the `id` you use
in `sessions.js` matches the `#id` used in the email link.

## Files

- `index.html` — the page itself (design, layout, conversion logic).
  Rarely needs editing.
- `sessions.js` — the three session dates/times/links. Edited monthly.
- `README.md` — this file.
