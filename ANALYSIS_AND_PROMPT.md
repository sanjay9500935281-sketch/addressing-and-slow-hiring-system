# CareerOS — Deck Analysis & Build Prompt
*Team SkyKnights · HackACE 2026 · Domain: Open Challenge Solutions*

## What your deck says (17 slides, summarized)

| Slide(s) | Content |
|---|---|
| 1–3 | Team & event cover: SkyKnights, SPOC Sanjay B, hackathon registration details |
| 4 | Problem statement title: *Addressing Slow Hiring, Resume Fraud & Overlooked Talent* |
| 5–6 | Abstract: recruitment is broken by fake resumes, unverified experience, scattered records, and keyword-ATS rejections. **CareerOS** = an AI-powered digital career identity platform giving every person a lifelong, verified **Career ID**. |
| 7 | Problem statement in detail — 5 key challenges (fake resumes, ATS rejecting good candidates, slow manual verification, scattered certificates, no trusted lifelong identity) |
| 8 | Objectives & aim — verified Career ID, reduced fraud, AI-smart matching, a transparent hiring ecosystem |
| 9 | Solution overview — unique Career ID, verified education/experience/certs, AI profile analysis, lifetime portfolio |
| 10 | Workflow: Student/Employee → Upload → College/Company Verification → CareerOS Database → AI Analysis Engine → Recruiters & Job Portals |
| 11 | AI Innovation — 6 modules: Resume Intelligence, Candidate Matching, Fraud Detection, Skill Gap Analysis, Career Recommendation Engine, Hiring Insights Dashboard |
| 12 | Benefits by stakeholder — Students, Recruiters, Colleges |
| 13 | Tech stack — React, Spring Boot/Node.js, MongoDB, Python, LLMs, OCR, AWS/Azure, REST APIs |
| 14 | Future scope — blockchain verification, government integration, global Career ID, AI interview prep |
| 15–17 | Your own architecture diagrams (workflow visuals) |

**This is a strong, complete hackathon deck** — the idea directly answers all three parts of the problem statement, the architecture diagrams are detailed and consistent across slides, and the tech stack is realistic for a working prototype.

One small inconsistency to clean up before you present: slide 8 has a stray placeholder line ("uygdwuygduyd") — worth deleting from the actual pptx before submission.

---

## The Build Prompt

Use this to brief an AI tool (or your own dev team) to turn the CareerOS concept into working code:

```
Build "CareerOS" — an AI-powered digital career identity platform with three
connected modules:

1. CAREER ID (Student/Professional side)
   - Registration issues a unique, permanent Career ID
   - Structured upload for: academic records, certifications, work experience,
     skills, projects/GitHub, resume
   - A verification queue that checks each item against its issuing source
     (college, company, certificate provider) before it's marked verified —
     never auto-verify on upload alone

2. AI ENGINE (six modules, each independently testable)
   - Resume Intelligence: builds a structured profile from verified data only
   - Candidate Matching: ranks candidates per role using verified skill
     evidence, not resume keywords
   - Fraud Detection: flags employment date overlaps, unproven skill claims,
     and resume-template similarity — with a reasoned score, not a silent
     rejection
   - Skill Gap Analysis: compares a candidate's verified skill levels against
     a role's required levels and suggests what closes the gap
   - Career Recommendation Engine: suggests roles, courses, and next steps
   - Hiring Insights Dashboard: gives recruiters auditable, explainable
     reasoning behind every score

3. DASHBOARDS
   - Recruiter: search verified candidates per role, see AI match % and
     fraud risk, drill into the reasoning behind any score
   - Student: see Career ID, verification status, and skill-gap results
   - University/Government (future scope): aggregate placement and
     verification analytics

CONSTRAINTS:
- Verification must be source-of-truth-checked (college/company/certificate
  body), not self-declared
- Every AI score (match %, fraud risk, skill gap) must ship with a
  human-readable reason, not just a number
- Recruiters make the final call — the system assists, it doesn't auto-reject

TECH STACK: React (frontend), Node.js/Spring Boot (backend), MongoDB
(database), Python + LLMs for the AI engine, OCR for document parsing,
AWS/Azure for hosting, REST APIs for integration with existing ATS/HR tools.

DELIVERABLE: a working demo of the flow Register → Upload → Verify →
AI Engine → Dashboard, with the three headline metrics (time-to-shortlist,
fraud caught, verified-profile rate) visible on the recruiter dashboard.
```

---

## What's in this zip

- **`index.html`** — an interactive, working demo of CareerOS. Open it in any browser:
  - **Sign-in screen** — a Google-style sign-in (demo only — no real account is contacted). Pick the sample account or "Use another account" to enter any name/email; it carries into the Career ID form.
  - **Overview** — the pitch, key metrics, and workflow at a glance
  - **My Career ID** — walk through registration → Career ID issuance → **Add records to verify** (now correctly opens the upload step) → document upload with live per-document verification → skill-gap analysis against your chosen target role
  - **Recruiter Dashboard** — a searchable table of verified candidates per role, ranked by AI match %, with fraud-risk tags and full explainable-AI reasoning on click
  - **AI Engine** — all 6 modules from your deck, each with a sample run (the Fraud Detection sample mirrors your slide 11 example: an employment-date overlap plus unproven skill claims)
- **`ANALYSIS_AND_PROMPT.md`** — this document.

### Registration now covers all streams, not just tech
The **Degree / stream** field offers Engineering (CSE, ECE, Mechanical, Civil), Science (CS, Physics, Chemistry, Mathematics, Biology), Arts (English, History, Economics, Psychology), and Commerce/Management (B.Com, BBA) — 15 degrees in total. Each degree unlocks its own two relevant target roles (e.g. Mechanical → Mechanical Design Engineer / Manufacturing Engineer; B.A. English → Content Writer / Editor), and the skill-gap screen has its own tailored skill set and required levels for all 30 roles.

### Courses, now upload-and-verify like records
Step 3 ("Upload & verify") is split into two tabs: **Records** (degree, certs, experience — as before) and **Courses**. Add a course with its provider, claimed start month, and completion month; each course goes through the same "send for verification" flow as a document, checked against the named provider before it counts.

### Skill gap now shows real completion timelines
Every skill row in the skill-gap screen shows either:
- a linked course already on file, with its actual claimed month range and live verification status, or
- a suggested completion window computed from today's date (e.g. "Sep 2026 – Dec 2026"), sized to how large the gap is.

### Recruiter dashboard now logs who opens a Career ID, and how
Below the candidate table, an **Access activity** panel shows recent opens by name, company, and method (role search, keyword search, direct Career ID lookup) with a timestamp. When you open a candidate's profile yourself, a new "You — opened … just now" entry appears at the top of the log immediately, so access is auditable in real time — matching the "explainable, auditable" principle from your own AI Engine slide.
