# Aster

Aster is a personalized Chrome new-tab dashboard designed to turn the browser's default start page into a focused workspace for everyday tasks, notes, shortcuts, scheduling, and focused work.

Instead of replacing the new tab with another collection of distractions, Aster keeps the interface intentionally compact and puts the things you need most often in one place.

## Features

- **Personalized new-tab dashboard** — Aster replaces Chrome's default new-tab page with a custom dashboard.
- **Quick access shortcuts** — Add, edit, and organize shortcuts to frequently used websites.
- **Web search** — Search directly from the dashboard with support for Google, Bing, DuckDuckGo, and Brave.
- **Search commands** — Use shortcuts such as `g`, `yt`, and `gh` to route searches directly to Google, YouTube, or GitHub.
- **Task management** — Create tasks, mark them complete, and keep completed items available for reference.
- **Today planner** — Add time-based entries to keep track of what is happening throughout the day.
- **Notes** — Keep a lightweight note directly on the new-tab page.
- **Focus timer** — Use configurable Focus, Short Break, and Long Break sessions with preset or custom durations.
- **Themes** — Switch between Midnight and Light appearances and customize the dashboard accent.
- **Persistent data** — Shortcuts, tasks, notes, Today entries, and settings are stored locally using Chrome storage.
- **Import and export** — Export Aster data as JSON and import it when moving or restoring a setup.
- **Onboarding** — A first-run setup helps configure the user's name and preferred appearance.
- **Offline-first interface** — The dashboard itself does not require a backend or account to manage personal data.

## Screenshots

Add screenshots of the dashboard here once the final UI is ready. Keeping the repository's README focused on the actual interface makes the project easier to evaluate without turning the page into a marketing brochure.

## Tech Stack

- HTML5
- CSS3
- JavaScript (ES Modules)
- Chrome Extensions Manifest V3
- Chrome Storage API
- Chrome Alarms API

The extension uses a service worker for background functionality and a custom `chrome_url_overrides.newtab` page for the dashboard. fileciteturn4file0

## Project Structure

```text
.
├── LICENSE
└── aster/
    ├── assets/
    │   └── icons/
    ├── css/
    │   ├── components.css
    │   ├── layout.css
    │   ├── refine.css
    │   ├── search-polish.css
    │   └── variables.css
    ├── js/
    │   ├── app.js
    │   ├── background.js
    │   ├── clock.js
    │   ├── notes.js
    │   ├── search.js
    │   ├── settings.js
    │   ├── shortcuts.js
    │   ├── storage.js
    │   ├── tasks.js
    │   ├── timer.js
    │   └── today.js
    ├── index.html
    └── manifest.json
```

The current project is a lightweight static extension with separate modules for tasks, notes, search, settings, shortcuts, storage, the focus timer, and Today entries. fileciteturn3file0

## Installation

Aster can currently be installed locally as an unpacked Chrome extension. No build system or package manager is required.

### 1. Clone the repository

```bash
git clone https://github.com/Jofil-Joby/Aster-A-Personalized-Chrome-New-Tab-Dashboard-and-Productivity-Extension.git
cd Aster-A-Personalized-Chrome-New-Tab-Dashboard-and-Productivity-Extension
```

### 2. Open Chrome Extensions

Navigate to:

```text
chrome://extensions
```

Enable **Developer mode** in the top-right corner.

### 3. Load Aster

Select **Load unpacked** and choose the `aster` directory from the cloned repository.

### 4. Open a new tab

Open a new Chrome tab. Aster should now appear as the new-tab page.

## Permissions

Aster requests the following Chrome permissions:

| Permission | Purpose |
|---|---|
| `storage` | Store dashboard data such as tasks, notes, shortcuts, and settings locally. |
| `alarms` | Support timer-related background behavior. |

The extension also uses Chrome's `newtab` override to replace the default new-tab page. These permissions are defined in the extension manifest. fileciteturn4file0

## Data & Privacy

Aster is designed around local browser storage rather than a user account or application backend.

Personal dashboard data such as tasks, notes, shortcuts, and preferences is stored through Chrome's storage API. The extension does not require a sign-in flow to use its core functionality.

Search functionality may communicate with the selected search provider, and search suggestions use Google's suggestion endpoint as configured by the extension's content security policy. fileciteturn4file0

## Customization

Aster provides settings for:

- User name
- Search engine
- Theme
- Accent color
- Focus duration
- Short-break duration
- Long-break duration

The dashboard also provides JSON import/export so the user's Aster data can be backed up or transferred manually.

## Development

There is currently no dependency installation or build step. The extension is implemented with browser-native HTML, CSS, and JavaScript modules.

For development:

1. Make changes inside the `aster` directory.
2. Open `chrome://extensions`.
3. Reload the Aster extension after making changes.
4. Open a new tab to verify the result.

When changing the extension manifest, make sure the referenced files and permissions remain consistent with the actual project structure.

## Roadmap

Potential future improvements include:

- Chrome Web Store release
- Drag-and-drop shortcut organization
- More dashboard customization options
- Additional productivity integrations
- Improved accessibility and keyboard navigation
- More flexible timer workflows
- Optional synchronization across devices

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

## Author

**Jofil Joby**

GitHub: [@Jofil-Joby](https://github.com/Jofil-Joby)
