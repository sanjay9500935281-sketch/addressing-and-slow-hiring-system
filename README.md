# Career Sync 

## What's in this folder
- `index.html` — the working interactive demo. No install needed.
- `ANALYSIS_AND_PROMPT.md` — deck analysis + the build prompt used to generate this demo.
- `README.md` — this file.

## How to run it
1. Extract the zip.
2. Double-click `index.html` (or right-click → Open With → any browser: Chrome, Edge, Firefox).
3. No server, no internet, no install required — everything runs client-side in the browser.

## How to use the demo
1. **Sign in** — click "Continue with Google" (demo only, no real account is contacted). Pick the sample account, or "Use another account" to type any name/email — it carries into your Career ID.
2. **My Career ID → Register** — fill degree/stream, click **Issue Career ID** to get your unique ID.
3. **Upload & verify**
   - **Records tab** — add education, certifications, work experience.
   - **Courses tab** — add a course with provider + claimed start/completion month.
   - Click **Send for verification** — each item is checked against its issuing source (college/company/provider) before it's marked **Verified**. Nothing is auto-verified on upload.
4. **Skill Gap** — pick a target role; see verified skill levels vs. required levels, with linked courses or a suggested completion window.
5. **Recruiter Dashboard** — search verified candidates by role, see AI match %, fraud-risk tags, and click into any candidate for full explainable-AI reasoning. The **Access activity** log shows who opened a profile and how.
6. **AI Engine tab** — sample runs of all 6 modules from the deck (Resume Intelligence, Candidate Matching, Fraud Detection, Skill Gap Analysis, Career Recommendation, Hiring Insights).

## Notes
- This is a front-end prototype: all data is generated/simulated in-browser (no backend, no real verification calls).
- See `ANALYSIS_AND_PROMPT.md` for the full deck breakdown and the prompt to brief a dev team on building the real backend (React + Node/Spring Boot + MongoDB + Python/LLM AI engine).
