# Accessibility and Dark Mode Audit
## Faculty Work Made Easier — WCAG 2.2 AA code-level review

Date: September 4, 2026

### Scope
Reviewed and rebuilt the public homepage (`index.html`) with WCAG 2.2 Level AA criteria relevant to this static page, plus dark mode, high-contrast/forced-colors behavior, mobile reflow, and keyboard use.

This is a code-level accessibility review, not a legal certification. Final conformance also depends on the deployed environment, linked project pages, browser/assistive-technology combinations, and future content changes.

## Changes made

### Page identity and branding
- Removed “Karen Crozer” from the top/header area and from the browser title.
- Kept author information in the About section and independent-project notice, where it has context.
- Rebuilt every favicon size from the newly supplied `favicon10` source.
- Removed orange/citrus hero artwork and all decorative body images.

### WCAG 2.2 AA items addressed
- **1.1.1 Non-text Content:** no meaningful raster images are used on the page; inline SVG icons are decorative and hidden from assistive technology.
- **1.3.1 Info and Relationships:** semantic header, nav, main, sections, headings, articles, lists, aside, and footer; heading hierarchy is H1 → H2 → H3.
- **1.3.2 Meaningful Sequence:** DOM reading order matches visual order.
- **1.4.1 Use of Color:** color is not the only cue for links, navigation state, categories, or focus.
- **1.4.3 Contrast (Minimum):** core light- and dark-mode text colors were selected above AA thresholds.
- **1.4.10 Reflow:** responsive one-column layout below tablet widths; no fixed content widths that require two-dimensional scrolling at narrow viewport sizes.
- **1.4.11 Non-text Contrast:** focus indicators, borders, and essential controls use stronger contrast.
- **1.4.12 Text Spacing:** no fixed-height text containers; cards and sections can grow when users change text spacing.
- **1.4.13 Content on Hover or Focus:** no information appears only on hover/focus.
- **2.1.1 Keyboard:** all controls are native links and keyboard operable.
- **2.1.2 No Keyboard Trap:** no scripts, dialogs, or custom controls can trap focus.
- **2.4.1 Bypass Blocks:** visible-on-focus “Skip to main content” link.
- **2.4.2 Page Titled:** concise descriptive page title.
- **2.4.3 Focus Order:** source order is logical and matches the page.
- **2.4.4 Link Purpose (In Context):** link text describes destinations/actions.
- **2.4.6 Headings and Labels:** headings describe each section.
- **2.4.7 Focus Visible:** strong 3px focus ring with offset.
- **2.4.11 Focus Not Obscured (Minimum):** header is no longer sticky, avoiding focus/anchor targets being hidden behind it.
- **2.5.8 Target Size (Minimum):** navigation, buttons, and footer/project links are at least 44px high where practical, exceeding the 24×24 CSS-pixel AA minimum.
- **3.1.1 Language of Page:** `lang="en"` is present.
- **3.2.x Predictable:** no unexpected context changes.
- **4.1.2 Name, Role, Value:** native semantic elements are used instead of custom scripted widgets.

### Dark mode
- Replaced the earlier color inversion approach with dedicated semantic dark-mode variables.
- Fixed the major dark-mode failure in the dark “work behind the work” section: its background no longer becomes light when `--ink` changes in dark mode.
- Added dark-mode values for text, muted text, borders, links, focus rings, card surfaces, tinted task cards, badges, and footer.
- Added separate light/dark `theme-color` metadata.
- Kept body artwork out of the design so transparent-image behavior cannot create black boxes in dark mode.

### Additional resilience
- `prefers-reduced-motion` removes nonessential movement.
- `prefers-contrast: more` strengthens borders.
- `forced-colors: active` preserves visible boundaries and focus behavior in Windows High Contrast/forced-color modes.
- Print styles avoid dark backgrounds.
- Viewport settings preserve user zoom.
- No horizontal-scrolling mobile navigation.
- No placeholder `href="#"` links; unpublished project destinations are shown as status text instead of fake links.

## Contrast spot checks
Representative pairings used in the rebuild:
- Light body text `#17253a` on white: about **15.4:1**
- Light secondary text `#3c4b5f` on white: about **8.9:1**
- Light muted text `#586779` on white: about **5.8:1**
- Light link `#155d82` on white: about **7.2:1**
- Dark body text `#f2f6fa` on `#121a24`: about **16.1:1**
- Dark secondary text `#d6e0e9` on `#121a24`: about **13.1:1**
- Dark muted text `#b5c3d1` on `#121a24`: about **9.8:1**
- Dark link `#8fd3ff` on `#121a24`: about **10.8:1**
- Mission text `#f7fbff` on `#17283d`: about **14.4:1**

## Final deployment checks still recommended
1. Run the deployed URL through WAVE and axe DevTools after GitHub Pages updates.
2. Keyboard-test in Chrome/Safari/Firefox: Tab, Shift+Tab, Enter, skip link, and all navigation.
3. Test at 200% browser zoom and at approximately 320 CSS px width.
4. Test macOS/iOS dark mode and Windows High Contrast/forced-colors if available.
5. Test with VoiceOver or NVDA for heading navigation and link announcements.
6. Add verified public URLs for CCC English OER Picks, The OER Promptbook, and Student Learning Labs when ready; do not replace status text with `#` links.
7. Re-run accessibility review whenever major content, navigation, scripts, forms, or interactive widgets are added.
