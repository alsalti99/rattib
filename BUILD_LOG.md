# Rattib · رتّب — BUILD_LOG

TechOlympics 2026 · AI Vibe Coding Challenge · theme: **Education: Reimagining Student Learning and Campus Life (Break the Ordinary)**
Inspired by Cult UI (Halo Tabs, Halo Input, Halo Button, Halo Card, Halo Notification, Hero Color Panels) and the Harvest style reference. All components were rebuilt in plain HTML/CSS/JS: no React, no npm.

## Concepts
The team brought one concept: Rattib Untangle (the brief was sent with `/build`).

## Chosen concept
- **Name:** Rattib · رتّب ("arrange / put in order")
- **Pitch:** Paste class-group chaos in Arabic and English and get a calm, time-blocked week back.
- **Problem & people:** College students in Oman (MCBS, SQU, UTAS and others) gather deadlines from WhatsApp groups, Moodle and lecturers, then discover the night before that three are due at once.
- **Signature moment:** A tangled knot of deadline threads sits over drifting translucent panels. On Untangle, the threads straighten into weft lines while the panels settle into the Sun–Thu columns of a loom/week grid. Three deadline cards slide in with a soft whoosh and chime.
- **Core features:** (1) bilingual chaos parser with inline highlights; (2) physics knot + week planner; (3) panic check + cut a thread with an extension email.

## Design tokens
| Token | Hex | Role |
|---|---|---|
| mist | #F4F6FB | page background (Harvest cream role) |
| white | #FFFFFF | cards, inputs (frosted glass on ≤4 panels) |
| blue | #2B59FF | the one functional accent: buttons, links, active tab, focus |
| violet | #7A55F5 / text #6A45E6 | brand moments, gradient rims (violet text uses #6A45E6 for AA) |
| sky / lilac | #6BC8FF / #B8A5FF | atmosphere only: washes, spotlight, thread glows |
| ink / slate | #0F1330 / #586078 | text / secondary text |
| line | #E3E7F1 | borders, dividers |
| risk | teal #0B7F72 · amber #9A5B00 · coral #C93A3F | safe · watch · at risk |

