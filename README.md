<div align="center">

# Rattib · رتّب

<img src="assets/logo.svg" alt="Rattib logo" width="112">

### Paste the chaos. Untangle your week.

**A bilingual (English + العربية) deadline untangler for college students in Oman.**
Paste your WhatsApp group chat, Moodle notices and lecturer emails, and get back a calm, time-blocked week planned around your classes and prayer times. Rattib also tells you which deadline is *really* at risk.

[**Open the live site → rattib-om.netlify.app**](https://rattib-om.netlify.app)  ·  mirror: [alsalti99.github.io/rattib](https://alsalti99.github.io/rattib/)

![Single file](https://img.shields.io/badge/single%20file-index.html-2B59FF)
![No build step](https://img.shields.io/badge/build%20step-none-7A55F5)
![English + Arabic](https://img.shields.io/badge/language-English%20%2B%20%D8%A7%D9%84%D8%B9%D8%B1%D8%A8%D9%8A%D8%A9-6BC8FF)
![Privacy](https://img.shields.io/badge/data-stays%20on%20your%20device-0B7F72)

<a href="https://rattib-om.netlify.app/assets/preview.mp4"><img src="assets/preview.gif" alt="30-second Rattib preview: paste the chaos, untangle it, see what's really at risk" width="820"></a>

<sub>▶ Click the preview for the full video with sound</sub>

</div>

---

## The problem
Deadlines reach students from everywhere: class WhatsApp groups, Moodle and lecturer emails. They're half English and half Arabic, buried between "good morning" stickers. Too often we find out the night before that **three things are due tomorrow**.

## What Rattib does

| | Feature | What you get |
|---|---|---|
| 🧵 | **Bilingual chaos parser** | Paste messy chat in English, Arabic or both. WhatsApp timestamps and names are stripped, and each deadline becomes a card with course, type, date, time, hours and weight. The words that gave each detail are highlighted, so you can see *why*. Understands `tmrw`, `next sun`, `14 oct`, `14/10`, `11:59pm`, `بكرة`, `بعد يومين`, `١١:٥٩ م`, Arabic day and month names and Arabic-Indic digits. |
| 🪢 | **Physics knot + week planner** | Every deadline is a thread in a living knot you can drag apart. **Untangle** straightens them into a Sun–Thu week of study blocks placed around your classes, the Ministry's prayer times for your city (±15 min), sleep and a 6 h daily cap. Click any block to see *why it's there* and mark it done. |
| 🚨 | **Panic check + cut a thread** | Compares the hours you need with the free hours you actually have, and labels every task **safe / watch / at risk**. It suggests the lowest-weight task to postpone, with before/after numbers. One click cuts the thread, re-plans the week and writes a polite **extension email** in English or Arabic. |

**Signature moment:** the tangled threads straighten into weft lines while translucent panels settle into the Sunday-to-Thursday columns of a loom, and your deadlines slide into place. The border is a woven pattern inspired by Omani textiles.

## How it works (no magic)
- **Parser:** rule-based regular expressions, not an AI model. Arabic-Indic digits are mapped to ASCII one-to-one so the highlights line up with the original text.
- **Planner:** each day is cut into 15-minute slots; classes, prayer windows, sleep and the past are blocked out. Then it uses **earliest deadline first**, aims to finish a few hours early, and adds a 30-minute break after every 2 hours.
- **Risk:** `load = hours still needed (this task + everything due before it) ÷ free study hours before (due − buffer)`. Under 75% is safe, 75–100% is watch, over 100% is at risk.
- **Knot:** each thread is a 26-point Verlet rope on a `<canvas>`; untangling blends each one from a tangled curve into a straight row.
- **Sound:** short UI effects synthesised live with the Web Audio API (no audio files). Press **M** to mute.

## Honest by design
- 🔒 Everything runs **in your browser**. Nothing you paste is uploaded, data is saved only on your device, and **Reset** clears it.
- 🕌 Prayer times come from the **Ministry of Awqaf and Religious Affairs** calendar ([mara.gov.om](https://www.mara.gov.om/arabic/calendar_page1.asp)) for **86 cities**. The data was saved into the page (Oct 2026 – Jan 2027): Muscat for every day, and other cities on sample days with the days between interpolated (checked against the Ministry site to within 1 minute). Muscat is the default, and the city you pick is remembered.
- 📝 Sample deadlines and the class timetable are labelled **sample**. Hours are **estimates** you can edit.

## Run it
It's a single file. Download `index.html` and double-click it, or serve the folder:
```bash
python -m http.server 8000
```

## Built by
| | |
|---|---|
| **AlSalt Al-Salti** | CEO · Community & social |
| **Omar Al-Salti** | Project Team lead · Idea owner |

Built live at the **IEEE TechOlympics 2026 AI Vibe Coding Challenge** (MCBS, Muscat) with **Claude Code**. Theme: *Education: Reimagining Student Learning and Campus Life*. The full build process, test results and design decisions are in [`BUILD_LOG.md`](BUILD_LOG.md).

UI components were inspired by [Cult UI](https://www.cult-ui.com/) (Halo Tabs, Input, Button, Card, Notification and Hero Color Panels), rebuilt in plain HTML/CSS/JS, plus the Harvest style reference. No university logos and no implied partnerships.
