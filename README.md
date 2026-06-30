# RADIOKOL — Session Time Converter

A static page that shows RADIOKOL session times (English/Français/Português),
set in Switzerland time, automatically converted to each visitor's own
timezone using their browser. No backend, no manual per-country setup.

Live at: `https://pafrou.github.io/radiokol-time-monthly/`

## Recommended: just ask Claude

The easiest way to do the monthly update is to open a chat with Claude
(claude.ai) and give it the three new dates/times — e.g. "English: Monday
20.7, 16:00 / Français: Thursday 23.7, 16:00 / Português: Friday 24.7, 15:00".

Claude has a skill called **radiokol-monthly-update** that already knows
this repo's URL, the file formats below, the email template, and the
preferred wording (language name first, e.g. "English • Monday 20.7 —
16:00"). It will hand back two ready-to-paste blocks: the new `sessions.js`
content, and the complete HubSpot email HTML with dates and links already
filled in. No need to remember the manual steps below in that case — they're
here mainly as a fallback, or for reference if doing it without Claude.

## Monthly update (manual fallback)

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
https://pafrou.github.io/radiokol-time-monthly/#en
https://pafrou.github.io/radiokol-time-monthly/#fr
https://pafrou.github.io/radiokol-time-monthly/#pt
```

The `#en` / `#fr` / `#pt` suffix matches the `id` field in `sessions.js`
for each session. Clicking it scrolls to and highlights that specific
event in light blue (highlight stays for the rest of the visit), and
auto-opens its time details.

Email session lines are formatted **Language • Day DD.M — HH:MM**, e.g.
"English • Monday 20.7 — 16:00" (language name first, bolded).

If you ever add or rename a session, just make sure the `id` you use
in `sessions.js` matches the `#id` used in the email link.

## Files

- `index.html` — the page itself (design, layout, conversion logic).
  Rarely needs editing.
- `sessions.js` — the three session dates/times/links. Edited monthly.
- `README.md` — this file.