- **Type:** Figtree (UI, .015em tracking), Fraunces (hero headline only, ~72px). Arabic: IBM Plex Sans Arabic (UI) and Amiri (hero headline). Letter-spacing is 0 in Arabic so the letters still join.
- **Radii:** buttons/inputs 16px · cards 20px · tags 999px. Max width 1200px, section gaps 64–80px, card padding 32–40px.
- **Elevation:** cards `6px 4px 24px rgba(43,89,255,.14)`, buttons `0 1px 4px rgba(15,19,48,.2)`. Only 4 blurred panels: header, paste box and the 2 hero preview cards. Everything else is solid white with a glass highlight.
- **Motif:** an Omani weave band (inline SVG diamonds in line gray and lilac) frames the loom and the footer.
- **Contrast check:** every team color passes AA in its role (slate on mist 5.8:1, blue on white 5.3:1, violet text #6A45E6 on mist 5.4:1, teal/amber/coral ≥4.5:1 on white). No lightness changes were needed beyond the team's own violet-text rule.

## Timeline
- [12:29] /start: empty folder; jsDelivr and Google Fonts reachable; built-in browser pane available, Python 3.14 as fallback.
- [12:40] /build: concept locked, tokens and plan written; building index.html.
- [13:02] /build done: single `index.html` (~310 KB, mostly the two inlined photos). Parser 25/25 on the test set below. All three features verified in the browser pane at 1440×900 and 390×844, in English and Arabic (RTL), with a clean console. Fixes made during QA: Lissajous pairs that collapsed a thread into a line, settings grid leaving an empty column, deadline cards spilling off the loom on phones, the hero preview card covering the Wed/Thu labels after weaving, the singular "1 line needs a date" toast, title filler ("worth", "ما له … للحين"), and `dir="auto"` for mixed Arabic/English text. Team photos are cropped to 480 px head-and-shoulders JPEGs (~38 KB each) and inlined; Omar's night photo was brightened with gamma only.
- [13:08] team request → the entry page is now just the logo and the name رتّب: the knot strokes draw in, a halo breathes behind the logo, and the weave band runs along the bottom, with no text about sound. A tap, click or key anywhere enters; that gesture starts the calm sound (unless the visitor muted it on an earlier visit) and the header toggle and M still mute. The wordmark uses IBM Plex Sans Arabic, because Amiri's shadda floated too high at display size and the gradient text clipped it. Escape enters quietly. Verified at 1440 and 390 with a clean console.

- [13:10] team request → the intro now plays by itself (logo draws, رتّب rises) and fades into the page after about 2.3 s; a tap or key skips it. The weave border was removed from the intro, and it no longer has a button or focus ring. Sound now starts on the visitor's first tap or key anywhere (browsers block audio before a gesture) unless they muted it before; tapping the sound toggle or pressing M is left to the toggle itself.

- [13:13] /pitch → PITCH.md: 5-min script with timings and demo clicks (AlSalt: problem + close; Omar: demo + how we built it), a pre-stage checklist, a 12-question Q&A bank and a short code tour.

- [13:16] team request → sound is on by default: the toggle shows on from page load, the audio graph starts at once, and the first tap or key resumes it if the browser held it. Muting is remembered.

- [14:35] team request → the site is served on port 5000 on all interfaces (`python -m http.server 5000 --bind 0.0.0.0`). It loads at http://localhost:5000 and the venue Wi-Fi address, and the existing Windows Firewall rule already allows Python inbound.

- [19:05] team request → all music removed: the ambient pad, the generative melody and the tense/resolve chords are deleted from the engine, and only the short UI effects remain (tick, click, pluck, snip, whoosh, chime). Deployed with `serve.py` (one Python process, one thread per address) on port 5000, only on 127.0.0.1, the ZeroTier address and the home Wi-Fi address. Other addresses refuse the connection, and only `/` and `/index.html` are served (other paths return 404). All three addresses load, with a clean console.

- [19:17] fix → the Arabic hero line "ورتّب أسبوعك." had the shadda and hamza clipped at the top (gradient text only paints inside its box). Arabic `.l2` now has 0.4em top padding offset by a negative margin, so the marks show and the spacing is unchanged. Verified after reload.

- [20:21] deploy → public GitHub repo **github.com/alsalti99/rattib** (README with preview image, topics). Published on GitHub Pages at **alsalti99.github.io/rattib** and on Netlify at **rattib-om.netlify.app** (the name `rattib` was taken). Netlify team protection was switched off for this site only, at the team's request. Both live URLs were verified in the browser: intro, Untangle, team photos, clean console. The repo excludes the local-only files (`serve.py`, `PITCH.md`, `.claude/`), and network addresses were removed from this log.

- [20:33] team request → **Ministry prayer times + city picker**. Scraped the Ministry of Awqaf and Religious Affairs calendar (mara.gov.om, one POST per city per day; 888 requests at about 2/s, 0 failures): Muscat for every day from 1 Oct 2026 to 31 Jan 2027, and the 85 other cities every 15 days. City times are not fixed offsets from Muscat, so the planner interpolates each city's offset between sample days; 16 random live spot checks were within 1 minute. The data is embedded as a 16 KB constant (pages can't fetch the Ministry site: CORS, and offline-safe for the venue). A city dropdown sits in the Week tab and in the setup panel (86 cities, names as on the Ministry page); Muscat is the default, and the visitor's pick is saved under its own key so it survives reloads and Reset. Prayer blocks now use the exact day's times (no ≈). Fixed an if/else chain broken while removing the old time inputs (caught in the browser, then checked with `node --check`). Netlify: the "Powered by Netlify" badge was turned off (`built_with_badge_enabled: false`). The name `rattib` is held by another Netlify account, so the team kept **rattib-om**.

