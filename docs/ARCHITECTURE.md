# Aster Architecture

Aster is intentionally built without a framework or build system. The extension uses browser-native HTML, CSS, JavaScript modules, and Chrome Extension APIs.

## High-level structure

```text
Chrome New Tab
      |
      v
  index.html
      |
      v
   app.js
      |
      +-------------------------------+
      |       |        |       |       |
      v       v        v       v       v
    Clock   Search   Tasks   Notes   Timer
      |       |        |       |       |
      +-------+--------+-------+-------+
                      |
                      v
                 Chrome Storage
```

## Presentation layer

The interface is defined in `aster/index.html` and styled through small CSS files:

- `variables.css` defines theme tokens and reusable values.
- `layout.css` controls page structure and responsive layout.
- `components.css` contains reusable component styling.
- `refine.css` and `search-polish.css` contain targeted visual refinements.

## Application layer

`app.js` initializes the dashboard and coordinates the feature modules.

Feature modules are intentionally separated by responsibility:

| Module | Responsibility |
| --- | --- |
| `clock.js` | Clock, date, greeting, and daily context |
| `search.js` | Search routing, command prefixes, suggestions, and history |
| `shortcuts.js` | Quick-access shortcut management |
| `tasks.js` | Daily task management |
| `today.js` | Time-based daily planning |
| `notes.js` | Persistent scratchpad behaviour |
| `timer.js` | Focus sessions, presets, pause, reset, and session state |
| `settings.js` | Personalisation, themes, durations, and import/export |
| `storage.js` | Shared Chrome Storage access |
| `background.js` | Service-worker timer completion handling |

## State and persistence

Aster stores application data locally through the Chrome Storage API.

```text
User interaction
      |
      v
Feature module
      |
      v
Storage helper
      |
      v
chrome.storage.local
```

The stored state includes settings, shortcuts, tasks, notes, daily planning items, timer state, onboarding state, and search history.

## Background behaviour

The extension uses a Manifest V3 service worker.

Chrome Alarms keeps focus-timer completion logic independent from the visible new-tab page. This allows timer state to be reconciled even when the original tab is no longer active.

## Extension integration

The extension replaces Chrome's default new-tab page through:

```json
{
  "chrome_url_overrides": {
    "newtab": "index.html"
  }
}
```

The current implementation is deliberately dependency-free. The goal is a small, inspectable extension that can run directly in Chrome without a framework, package installation, or build pipeline.
