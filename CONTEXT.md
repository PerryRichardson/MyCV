# Project Context Log: One-page résumé (MyCV)

## Current State
- Last Updated: 2026-09-21
- Active Focus: Workflow step 1 done except 4 blockers. Next: write resume_plan.md (step 2), then STOP for approval.
- Key Constraints:
  - 1 page, A4, self-contained resume.html (inline CSS/JS, offline, no frameworks)
  - Master resume.json, entries tagged ds/policy; filter buttons dim on screen, print outputs selected view
  - Sections: Summary, Experience, Education, Skills; referees "available on request"; phone + email shown
  - include:false in JSON: Strengths, Certifications, Achievements, Publications, Affiliations, Community
  - Transcribe 1:1, never invent; flag gaps
  - Do NOT choose style until user uploads inspiration
  - No HTML until plan approved; leave existing index.html untouched
  - Files: resume_plan.md, resume.json, resume.html, CONTEXT.md (project root)
- Open Threads:
  - Style inspiration upload (required, not yet received)
  - GitHub URL (user chose "add GitHub", gave none)
  - Bootcamp date: "in progress", new expected date unknown
  - Delete stale untracked Resume/ folder? (asked, no answer)

## Sessions (newest first)

### [2026-09-21] Session 1: Sources read, questions asked
- Completed: Read docx (copied to scratchpad, unzipped, stripped document.xml) and index.html. Ran one question round. Created this CONTEXT.md at project root.
- Decisions:
  - Teaching & Mentoring: 1 merged bullet
  - Headline retargeted: "Data Scientist | Computer Vision & Ecology"
  - Keep "Available for remote work"
  - Add LinkedIn and GitHub links
  - Bootcamp: still in progress
- Context Notes:
  - Docx: PhD Zoology Stellenbosch 2023-present exp. 2027; YOLO + U-Net, 0.97 precision, 0.98 recall, ~9:1 imbalance, ~3,000 specimens; MSc Entomology Rhodes distinction 2021-2022; teaching 2019-2025; bootcamp "expected 2026"; contact perryrich@sun.ac.za, (+27) 71 333 6414
  - LinkedIn from index.html: linkedin.com/in/perryn-richardson
  - Source gap: docx says "six years" tutoring; index.html shows tutoring 2019-2022 + demonstrating 2023-2025. Transcribe docx wording, flag.
  - index.html shows bootcamp Mar 2025 to Jun 2026 (conflicts with "in progress")
  - Stale untracked Resume/resume_plan.md exists from earlier session (files in Resume/, assumes Letter). Not used.
- Dead Ends: None. User said "make context folder"; interpreted as CONTEXT.md file at root (unconfirmed).
- Open Threads: See Current State.
- Next Steps:
  1. Get style upload, GitHub URL, bootcamp date, Resume/ deletion OK
  2. Write resume_plan.md ("draft for review"): Concept, File structure, ASCII wireframe, Section detail, JSON schema, Visual style spec, Open questions, dated Decisions log. Stop for approval.
  3. After approval: resume.json with inferred tags, show for review
  4. Build resume.html; test filter, print (1 page A4), narrow width in built-in browser
  5. Final CONTEXT.md update