- [20:43] team requests → (1) **Halo-style city picker**: the native selects became a custom combobox in the app's style. It's a pill button with a gradient pin, and it opens a white card with a gradient rim. There's a search box that matches Arabic loosely (ignores harakat, alef forms and the leading ال) and also English names ("salalah" → صلالة). Each city shows today's Fajr and Maghrib, the selected one gets a gradient bar and check, and it works with the keyboard (arrows, Enter, Escape, aria-activedescendant) and flips to stay on screen. (2) **Preview video**: the team's own `preview.mp4`, used as is (byte-identical copy, 30 s, 720p), sits at the top of How it works. It never autoplays and has a poster frame. The README got the logo under the title (`assets/logo.svg`) and a play-button thumbnail that opens the video. (3) **Netlify ↔ GitHub auto-deploy**: a read-only deploy key on the repo plus a push webhook to Netlify, with `netlify.toml` (no build, publish root). Every push to `main` now redeploys rattib-om.netlify.app; GitHub Pages already rebuilds on push.

### Parser test (rule-based, today = Tue 6 Oct 2026 12:45)
| # | Input (messy) | Result | Pass |
|---|---|---|---|
| 1 | `calc quiz tmrw, OS lab thu, ENG essay 14 oct, عرض الإدارة يوم الأحد` | 4 tasks: Calc quiz Wed 09:00 (assumed) · OS lab Thu 23:59 · ENG essay Wed 14 Oct · عرض الإدارة Sun 09:00, presentation, Management | ✅ |
| 2 | `[06/10/2026, 9:14 PM] Sara (CS rep): Reminder guys!! Calc quiz tmrw 9am 📚` | timestamp + sender stripped → "Calc quiz", Wed 09:00 | ✅ |
| 3 | `… ENG report due tmrw 11:59pm, 10%` | ENG report, Wed 23:59, weight 10% (comma part re-joined) | ✅ |
| 4 | `… OS lab 4 submission in 2 days 5pm` | Thu 17:00, lab | ✅ |
| 5 | `[٦/١٠/٢٠٢٦، ٩:٢٢ م] Mazin: مشروع قواعد البيانات بعد يومين الساعة ١١:٥٩ م، ٣٠٪` | Arabic timestamp stripped, Arabic-Indic digits, project, Databases, Thu 23:59, 30% | ✅ |
| 6 | `[…] Huda: anyone has the slides? 😅` | skipped as chat | ✅ |
| 7 | `06/10/2026, 21:31 - Dr. Khalid: Stats midterm next sun 10am, 25%` | Android-style prefix stripped, Sun 11 Oct 10:00, 25% | ✅ |
| 8 | `… ENG essay next wed` | Wed 14 Oct (next week's Wednesday) | ✅ |
| 9 | `… Sara: واجب الإحصاء ما له موعد للحين` | "needs a date" card (assignment, Statistics) | ✅ |
| 10 | `MATH1101 assignment 3 due 14/10 at 5` | course code, 14/10 = 14 Oct, "at 5" = 17:00 | ✅ |
| 11 | `Physics lab report oct 20 11:59pm ~3h` | report, Tue 20 Oct 23:59, 3 h from message | ✅ |
| 12 | `كويز الفيزياء غدًا الساعة ٨ ص` | quiz, Physics, Wed 08:00 | ✅ |
| 13 | `تسليم تقرير المحاسبة يوم الخميس ٥ م` | report, Accounting, Thu 17:00 | ✅ |
| 14 | `امتحان التسويق ١٨ أكتوبر` | exam, Marketing, Sun 18 Oct 09:00 (assumed) | ✅ |
| 15 | `networks presentation next fri 20%` | Fri 16 Oct, 20% | ✅ |
| 16 | `hw for programming tonight` | assignment, today 23:59 | ✅ |
| 17 | `Econ essay in 3 days` | Fri 9 Oct | ✅ |
| 18 | `بكرة واجب البرمجة` | assignment, Programming, Wed | ✅ |
| 19 | `project proposal DB next week` | project, Databases, Sun 11 Oct (assumed start of next week) | ✅ |
| 20 | `9:05 PM - Lina: chem quiz today 3pm` | time-only prefix stripped, today 15:00 | ✅ |
| 21 | `<Media omitted>` | skipped | ✅ |
| 22 | `ok thanks 👍` | skipped | ✅ |
| 23 | `Biology final exam 2/11` | exam, Mon 2 Nov | ✅ |
| 24 | `مقالة الإنجليزي بعد ٣ أيام` | essay, English, Fri 9 Oct | ✅ |
| 25 | `stats hw tmrw 17:00 worth 5%` | assignment, Wed 17:00, 5% (title cleaned after fix) | ✅ |

## How it works
Code lives in `index.html`, script sections 0–5 (Config & data · State & storage · Sound engine · Features · Motion · Init).

**1. Bilingual chaos parser** (`3.2 Parser`)
- Splits the paste into lines, strips WhatsApp prefixes (`[date, time] Name:`, `date, time - Name:`, `time - Name:`, phone numbers) and system lines (`<Media omitted>`). Lines are then split on commas, and parts with no task of their own (like `10%`) are re-joined.
- Arabic-Indic digits and ٪ are mapped one-to-one to ASCII, so highlight positions still line up with the original text. Ordered regular expressions find weight → hours → date → time → type → course, and each match is stored as a span that the card highlights.
- Type sets the editable effort estimate. With no time given: 09:00 for quiz/midterm/exam/presentation, 23:59 otherwise (labelled "time assumed"). A line counts as a task only with a type, a course, or a date plus a due word; other chat is skipped. Undated tasks become "needs a date" cards with a date picker. There's also a manual form.

**2. Physics knot + week planner** (`3.4 Planner`, `3.5 Loom`)
- Planner: each day from wake to sleep is cut into 15-min slots. A slot is removed if it overlaps a class, a prayer ±15 min (approximate Muscat times, editable), the past, or a done block. A shared `fill()` applies the daily cap (6 h, 2 h on Fri/Sat) and a 30-min break after 2 h. Earliest deadline first: each slot goes to the task with the nearest due date, aiming to finish `buffer` (4 h) early, and may dip into the buffer, which flags the task as watch.
- Loom: one verlet rope per task (26 points, ≤12 threads), springing toward a home shape that blends a rose-curve tangle with a straight row as `loose` goes from 0 to 1. Dragging a point raises `loose` (rising pluck). Untangle animates every `loose` to 1. Width = 1.5 + 0.45 × hours, the bead shows risk colour, and the most-at-risk thread is coral. Pixel ratio is capped at 1.5, it pauses off-screen and in hidden tabs, and it is static under reduced motion.
- Week: 7-day grid (agenda list on phones). Click a block → "Why here?" (deadline, buffer, EDF, neighbouring class or prayer, the day's cap) and Mark done. There are also Re-plan and Copy my week.

**3. Panic check + cut a thread** (`renderPanic`, `Planner.suggest`, `cutTask`, `emailText`)
- Load = hours needed for this task and everything due before it ÷ free study hours before (due − buffer), using the same `fill()` so the numbers match the plan. Safe < 75 %, watch 75–100 % or in buffer, at risk > 100 % or not fully scheduled.
- Suggestion: among tasks due no later than the riskiest one, the lowest written weight (unknown = 100 %); ties go to more hours. It re-plans without that task to show before/after load, at-risk count and tension.
- Apply → the thread snaps (snip sound, falls with gravity), the tension meter shows "−N h", the week re-plans, and an extension email (English or Arabic, with name/lecturer fields) appears ready to copy. Cut threads can be restored.

**Hero moment** (`3.9 Hero`): Untangle parses the box. The threads straighten into weft rows while 5 wash panels transition from crossed angles into Sun–Thu columns, then three deadline cards slide in (paste order) and a chime plays. Any click or key skips; Replay re-tangles and plays again. Pulling every thread free by hand also completes the weave.

**Sound** (`2 Sound engine`): skill engine with UI sound effects only and no background music. Added SFX: pluck (pitch rises with looseness), snip, chime. Intro: logo and رتّب only, auto-enters after ~2.3 s; sound starts on the first tap or key anywhere (the browser needs a gesture). Header toggle and M key mute it, and the choice is remembered.

**Honesty notes:** rule-based (not AI), nothing uploaded, sample deadlines/timetable labelled sample, prayer times labelled approximate, hours labelled estimates.

## AI pipeline used
- Claude Code (Opus) in the Claude desktop app: /start → /build → /judge → /polish → /pitch → /ship.
- Skills: premium-web-design (art direction, motion recipes, i18n pattern), sound-design (Web Audio engine with custom SFX; music removed at the team's request).
- Browser-verified QA in the app's built-in browser pane (console, 1440×900, 390×844, every control).
