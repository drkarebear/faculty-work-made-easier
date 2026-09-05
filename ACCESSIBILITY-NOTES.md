# Accessibility Notes — Faculty Work Made Easier Hub
## WCAG 2.2 AA-oriented static-site build

This package contains:
- `index.html`
- `oer-tools/index.html`
- `student-learning-resources/index.html`
- one shared `styles.css`
- the selected path-and-sun favicon set
- no decorative body images

### Public resources intentionally surfaced
- Data Mart Smart
- CCC English OER Picks
- The OER Promptbook
- ENGL C1000 Resources
- ENGL C1002 Resources

Other repositories are not linked or mentioned in this public hub.

## Accessibility design decisions

- Semantic landmarks: header, nav, main, section, article, aside, footer.
- One H1 per page with logical H2/H3 structure.
- Skip-to-main link and programmatically focusable main content.
- Native links only; no scripted custom controls.
- Clear visible focus rings.
- Interactive controls are at least 44px high where practical.
- No link relies on color alone; links use underlines or button/card treatment.
- No body images require alt text; inline SVG icons are decorative and hidden from assistive technology.
- No hover-only content.
- No sticky header, reducing risk of focused content being obscured.
- Responsive reflow to one column without horizontal navigation scrolling.
- No fixed-height text boxes; user text-spacing changes can expand content.
- `prefers-reduced-motion`, `prefers-contrast: more`, forced-colors, dark mode, and print support.
- Dedicated light and dark color tokens rather than simple inversion.
- External project links use descriptive text and an optional decorative external-link icon.
- Intermediary pages use breadcrumbs and plain-language “best for” guidance.
- No placeholder `href="#"` links.
- No links to intentionally unsurfaced projects.

## Final verification recommended after deployment

1. Run WAVE and axe against all three deployed pages.
2. Keyboard test: Tab, Shift+Tab, Enter, skip link, breadcrumbs, and every resource link.
3. Test at 200% zoom and approximately 320 CSS px width.
4. Test dark mode on macOS/iOS and Windows if available.
5. Test Windows High Contrast / forced colors if available.
6. VoiceOver or NVDA: navigate by headings, landmarks, and links.
7. Re-run checks when new course/resource cards are added.

This is a code-level accessibility build, not a legal certification. WCAG conformance also depends on the linked destination sites and future changes.
