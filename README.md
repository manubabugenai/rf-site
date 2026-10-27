# rf-site

A small stand-in for the source of [robotframework.org](https://robotframework.org), used by the
AI test-automation demo. It plays the role of the application repo (Bitbucket at the client).

| Path | Site area | Requirement |
|---|---|---|
| `src/pages/index.html` | Home page | REQ-100 |
| `src/components/Header.html`, `src/components/Footer.html` | Shared header and footer (all pages) | REQ-200 |
| `src/styles/global.css` | Styles shared by all pages | REQ-100, REQ-200, REQ-300 |
| `src/pages/foundation/index.html`, `src/components/FoundationMenu.html` | Foundation page | REQ-300 |

## The demo fix

`main` has the bug from the incident: on the Foundation page, the **Join** menu link points to `#join`, but the
section's id is `how-to-join`, so clicking it does nothing.

The pull request **"Fix Join link on the Foundation page"** (branch `fix/foundation-join-link`) is the developer's
fix. It is **never merged**, so it can be linked to a new incident and reused for every demo run. It changes:

- `src/components/FoundationMenu.html`: the Join link now points to `#how-to-join` (the fix).
- `src/styles/global.css`: a scroll offset so the sticky header doesn't cover the section heading. This file is
  shared by every page, and the Change Impact page doesn't mention it; the agent is expected to notice.
