# BuildMyResume

BuildMyResume is a single-page web app to create professional resumes with a live preview and export options.

## Features

- **Live editing with instant preview:** As you type in the form, the resume preview updates immediately so you can see formatting and content changes in real time.
- **Complete resume sections:** The builder supports personal details, professional summary, education, experience, projects, honors and awards, certifications, technical skills, and language proficiency ratings.
- **Dynamic section management:** You can add or remove entries for education, experience, projects, honors, certifications, and languages based on your profile needs.
- **Smart date input handling:** Date dropdowns support month/year ranges and a `Present` option for current roles or ongoing education.
- **Built-in personalization controls:** A dark mode toggle is available, and your theme preference is saved locally for future visits.
- **Automatic and manual local persistence:** Resume data is auto-saved every 30 seconds in browser local storage, and keyboard shortcuts are available for manual save/export actions.
- **Easy export options:** You can download your resume as a PDF or PNG image directly from the app.
- **Quick-start sample content:** A sample data loader helps you instantly populate the form and understand the expected resume structure.

## Tech Stack

- HTML5
- CSS3
- Vanilla JavaScript
- Service Worker (`sw.js`) for basic caching
- CDN libraries:
  - `html2pdf.js`
  - `html2canvas`
  - Font Awesome

## Project Structure

```text
BuildMyResume/
├── index.html      # Main UI and form structure
├── style.css       # Styling and theme support
├── script.js       # Form logic, preview updates, exports, autosave
├── sw.js           # Service worker cache handling
├── resume.tex      # LaTeX resume template sample
└── favicon.png
```

## Run Locally

Because this project includes a service worker, use a local HTTP server (not `file://`).

### Option 1: Python (recommended)

```bash
cd path/to/BuildMyResume
python3 -m http.server 8000
```

Open: `http://localhost:8000`

### Option 2: VS Code Live Server

Open the folder in VS Code and run **Live Server** on `index.html`.

## How to Use

1. Open the app in your browser.
2. Fill in your details in the editor panel.
3. Use **+ Add Education / Experience / Project / Honor / Certification / Language** to add entries.
4. See updates instantly in the right-side preview.
5. Click:
   - **Export PDF** to download a `.pdf`
   - **Export Image** to download a `.png`
   - **Load Sample** to prefill demo content

### Keyboard Shortcuts

- `Ctrl + S` (or `Cmd + S`): Save current resume data to local storage
- `Ctrl + P` (or `Cmd + P`): Export PDF

## Data Persistence

Resume content is stored in your browser local storage:

- `resumeBuilderData` (manual save)
- `resumeBuilderAutoSave` (automatic save)
- `theme` (dark/light mode)

## Notes

- This is a static frontend project; no backend setup is required.
- Export quality may vary slightly by browser because rendering depends on client-side libraries.
