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
- localStorage keys: Access uses `cbc-access-v1`, Offboarding uses `cbc-offboarding-v1`. Both apps are on catherine-jason.github.io and share browser storage, so these must never match.
- Access says "your organization" where Offboarding says "nonprofit"
- Features only in Access: the Onboarding tab, the Inventory tab, backup and restore, and the links between them (for example "Load their devices from inventory" and check in updating the inventory). Access may add hooks around shared code for these, as long as the shared behavior stays the same.

## Working rules

- Test every change, show the diff (and any README change) before committing, and wait for "commit".
- README text is plain words with no dashes.
