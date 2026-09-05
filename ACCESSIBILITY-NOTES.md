# Accessibility Notes

This build is designed toward WCAG 2.2 Level AA for the static hub pages.

Key decisions:
- one H1 per page with semantic H2/H3 structure
- skip-to-main link
- semantic header/nav/main/section/footer structure
- native links only; no scripted widgets
- visible 3px focus indicator
- interaction targets at least 44px high where practical
- direct descriptive link text
- no hover-only information
- no decorative body images
- colored tool cards do not rely on color alone: each has a text label, heading, description, icon, and link
- light and dark palettes use separate semantic color tokens
- responsive one-column reflow on narrow screens
- reduced-motion, increased-contrast, forced-colors, and print support
- no first-party forms, analytics, scripts, frames, or connections on these three pages
- restrictive Content Security Policy for the hub itself

Final verification after deployment:
1. WAVE
2. axe DevTools
3. keyboard-only test
4. 200% zoom and 320 CSS px reflow
5. light/dark mode
6. VoiceOver or NVDA
7. Windows High Contrast / forced colors if available
