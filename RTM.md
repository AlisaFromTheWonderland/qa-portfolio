# RTM Matrix — Roles and Access

## Scope

This matrix is designed for:
- **requirements traceability**
- **role-based access validation**
- **documentation testing**
- **coverage tracking**

---

## Roles

- **Guest**
- **Registered User**
- **Premium User**
- **Administrator / Moderator**

---

## Access Legend

- **✅** — full access
- **❌** — no access
- **🔹** — limited / partial access
- **—** — not applicable

---

## Coverage Legend

- **Covered** — test cases exist
- **Partially Covered** — covered only for selected roles / scenarios
- **Not Covered** — no test cases yet
- **Planned** — planned for future coverage

---

## Status Legend

- **Approved** — requirement is confirmed in documentation
- **In Review** — requirement needs clarification or validation
- **Draft** — preliminary requirement
- **Blocked** — cannot be validated yet

---

## RTM — Role and Access Matrix

| Requirement ID | Functionality / Module | Guest | Registered User | Premium User | Administrator / Moderator | Priority | Test Coverage | Status | Comment |
|---|---|---|---|---|---|---|---|---|---|
| RA-01 | Account registration (email, Google, Apple ID) | ✅ | — | — | — | High | Covered | Approved | Required to unlock full mode |
| RA-02 | Authorization / Login | — | ✅ | ✅ | ✅ | High | Covered | Approved | Access to own account |
| RA-03 | Password recovery | ✅ | ✅ | ✅ | — | High | Partially Covered | In Review | Via email |
| RA-04 | View public community / profiles | 🔹 Limited view | ✅ Full view | ✅ Full view | ✅ Full view + moderation | Medium | Planned | In Review | Guest can only see public information |
| RA-05 | Add a book to library | ❌ | ✅ | ✅ | 🔹 Can review user libraries | High | Covered | Approved | Authorized users only |
| RA-06 | Edit / delete a book | ❌ | ✅ | ✅ | 🔹 May intervene in case of rule violations | High | Partially Covered | In Review | User's own library |
| RA-07 | Start reading session (timer, pages, notes) | ❌ | ✅ | ✅ | — | High | Covered | Approved | Core tracking feature |
| RA-08 | View reading history | ❌ | ✅ | ✅ | 🔹 For moderation | Medium | Planned | In Review | Personal analytics |
| RA-09 | View statistics / analytics (charts, calendar) | ❌ | ✅ Basic | ✅ Extended | 🔹 User analytics access | Medium | Planned | In Review | Premium includes advanced analytics |
| RA-10 | Challenges | 🔹 Overview | ✅ Basic participation | ✅ Premium challenges | 🔹 Creation / moderation | Medium | Planned | Draft | Premium challenges are paid-only |
| RA-11 | Achievements, badges, motivation system | ❌ | ✅ Basic | ✅ Extended + bonuses | 🔹 Manage badge list | Medium | Planned | Draft | Badges are synced with profile |
| RA-12 | Community (profiles, likes, comments) | 🔹 View public content | ✅ Full interaction | ✅ Full interaction + extra features | ✅ Content moderation | High | Partially Covered | In Review | Core social feature |
| RA-13 | Buddy Reading (shared reading) | ❌ | ❌ | ✅ | 🔹 Can manage groups | Medium | Not Covered | Draft | Premium-only feature |
| RA-14 | Book barcode scanning (AI, OCR) | ❌ | ❌ | ✅ | — | Medium | Not Covered | Draft | Premium feature |
| RA-15 | AI book recommendations | ❌ | ❌ | ✅ | 🔹 Output control | Low | Not Covered | Draft | Phase 2 / Premium |
| RA-16 | Data synchronization across devices | 🔹 Limited (local data) | ✅ Auto-sync | ✅ Auto-sync + backup | 🔹 Sync log monitoring | High | Planned | In Review | Cloud-based |
| RA-17 | Offline mode | ✅ Guest mode | ✅ Limited functionality | ✅ | — | Medium | Not Covered | Draft | Data is cached locally |
| RA-18 | Profile / privacy settings | ❌ | ✅ | ✅ | ✅ Can edit or block a user | High | Partially Covered | In Review | GDPR compliance |
| RA-19 | Dark / light theme | ✅ | ✅ | ✅ | ✅ | Low | Not Covered | Approved | Saved in settings |
| RA-20 | Interface languages (UA / EN) | ✅ | ✅ | ✅ | ✅ | Low | Not Covered | Approved | Switched in settings |
| RA-21 | Admin panel / moderation | ❌ | ❌ | ❌ | ✅ | High | Covered | Approved | User, reports, and content management |
| RA-22 | Logout / account deletion | ❌ | ✅ | ✅ | ✅ Forced deletion in case of violations | High | Partially Covered | In Review | GDPR-related functionality |

---

## Notes for QA

### Recommended validation focus
- guest restrictions
- registered vs premium access boundaries
- admin-only functionality
- moderation permissions
- premium-only features
- GDPR-related actions
- UI visibility vs backend permission consistency

