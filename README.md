# Office Ergonomics Checklist


An interactive, browser-first Office Ergonomics Checklist used to assess workstation setup and record recommended actions. This single-file app (index.html) was created for use by workplace assessors, safety officers, and department staff to complete, review, export, and print workstation assessment records.


---


## Features
- 28 ergonomics checks grouped by section (Work Surface, Chairs, Monitor, Input Devices, Telephone & Other).
- Save/load drafts as JSON (download and re-upload).
- Review stage showing unanswered questions, concerns, and recommended actions.
- Printable assessment report optimized for A4.
- Fully client-side — no server required; data remains local to the browser.


## Files
- `index.html` — the complete single-page application (HTML + CSS + JavaScript). All app code and the checklist data live here.
- `README.md` — this file.


## Quick start
From a fresh clone:


1. Open the checklist in your browser:
   - Double-click `index.html`, or
   - Right-click and choose "Open with..." in your browser.


2. Or serve it locally (recommended):
   - python 3:
     ```
     python3 -m http.server 8000
     ```
     Then open: `http://localhost:8000/index.html`


No build steps or dependencies required.


## How it works (implementation notes)
- The checklist data is defined in `index.html` in the `items` and `groups` arrays (search for `const items = [`).
- The UI is generated dynamically from those arrays. Each question has metadata (id, group, html text, guidance).
- The app provides draft save/load (JSON), a review panel that summarizes concerns and recommended actions, and a print layout optimized for A4.
- Assessment evaluation is performed in JavaScript (`assessmentResult()` and related helper functions inside `index.html`).


## Customization
To edit the checklist text, ordering, or guidance:
1. Open `index.html` in a text editor.
2. Search for `const items = [` and modify the items (or `groups`).
   - Each item includes keys such as `id`, `group`, `html`, and `guidance`.
3. You can extract CSS and JS into separate files (`styles.css`, `script.js`) if you prefer modular structure.


If you want I can:
- Split `index.html` into `index.html`, `styles.css`, and `script.js`.
- Extract the checklist data into a separate JSON file for easier maintenance.


## Accessibility & privacy
- Designed to be usable in modern browsers; minimal JS ensures basic progressive enhancement.
- The app runs completely client-side: no data is sent externally by default. Drafts are downloaded/uploaded locally by the user.


## Contributing
- Small changes: edit `index.html` and open a pull request.
- Larger changes: consider splitting CSS/JS into separate files and adding tests or an accessibility audit step in CI.


Suggested PR checklist:
- Include a short summary of content changes.
- If changing question text, preserve the `id` to keep draft compatibility.
- Test saving/loading a draft and printing the assessment record.


## License

This repository does not include a license file yet. If this is intended for public reuse, add a license (e.g., MIT, CC-BY, or a government/organizational-compatible license). If you want, I can add a LICENSE file for you — tell me which license to use.

## Credits

Original content and guidance: NUS Office of Risk Management and Compliance (as referenced in index.html).

## Intended use

**For NUS internal use**

This checklist is developed for NUS staff and students to support ergonomic self-assessment and identify improvements. It does not replace a task-specific risk assessment or professional advice.

External users should obtain their institution’s approval and assess its suitability before use. References to NUS procedures, contacts and support arrangements apply only within NUS.
