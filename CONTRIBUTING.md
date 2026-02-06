# Contributing to RunTrack

Thanks for your interest in improving RunTrack! Here's how to contribute.

## Workflow

### 1. Fork & Clone
```bash
git fork https://github.com/YOUR_USERNAME/runtrack-dashboard
git clone https://github.com/YOUR_USERNAME/runtrack-dashboard.git
cd runtrack-dashboard
```

### 2. Create a Branch
Name your branch after the issue:
```bash
git checkout -b fix/issue-8-footer-contrast
```

### 3. Screenshot "Before"
Open `index.html` in your browser and take a screenshot of the area you're about to fix. Save it for your PR description.

### 4. Make Your Fix
Edit `index.html` — all styles and scripts are in this single file.

### 5. Screenshot "After"
Take another screenshot showing the improvement.

### 6. Commit & Push
```bash
git add index.html
git commit -m "fix: improve footer text contrast (#8)"
git push origin fix/issue-8-footer-contrast
```

### 7. Open a Pull Request
In your PR description, include:

```markdown
## What
Fixes #8 — Footer text was nearly invisible due to low contrast.

## Before
![before](before-screenshot.png)

## After
![after](after-screenshot.png)

## Changes
- Changed footer text color from `#e5e7eb` to `#6b7280`

## Testing
- Verified in Chrome and Firefox
- Checked WCAG contrast ratio passes AA (4.5:1+)
```

## Commit Message Format

Use conventional commits:
- `fix: description` for bug fixes
- `feat: description` for new features
- `style: description` for visual-only changes

## Tips

- One issue per PR — keep changes small and focused
- Always include before/after screenshots for visual changes
- Test at both desktop (1440px) and mobile (375px) widths
- Check color contrast with [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/)
