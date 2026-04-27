# To do — install and deploy guide

## What's new in v1.1.0

- **Priorities** — High, Medium, Low, or none. Active list auto-sorts by priority. Triangle icon next to task title shows priority colour.
- **Work / Personal context** — Every task is either Work (sky blue) or Personal (violet). Filter pills at the top let you focus on one or the other. The quick-add field remembers what context you're adding to.
- **Auto-updates** — When the app is hosted online, it picks up new versions automatically next time you open it.

---

## Deploy to GitHub Pages (recommended)

This is the proper way. Once set up, every future update is one click.

### One-time setup (about 10 minutes)

**Step 1: Create a GitHub account**

If you don't have one already, sign up at https://github.com. Free.

**Step 2: Create a new repository**

1. Click the `+` icon top right > **New repository**
2. Name it whatever you like (e.g. `todo-app`)
3. Set it to **Public** (private repos need a paid plan to use Pages)
4. Don't tick any of the "Initialize with..." boxes
5. Click **Create repository**

**Step 3: Upload the files**

On the new empty repo page, click **uploading an existing file** (the link in the middle of the page).

1. Drag all four files from this zip into the upload area: `index.html`, `sw.js`, `manifest.webmanifest`, `icon.svg`
2. Scroll down, click **Commit changes**

**Step 4: Turn on GitHub Pages**

1. In the repo, click **Settings** (top nav)
2. Click **Pages** in the left sidebar
3. Under "Source", select **Deploy from a branch**
4. Branch: `main`, folder: `/ (root)`. Click **Save**
5. Wait about a minute. Refresh the Pages settings page. You'll see "Your site is live at `https://yourname.github.io/todo-app/`"

**Step 5: Install the app from that URL**

1. Open the URL in Edge or Chrome
2. Click the install icon in the address bar
3. Done. The app now updates automatically.

### How updates work

When I send you a new version:

1. Go to your GitHub repo in the browser
2. Click each updated file, click the pencil icon to edit, paste new contents, commit
3. (Or drag-drop replace via **Add file** > **Upload files**)
4. Wait about a minute for GitHub Pages to rebuild
5. Open your installed app. It detects the new version, applies it, and reloads. Zero effort on your end.

The version number at the bottom of the app will update so you know it worked.

---

## Alternative: Netlify drag-and-drop

Even less setup if GitHub feels heavy.

1. Go to https://app.netlify.com/drop
2. Sign up (free)
3. Drag the `todo-pwa` folder onto the page
4. Netlify gives you a URL. Install from it.
5. To update: drag the new folder onto the same site

---

## Local-only fallback

If you don't want to host it online:

1. Unzip somewhere permanent
2. Double-click `index.html`, install via Edge/Chrome address bar
3. Updates require manually replacing the files in the folder when I send a new version

You won't get auto-updates this way.

---

## Your data

Tasks live in the browser's local storage for the URL the app was installed from. **This means:**

- If you install from `localhost` or `file://`, your data lives there
- If you later install from your GitHub Pages URL, that's a fresh start

So decide upfront: install from your hosted URL from day one if you want to keep your data forever.

Tasks do NOT sync across devices. If that becomes important later, we can talk about adding a sync backend.

---

## Keyboard shortcuts

- `⌘K` / `Ctrl+K` — focus the Add Task field
- `Enter` — add the task
- Click a task to expand details
