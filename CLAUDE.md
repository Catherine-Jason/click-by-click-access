# Click by Click Access

Single file app (`index.html`). It grew out of Click by Click Offboarding, which lives in `C:\Users\User\click-by-click-offboarding`.

## Mirroring rule

These stay the same in both repos:

- Offboarding steps (titles, "why" text, when each step applies, urgent flags)
- "Why this matters" text
- Framework tags and their links
- Device fields (types, OS, encryption, More details fields)
- CSV import and export (column matching, template, export columns)
- Learn mode, glossary and sources
- Records for HR and audits (Access v2.8, Offboarding v1.8): the optional Organization name near the top of the intake (null means it follows the last name typed), the record number (OFF or ON, the date and a 4 character code, kept with the person), Prepared for and the record number at the top of the record, the sign off lines, page numbers, credit and disclaimer when printing, and the same lines at the end of the text file and copied record. Each app uses its own name and address in the credit.
- Security (Access v2.9, Offboarding v1.9): the Content Security Policy meta tag, fonts served from the `fonts` folder (no other website is contacted), no inline style attributes (use a class), Clear this computer (Access: More options in Your data on the Inventory tab; Offboarding: next to Start new) with the in page pop-up, the official address in the footer and README, and SECURITY.md.

Any change to those goes into both repos in the same session, as a separate commit in each repo.

Expected differences, which do not need mirroring:

- Titles, taglines, footers and version numbers
- localStorage keys: Access uses `cbc-access-v1`, Offboarding uses `cbc-offboarding-v1`. Access is live at https://access.catherinejason.com and Offboarding at https://catherine-jason.github.io/click-by-click-offboarding/, so they no longer share browser storage. Keep the keys different anyway, in case they ever end up on the same address again. These must never match.
- Access says "your organization" where Offboarding says "nonprofit"
- Features only in Access: the Onboarding tab, the Inventory tab, backup and restore, and the links between them (for example "Load their devices from inventory", the name picker, check in and hand out updating the inventory). Access may add hooks around shared code for these, as long as the shared behavior stays the same.
- Person files are Access only (v2.6, the "v2.6 (Access only): Person files" block). Each person gets one .xlsx saved at the Record step, with readable tabs and a hidden Data tab the app reopens from. Do not add them to Offboarding.
- Also Access only since v2.6: Load example opens a separate example view that never saves, the in-page pop-up before anything is erased or replaced, and the browser's leave warning for work not yet saved to a file.
- Also Access only since v2.7: the short description next to each tab name (v2.7.1, which replaced the v2.7 start screen and Home link; the app opens on the last tab if it has work, else a tab with work, else Onboarding), the done summary, main buttons and More options at the top of each Record step, the print layout (Offboarding has used the same light print colors since v1.8), and the onboarding 30 day check box with its calendar (.ics) file.
- Access only parts of the v2.8 record features: the Organization name on the Onboarding intake and the Inventory tab, the record number and name on the onboarding record, and the Read me tab of person files and of the inventory .xlsx downloads (the Read me is the last tab, because Import from Excel reads the first).
- Onboarding adds its own steps, "Why this matters" text, the PR.AT-01 and CIS Control 14 tags, glossary terms and sources in the "v2.2 (Access only): Onboarding" block. Those are not mirrored. Edit them there, not in the shared lists.

## Working rules

- After every change to the `<script>` or `<style>` in index.html, run `python tools/update-csp.py`. The Content Security Policy only lets the page run the exact script and styles it was hashed for, so a stale hash stops the whole app. `python tools/update-csp.py --check` only checks.
- Never add `'unsafe-inline'`, an outside script, stylesheet or font, `style="..."` attributes, inline event handlers (`onclick=`) or `eval`. They are blocked by the policy.
- Test every change, show the diff (and any README change) before committing, and wait for "commit".
- README text is plain words with no dashes.
