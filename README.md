<div align="center">

# Aster

### A focused Chrome new-tab dashboard for a calmer start to every session.

Aster replaces Chrome's default new tab with a lightweight personal workspace for search, planning, tasks, notes, shortcuts, and focused work.

[![Manifest V3](https://img.shields.io/badge/Chrome-Manifest%20V3-4285F4?style=flat-square&logo=googlechrome&logoColor=white)](https://developer.chrome.com/docs/extensions/develop/migrate/what-is-mv3)
[![JavaScript](https://img.shields.io/badge/JavaScript-ES%20Modules-F7DF1E?style=flat-square&logo=javascript&logoColor=black)](https://developer.mozilla.org/docs/Web/JavaScript/Guide/Modules)
[![License](https://img.shields.io/badge/License-MIT-2E7D32?style=flat-square)](LICENSE)
[![Validate Extension](https://github.com/Jofil-Joby/Aster/actions/workflows/validate-extension.yml/badge.svg)](https://github.com/Jofil-Joby/Aster/actions/workflows/validate-extension.yml)

<br>

**Less interface. More focus.**

</div>

---

## Overview

Most new-tab pages are either empty, noisy, or trying to become an operating system. Aster takes a narrower approach.

It provides the things that are useful at the start of a browsing session without requiring an account, backend, subscription, or build process.

- Search from a focused command bar
- Keep frequently used links close
- Manage lightweight daily tasks
- Plan time-based entries for today
- Keep a persistent scratchpad
- Run a built-in focus timer
- Personalize the theme and accent
- Keep data locally in Chrome
- Import and export Aster data

## Preview

### Dashboard

<p align="center">
  <img src="screenshots/dashboard-dark.png" alt="Aster dashboard in Midnight theme" width="100%">
</p>

### Search

<p align="center">
  <img src="screenshots/search-dark.png" alt="Aster search suggestions and command input" width="100%">
</p>

### Settings and Light Theme

<p align="center">
  <img src="screenshots/settings-light.png" alt="Aster settings drawer in Light theme" width="100%">
</p>

### Focus Timer

<p align="center">
  <img src="screenshots/focus-timer.png" alt="Aster expanded focus timer" width="760">
</p>

---

## Features

| Area | What it provides |
| --- | --- |
| **Search** | Web search, direct URLs, recent searches, live suggestions, and command prefixes |
| **Quick Access** | Editable shortcuts for frequently used websites |
| **Tasks** | Lightweight daily task management |
| **Today** | Time-based entries for a simple daily plan |
| **Notes** | A persistent scratchpad for temporary information |
| **Focus** | Focus, short-break, and long-break modes with presets and custom durations |
| **Themes** | Midnight and Light themes with accent customization |
| **Storage** | Local persistence through Chrome Storage |
| **Data Control** | JSON import, export, and reset |
| **Onboarding** | First-run personalization for name and appearance |

### Search commands

Use prefixes to route searches directly:

```text
hello world        → selected search engine
g hello world      → Google
yt javascript      → YouTube
gh chrome api      → GitHub
```

Aster also recognizes direct URLs, so typing a website address opens it without forcing it through a search engine.

Supported default search engines:

- Google
- Bing
- DuckDuckGo
- Brave Search

### Focus timer

The built-in timer supports:

- Focus sessions
- Short breaks
- Long breaks
- Preset durations
- Custom durations
- Pause and resume
- Reset controls
- Background alarm handling through Chrome Alarms

---

## How Aster Works

```text
New Tab
   │
   ▼
Aster Dashboard
   │
   ├── Search
   ├── Shortcuts
   ├── Tasks
   ├── Today
   ├── Notes
   └── Focus Timer
          │
          ▼
    Chrome Storage + Alarms
```

The extension runs entirely in the browser. Core dashboard data is stored locally through Chrome Storage, while Chrome Alarms supports focus-timer completion handling.

For a deeper breakdown, see [Architecture](docs/ARCHITECTURE.md).

---

## Tech Stack

| Technology | Purpose |
| --- | --- |
| HTML5 | Dashboard structure |
| CSS3 | Layout, themes, and components |
| JavaScript | Application logic and UI behaviour |
| ES Modules | Modular client-side architecture |
| Chrome Manifest V3 | Extension platform |
| Chrome Storage API | Local persistence |
| Chrome Alarms API | Timer and background behaviour |

Aster intentionally has **no framework, dependency installation, or build step**.

---

## Installation

Aster currently runs as an unpacked Chrome extension.

### 1. Clone the repository

```bash
git clone https://github.com/Jofil-Joby/Aster.git
cd Aster
```

### 2. Open Chrome Extensions

Navigate to:

```text
chrome://extensions
```

Enable **Developer mode**.

### 3. Load the extension

Click **Load unpacked** and select:

```text
Aster/aster
```

### 4. Open a new tab

Aster should replace Chrome's default new-tab page.

### Updating the extension during development

After changing files:

1. Open `chrome://extensions`
2. Click **Reload** on Aster
3. Open a new tab
4. Test the changed behaviour
5. Check both Midnight and Light themes for UI changes

---

## Privacy

Aster does not require an account or backend for its core functionality.

Dashboard data such as tasks, notes, shortcuts, settings, and planning entries is stored locally through the Chrome Storage API.

Search requests are sent to the search provider selected by the user. Google search suggestions are requested when live suggestions are used.

Aster does not provide cloud synchronization in its current version.

---

## Permissions

Aster requests only the permissions needed for its current functionality.

| Permission | Purpose |
| --- | --- |
| `storage` | Persist dashboard data and settings |
| `alarms` | Support focus-timer background behaviour |

The extension also uses Chrome's new-tab override mechanism to replace the default new-tab page.

---

## Project Structure

```text
Aster/
├── aster/
│   ├── assets/
│   │   └── icons/
│   ├── css/
│   │   ├── variables.css
│   │   ├── layout.css
│   │   ├── components.css
│   │   ├── refine.css
│   │   └── search-polish.css
│   ├── js/
│   │   ├── app.js
│   │   ├── background.js
│   │   ├── clock.js
│   │   ├── notes.js
│   │   ├── search.js
│   │   ├── settings.js
│   │   ├── shortcuts.js
│   │   ├── storage.js
│   │   ├── tasks.js
│   │   ├── timer.js
│   │   └── today.js
│   ├── index.html
│   └── manifest.json
├── docs/
│   └── ARCHITECTURE.md
├── screenshots/
├── CONTRIBUTING.md
├── CHANGELOG.md
├── SECURITY.md
├── LICENSE
└── README.md
```

---

## Validation

The repository includes a GitHub Actions workflow that checks:

- Manifest JSON validity
- JavaScript syntax
- Required extension files

This keeps basic extension integrity checked on pushes and pull requests without adding a heavyweight toolchain.

---

## Roadmap

### Next

- [ ] Chrome Web Store release
- [ ] Drag-and-drop shortcut organization
- [ ] Improved keyboard navigation
- [ ] Expanded accessibility support
- [ ] Automated interaction testing

### Later

- [ ] More dashboard customization
- [ ] Additional productivity integrations
- [ ] Optional cross-device synchronization

The roadmap intentionally prioritizes polish and reliability over adding features merely because empty checkboxes are apparently irresistible.

---

## Contributing

Contributions, bug reports, and UI ideas are welcome.

Please read [CONTRIBUTING.md](CONTRIBUTING.md) before opening a pull request.

For bugs and feature ideas, use the repository issue templates.

---

## Security

Please do not report suspected security vulnerabilities through a public issue.

See [SECURITY.md](SECURITY.md) for reporting guidance.

---

## Changelog

See [CHANGELOG.md](CHANGELOG.md) for notable project changes.

---

## License

Aster is licensed under the [MIT License](LICENSE).

---

<div align="center">

**Aster** · A calmer place to begin.

</div>
