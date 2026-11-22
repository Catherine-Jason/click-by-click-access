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

Any change to those goes into both repos in the same session, as a separate commit in each repo.

Expected differences, which do not need mirroring:

- Titles, taglines, footers and version numbers
- localStorage keys: Access uses `cbc-access-v1`, Offboarding uses `cbc-offboarding-v1`. Access is live at https://access.catherinejason.com and Offboarding at https://catherine-jason.github.io/click-by-click-offboarding/, so they no longer share browser storage. Keep the keys different anyway, in case they ever end up on the same address again. These must never match.
- Access says "your organization" where Offboarding says "nonprofit"
- Features only in Access: the Onboarding tab, the Inventory tab, backup and restore, and the links between them (for example "Load their devices from inventory", the name picker, check in and hand out updating the inventory). Access may add hooks around shared code for these, as long as the shared behavior stays the same.
- Onboarding adds its own steps, "Why this matters" text, the PR.AT-01 and CIS Control 14 tags, glossary terms and sources in the "v2.2 (Access only): Onboarding" block. Those are not mirrored. Edit them there, not in the shared lists.

## Working rules

- Test every change, show the diff (and any README change) before committing, and wait for "commit".
- README text is plain words with no dashes.
