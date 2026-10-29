# MEGA.dev S01E03 · what it shows

The support desk merged 412 date reports into ticket #4471 and marked it as one known issue. The kb's own data shows two causes. This repo files one ticket per cause and adds a signed kb page about them.

## Tickets

| cause | ticket | reports | outcome |
| --- | --- | --- | --- |
| `parser`: the shared parser reads day-first dates month first | [#1](https://github.com/mjmazgaj/mega-s01e03-what-it-shows/issues/1) | 379 | fixed: `fix(dates): parse dd/mm for eu locales` (closed, completed) |
| `hint`: the booking-v3 form hint says MM/DD, and the form reads the date day first | [#2](https://github.com/mjmazgaj/mega-s01e03-what-it-shows/issues/2) | 33 | won't fix: booking-v3 form retired (closed, not planned) |

Engineering closed #4471 on 5 October.

## Page

- Source: [`support-kb/src/routes/kb/incidents/4471/causes/+page.svx`](support-kb/src/routes/kb/incidents/4471/causes/+page.svx)
- As the desk sees it: [`rendered/4471-causes.html`](rendered/4471-causes.html) and [`rendered/4471-causes.png`](rendered/4471-causes.png)
- Signed with the course ticket (frontmatter `signature`), desk ref `DR-200Q-3NJ2`

`support-kb/` is the kb export as it came from the course, with only the new page added.

## How the counts were made

The counts use the kb's own logic in `support-kb/src/lib/kb/causes.ts`:

1. Keep one report per id (the export has 427 rows and 412 unique reports).
2. Find each report's cause from its tenant's locale and booking form.
3. Group the reports by cause.

The render uses the same logic. Intake tags (`meta.intakeTag`) are a guess from the reporter's browser, so the counts do not use them.
