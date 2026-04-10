# Randers Øjenklinik — Claude Instructions

## Project

Static single-page website for Randers Øjenklinik. No build steps, no dependencies, no tests.

- Entry point: `index.html`
- Styles: `css/style.css`
- Images: `img/` and `img/team/`
- Hosted on GitHub Pages: https://eoolsen.github.io/randersoejenklinik/

## Work Cycle

Follow these steps for every change, in order:

### 1. Plan
Think through the change before touching any files. For non-trivial changes, briefly state the approach to the user before proceeding.

### 2. Branch
Create a feature branch from `main`:
```
git checkout -b <short-descriptive-name>
```

### 3. Code change
Make the change. Keep it focused — don't refactor or improve things outside the scope of the task.

### 4. PR
Commit and open a pull request against `main`:
```
git add <files>
git commit -m "<message>"
git push -u origin <branch>
gh pr create --title "..." --body "..."
```

### 5. Push (merge)
Merge the PR into `main`:
```
gh pr merge --squash --delete-branch
```

### 6. Launch
Open the site in Chrome to verify:
```
open -a "Google Chrome" /Users/eoolsen/source/randersoejenklinik/index.html
```

## Notes

- Always run the full cycle for any visible change — no direct commits to `main`
- After merging, GitHub Pages rebuilds automatically (allow ~1 min for live URL to update)
- The live URL is https://eoolsen.github.io/randersoejenklinik/
