# MubashirBuilds — devlog

Personal devlog built with pure HTML/CSS/JS. Posts are stored as JSON files in `/posts/` and served via GitHub Pages.

## Setup

### 1. Create the repo
Create a **public** GitHub repo (e.g. `mubashirbuilds`).

### 2. Push these files
```
index.html
admin.html
style.css
posts/
  index.json
```

### 3. Enable GitHub Pages
Repo → **Settings** → **Pages** → Source: `main` branch, `/ (root)`.

Your site will be live at: `https://mubashir9.github.io/mubashirbuilds/`

### 4. Update the repo name in index.html
In `index.html`, find this line and set your actual repo name:
```js
const GITHUB_REPO = 'mubashirbuilds'; // ← update this
```

### 5. Generate a GitHub Personal Access Token
Go to [github.com/settings/tokens](https://github.com/settings/tokens) → Generate new token (classic) → tick `repo` scope.

You paste this token into `admin.html` the first time — it saves to your browser's localStorage.

## Writing a post
Navigate to `https://mubashir9.github.io/mubashirbuilds/admin.html` (or `localhost/admin.html` if testing locally).

1. Paste your GitHub token (once — it remembers)
2. Fill in title, category, body (Markdown)
3. Hit **Publish post →**

The post JSON is committed to `/posts/` and `index.json` is updated. GitHub Pages will reflect it within ~30 seconds.

## File structure
```
/
├── index.html          ← public devlog
├── admin.html          ← your private posting page
├── style.css           ← shared styles
└── posts/
    ├── index.json      ← ordered list of post filenames
    ├── my-first-post-1234567890.json
    └── ...
```

Each post file looks like:
```json
{
  "title": "My first post",
  "category": "Misc",
  "date": "2025-01-01T12:00:00.000Z",
  "body": "# Hello\n\nMarkdown content here."
}
```
