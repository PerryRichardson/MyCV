# Résumé — Plan (Draft)

Status: **draft for review** — no HTML built. Edit/approve and I'll transcribe `resume.json`, then build `resume.html`.

## 1. Concept
One-page résumé for **industry data science + policy** roles. Single self-contained HTML page: screen view with role-tag filter, print/PDF view as a clean single-column A4/Letter page. Master content, tagged by role, so one file serves both audiences.

Sources (transcribed 1:1, nothing invented):
- `Richardson_Research_Scientist_Resume_1.docx` (primary)
- `MyCV/index.html` (only for items the docx lacks, if you ask)

## 2. File structure
```
MyCV/Resume/
  resume_plan.md   ← this doc
  resume.json      ← master data, tagged entries (edit this)
  resume.html      ← built last; embeds a snapshot of resume.json
  CONTEXT.md       ← session log
```
Placed inside the MyCV repo but in its own folder; `index.html` untouched.
Data: `resume.html` tries `fetch('resume.json')`, falls back to embedded snapshot (file:// blocks fetch). Banner shown on fallback. JSON edits need a manual resync into the HTML.

## 3. Layout (screen; print = same order, no chrome)
```
┌──────────────────────────────────────────────────┐
│ PERRYN RICHARDSON                                │
│ Research Scientist | Computational Bioimaging    │
│ Stellenbosch, SA • phone • email • GitHub        │
├──────────────────────────────────────────────────┤
│ View: [Data science] [Policy] [All]   (screen)   │
├──────────────────────────────────────────────────┤
│ SUMMARY  (2–3 lines)                             │
│ EXPERIENCE                                       │
│   PhD Researcher — SU          2023–present      │
│    • bullets (tagged)                            │
│   MSc Researcher — Rhodes      2021–2022         │
│    • bullets                                     │
│ EDUCATION  (4 one-liners)                        │
│ SKILLS  (grouped chips: 4 groups)                │
│ Referees available on request                    │
└──────────────────────────────────────────────────┘
```

## 4. Sections
- **Header:** name, headline, location, phone, email, (link to MyCV site/GitHub if you want).
- **Summary:** docx summary, trimmed to fit 1 page; wording changes flagged for your review, not silent.
- **Experience:** PhD, MSc. Teaching & Mentoring folded into 1–2 bullets or cut (open Q3).
- **Education:** PhD, Bootcamp, MSc, BSc Hons.
- **Skills:** Programming; Bioimaging & Analysis; Data Science & ML; Platforms & Infrastructure.
- **Referees:** "Available on request".
- **Cut for 1 page:** Strengths, Certifications, Achievements, Publications, Affiliations, Community. Kept in JSON as `"include": false` so they can return.

## 5. Filter behaviour (screen only; approval needed)
Buttons: **Data science / Policy / All**. Bullets and skills carry `tags`; non-matching items dim (not hide) so layout stays stable. Print output = currently selected view, dimmed items removed.

## 6. JSON schema
```json
{
  "meta": {"name": "", "headline": "", "location": "", "phone": "", "email": "", "links": []},
  "summary": {"text": "", "tags": []},
  "experience": [{
    "role": "", "org": "", "dept": "", "start": "", "end": "", "place": "",
    "bullets": [{"text": "", "tags": ["ds", "policy"]}]
  }],
  "education": [{"degree": "", "institution": "", "note": "", "years": ""}],
  "skills": [{"group": "", "items": [{"name": "", "tags": []}]}],
  "extras": {"strengths": [], "certifications": [], "achievements": [], "referees": []},
  "include": {"strengths": false, "certifications": false, "achievements": false}
}
```
Tags: `ds` (data science), `policy`. Inferred by me, shown to you for review before build.

## 7. Visual style spec
**Pending: you will upload inspiration.** Fixed regardless:
- System font stack, no external assets, inline CSS/JS.
- `@media print`: A4 (Letter switchable), ~12–15 mm margins, no shadows/cards, real selectable text, links printed as text, `break-inside: avoid` on each entry, filter bar hidden.
- Mobile: single column, no horizontal scroll.

## 8. Open questions
1. Upload style inspiration (image/URL/file).
2. Paper size: A4 (SA default) — confirm.
3. Teaching & Mentoring: 1 bullet, 2 bullets, or drop?
4. Headline: keep "Research Scientist | Computational Bioimaging" or retarget (e.g. "Data Scientist | Computer Vision & Ecology")? Docx title is research-flavoured.
5. Keep "Available for remote work" line? Add GitHub/website link?
6. Bootcamp "expected 2026": still accurate? (today is Sept 2026)

## 9. Decisions log
- 2026-09-21: Target = industry data science + policy blend.
- 2026-09-21: 1 page; master JSON + tag filter.
- 2026-09-21: Source = docx (+ MyCV site for gaps).
- 2026-09-21: New file in own folder `MyCV/Resume/`.
- 2026-09-21: Sections = Summary, Experience, Education, Skills.
- 2026-09-21: Phone + email shown; referees "on request".
- 2026-09-21: Style = user will upload inspiration; not chosen yet.
