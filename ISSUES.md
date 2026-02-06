# Open Issues

Each issue below maps to an intentional UX/UI flaw in the dashboard. Fix them one at a time, each as its own branch and PR.

---

### Issue #1 — Nav links are invisible
**Labels:** `good first issue` `UX/UI` `accessibility`

The navigation links (Dashboard, Runs, Goals, Settings) use a muted gray (`#6b7280`) against the dark nav bar (`#1a1a2e`). They don't look interactive — no hover state, no visual indication they're clickable. Users will miss them entirely.

**Expected:** Links should be clearly visible (white or light color), with a hover state that signals interactivity (underline, color shift, or both).

---

### Issue #2 — "Log New Run" button has terrible contrast
**Labels:** `good first issue` `UX/UI` `accessibility`

The primary CTA button uses light gray text (`#d4d4d4`) on a light gray background (`#e5e5e5`). It's nearly invisible and fails WCAG contrast requirements at every level.

**Expected:** A primary action button should use a bold, high-contrast color scheme (e.g., blue background with white text). It should also have a hover state.

---

### Issue #3 — Stats cards don't respond to screen size
**Labels:** `UX/UI` `responsive`

The stat cards use a fixed `width: 280px` which causes horizontal overflow on smaller screens. There's no wrapping or stacking behavior.

**Expected:** Cards should use a responsive layout (flex-wrap, CSS grid, or percentage widths) that gracefully stacks on smaller viewports.

---

### Issue #4 — Positive and negative stat changes look the same
**Labels:** `good first issue` `UX/UI`

Both the "up" and "down" change indicators use the same gray color (`#6b7280`). Users can't quickly scan to see what improved vs. what declined.

**Expected:** Positive changes should use green, negative changes should use red/orange. The arrow icons already indicate direction — color should reinforce it.

---

### Issue #5 — Table rows have no hover state
**Labels:** `good first issue` `UX/UI`

The Recent Runs table has no row hover effect, making it hard to visually track across columns in wide rows with lots of data.

**Expected:** Rows should highlight with a subtle background color on hover (e.g., `#f9fafb`). Cursor should indicate the row is interactive.

---

### Issue #6 — Edit/Delete action links are invisible
**Labels:** `UX/UI` `accessibility`

The Edit and Delete links in the Actions column use the same color and size as body text. Users won't recognize them as interactive elements.

**Expected:** Action links should be styled distinctly — use the primary brand color for Edit, a red/danger color for Delete, and increase the font size slightly. Add hover underlines.

---

### Issue #7 — "Update Goal" button looks disabled
**Labels:** `UX/UI`

The Update Goal button uses gray background (`#f3f4f6`) with muted text (`#9ca3af`), making it appear disabled/inactive even though it's clickable.

**Expected:** If the button is active, it should look active — use a visible border or brand color. If it should be disabled until a condition is met, add a `disabled` attribute and cursor.

---

### Issue #8 — Footer text is invisible
**Labels:** `good first issue` `UX/UI` `accessibility`

Footer text uses `#e5e7eb` on the `#f0f2f5` page background — nearly zero contrast.

**Expected:** Footer text should use a readable color like `#6b7280` or darker.

---

### Issue #9 — Save and Cancel modal buttons look identical
**Labels:** `UX/UI`

Both buttons in the "Log a Run" modal have the same white background, gray text, and border. There's no way to distinguish the primary action (Save) from the secondary action (Cancel).

**Expected:** Save should use a filled primary color (blue). Cancel should remain understated (outline or ghost style). This creates clear visual hierarchy.

---

### Issue #10 — Delete confirmation has no action buttons
**Labels:** `UX/UI` `functionality`

Clicking "Delete" on a run shows a yellow warning banner, but there are no Confirm or Cancel buttons. The user is stuck — they can't actually confirm or dismiss the deletion.

**Expected:** Add "Confirm Delete" (red/danger) and "Cancel" buttons to the confirmation banner. Clicking Cancel should hide the banner.

---

## Suggested Fix Order

Start with the easiest wins to build confidence:

1. **#8** — Footer contrast (1-line CSS fix)
2. **#1** — Nav link visibility (CSS only)
3. **#4** — Stat change colors (CSS only)
4. **#5** — Table row hover (CSS only)
5. **#2** — Button contrast + hover (CSS only)
6. **#6** — Action link styling (CSS only)
7. **#7** — Update Goal button (CSS)
8. **#9** — Modal button hierarchy (CSS)
9. **#3** — Responsive stat cards (CSS layout)
10. **#10** — Delete confirmation buttons (HTML + JS)

Issues #1–#9 are pure CSS. Issue #10 requires adding HTML elements and JavaScript event handlers.