### Suggested next step
Create linked test cases for each **Requirement ID** to make the matrix fully traceable.# RTM Matrix — Roles and Access

## Scope

This matrix is designed for:
- **requirements traceability**
- **role-based access validation**
- **documentation testing**
- **coverage tracking**

---

## Roles

- **Guest**
- **Registered User**
- **Premium User**
- **Administrator / Moderator**

---

## Access Legend

- **✅** — full access
- **❌** — no access
- **🔹** — limited / partial access
- **—** — not applicable

---

## Coverage Legend

- **Covered** — test cases exist
- **Partially Covered** — covered only for selected roles / scenarios
- **Not Covered** — no test cases yet
- **Planned** — planned for future coverage

---

## Status Legend

- **Approved** — requirement is confirmed in documentation
- **In Review** — requirement needs clarification or validation
- **Draft** — preliminary requirement
- **Blocked** — cannot be validated yet

---

## RTM — Role and Access Matrix

| Requirement ID | Functionality / Module | Guest | Registered User | Premium User | Administrator / Moderator | Priority | Test Coverage | Status | Comment |
|---|---|---|---|---|---|---|---|---|---|
| RA-01 | Account registration (email, Google, Apple ID) | ✅ | — | — | — | High | Covered | Approved | Required to unlock full mode |
| RA-02 | Authorization / Login | — | ✅ | ✅ | ✅ | High | Covered | Approved | Access to own account |
| RA-03 | Password recovery | ✅ | ✅ | ✅ | — | High | Partially Covered | In Review | Via email |
| RA-04 | View public community / profiles | 🔹 Limited view | ✅ Full view | ✅ Full view | ✅ Full view + moderation | Medium | Planned | In Review | Guest can only see public information |
| RA-05 | Add a book to library | ❌ | ✅ | ✅ | 🔹 Can review user libraries | High | Covered | Approved | Authorized users only |
| RA-06 | Edit / delete a book | ❌ | ✅ | ✅ | 🔹 May intervene in case of rule violations | High | Partially Covered | In Review | User's own library |
| RA-07 | Start reading session (timer, pages, notes) | ❌ | ✅ | ✅ | — | High | Covered | Approved | Core tracking feature |
| RA-08 | View reading history | ❌ | ✅ | ✅ | 🔹 For moderation | Medium | Planned | In Review | Personal analytics |
| RA-09 | View statistics / analytics (charts, calendar) | ❌ | ✅ Basic | ✅ Extended | 🔹 User analytics access | Medium | Planned | In Review | Premium includes advanced analytics |
| RA-10 | Challenges | 🔹 Overview | ✅ Basic participation | ✅ Premium challenges | 🔹 Creation / moderation | Medium | Planned | Draft | Premium challenges are paid-only |
| RA-11 | Achievements, badges, motivation system | ❌ | ✅ Basic | ✅ Extended + bonuses | 🔹 Manage badge list | Medium | Planned | Draft | Badges are synced with profile |
| RA-12 | Community (profiles, likes, comments) | 🔹 View public content | ✅ Full interaction | ✅ Full interaction + extra features | ✅ Content moderation | High | Partially Covered | In Review | Core social feature |
| RA-13 | Buddy Reading (shared reading) | ❌ | ❌ | ✅ | 🔹 Can manage groups | Medium | Not Covered | Draft | Premium-only feature |
| RA-14 | Book barcode scanning (AI, OCR) | ❌ | ❌ | ✅ | — | Medium | Not Covered | Draft | Premium feature |
| RA-15 | AI book recommendations | ❌ | ❌ | ✅ | 🔹 Output control | Low | Not Covered | Draft | Phase 2 / Premium |
| RA-16 | Data synchronization across devices | 🔹 Limited (local data) | ✅ Auto-sync | ✅ Auto-sync + backup | 🔹 Sync log monitoring | High | Planned | In Review | Cloud-based |
| RA-17 | Offline mode | ✅ Guest mode | ✅ Limited functionality | ✅ | — | Medium | Not Covered | Draft | Data is cached locally |
| RA-18 | Profile / privacy settings | ❌ | ✅ | ✅ | ✅ Can edit or block a user | High | Partially Covered | In Review | GDPR compliance |
| RA-19 | Dark / light theme | ✅ | ✅ | ✅ | ✅ | Low | Not Covered | Approved | Saved in settings |
| RA-20 | Interface languages (UA / EN) | ✅ | ✅ | ✅ | ✅ | Low | Not Covered | Approved | Switched in settings |
| RA-21 | Admin panel / moderation | ❌ | ❌ | ❌ | ✅ | High | Covered | Approved | User, reports, and content management |
| RA-22 | Logout / account deletion | ❌ | ✅ | ✅ | ✅ Forced deletion in case of violations | High | Partially Covered | In Review | GDPR-related functionality |

---

## Notes for QA

### Recommended validation focus
- guest restrictions
- registered vs premium access boundaries
- admin-only functionality
- moderation permissions
- premium-only features
- GDPR-related actions
- UI visibility vs backend permission consistency

### Suggested next step
Create linked test cases for each **Requirement ID** to make the matrix fully traceable.
