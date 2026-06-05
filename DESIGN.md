# DESIGN.md — Collab Directory LP

*Production-ready design specifications for Direction 1: Clean Energy (Mobile-First)*

---

## DESIGN DIRECTION

**Visual Thesis:** Bold, focused design with the directory mockup as the star. Blue and orange are intentional; orange only appears on CTAs. Black text on white is the foundation. Generous whitespace. Mobile-first: scales beautifully from 320px to desktop. No responsive tricks—everything stacks vertically on mobile, expands on desktop.

**Tone:** Trustworthy, energetic, no-nonsense. A founder who knows exactly what problem she's solving.

---

## TYPOGRAPHY SCALE

### Font Families
- **Display (Headlines):** DM Sans Bold or Sohne Bold
  - Weights: Bold (700) only
  - Usage: H1, H2 (main headlines)
  - Fallback: -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif

- **Body (Text, Navigation):** Lora or Basier Circle
  - Weights: Regular (400), Medium (500), Semibold (600)
  - Usage: Body copy, form labels, navigation, metadata
  - Fallback: Georgia, serif (for Lora) or -apple-system sans (for Basier)

### Type Scale (Modular Scale 1.5x)

| Usage | Mobile | Tablet | Desktop | Weight | Line Height |
|-------|--------|--------|---------|--------|-------------|
| H1 (Page Title) | 32px | 40px | 48px | Bold | 1.2 |
| H2 (Section Head) | 24px | 28px | 36px | Bold | 1.3 |
| H3 (Subhead) | 18px | 20px | 28px | Semibold | 1.4 |
| Body Copy | 16px | 16px | 18px | Regular | 1.6 |
| Small Text (Metadata) | 14px | 14px | 14px | Regular | 1.5 |
| CTA Button | 16px | 16px | 18px | Semibold | 1.4 |

### Hierarchy Rules
- Only 3 sizes used consistently (H1, H2, Body)
- No "medium" weights; jump from Regular → Semibold → Bold
- Contrast is built into size, not weight
- All text at 16px+ for mobile (accessibility)
- Line-height increases as size decreases (better readability)

---

## COLOR PALETTE

### Primary Colors (CSS Variables)
```css
--primary-blue: #0066ff;       /* Bold, energetic accent */
--primary-orange: #ff6b35;      /* Action and energy */
--text-black: #000000;          /* All body text */
--bg-white: #ffffff;            /* Card backgrounds, breathing room */
```

### Usage Rules
- **Blue:** Section backgrounds, directory mockup border, text emphasis, link underlines
- **Orange:** CTA buttons ONLY (no other use)
- **Black:** All body text, headlines, callouts
- **White:** Card backgrounds, negative space
- **Grey (optional):** #f5f5f5 (very light backgrounds if needed), #cccccc (borders)

### No other colors are allowed
- No gradients
- No transparency overlays (except background DAW/sheet music)
- Black + White + Blue + Orange only

---

## SPACING & GRID

### Spacing Scale (8px Base)
```
8px, 16px, 24px, 32px, 40px, 48px, 56px, 64px, 80px, 96px, 120px, 160px
```

### Viewport Padding (from edge)
- Mobile (320–767px): 16px left/right
- Tablet (768–1023px): 24px left/right
- Desktop (1024px+): Max-width 1200px, centered, 48px left/right

### Section Spacing (vertical)
- Mobile: 40px top/bottom per section
- Tablet: 56px top/bottom
- Desktop: 80px top/bottom

### Content Column Width
- Mobile: Full width (minus 32px padding)
- Tablet: 90% of viewport, max 600px
- Desktop: 70% of viewport, max 800px (text content), directory mockup can be wider

### Grid System
- 12-column grid on all sizes
- Mobile: 1 column (content takes columns 1–12)
- Tablet: Content in columns 3–10 (3-column gutters left/right)
- Desktop: Content in columns 3–10 (same, maintains focus)

---

## COMPONENT SPECIFICATIONS

### CTA Button
- **Size:** 48px height minimum (touch-friendly)
- **Padding:** 16px horizontal, 12px vertical (total 48px height)
- **Background:** Blue (#0066ff)
- **Text:** White, Semibold, 18px
- **Border:** None
- **Border-radius:** 0px (square edges, matches bold aesthetic)
- **Hover state:** Blue #0055dd (slightly darker)
- **Active state:** Blue #004499 (more contrast)
- **Never use:** Orange buttons. Orange is for CTAs ONLY and must be blue as per design.

Wait—**correction**: Re-read the design. Orange IS for CTAs. Let me revise:

### CTA Button (CORRECTED)
- **Size:** 48px height minimum (touch-friendly)
- **Padding:** 16px horizontal, 12px vertical (total 48px height)
- **Background:** Orange (#ff6b35)
- **Text:** Black, Semibold, 18px
- **Border:** None
- **Border-radius:** 0px (square edges, matches bold aesthetic)
- **Hover state:** Orange #ff5517 (slightly darker)
- **Active state:** Orange #ff4400 (more contrast)
- **Placement:** One button per section, centered or right-aligned on desktop
- **Never stack:** Only one CTA button visible per section

### Form Input (Email Signup)
- **Height:** 48px
- **Padding:** 12px (vertical), 16px (horizontal)
- **Border:** 2px solid #0066ff
- **Background:** White
- **Text:** 16px, Regular, Black
- **Placeholder:** 14px, Regular, #999999
- **Focus state:** Border becomes #004499 (darker blue), box-shadow: 0 0 0 3px #0066ff22 (blue with transparency)
- **Label:** 14px, Semibold, Black, positioned above input
- **Feedback:** Success (green), error (red) states—confirm specs with Rachel

### Profile Card (in Directory Mockup)
- **Width:** 280px (mobile), 320px (desktop)
- **Background:** White
- **Border:** 2px solid #0066ff
- **Border-radius:** 0px (square, consistent)
- **Padding:** 16px
- **Avatar:** 80×80px, circular, black & white placeholder photo
- **Name:** 18px, Semibold, Black
- **Role:** 14px, Regular, #0066ff
- **Location:** 14px, Regular, #666666
- **What I Offer:** 12px, Semibold, Black (label), followed by tags
- **Looking For:** 12px, Semibold, Black (label), followed by tags (orange background for tags)
- **Demo Link:** 14px, Semibold, #0066ff, underline on hover

### Section (Container)
- **Background:** White
- **Padding:** (see Spacing Scale above)
- **Borders:** None (use whitespace to separate)
- **Optional:** Ghosted DAW or sheet music in background (10–15% opacity, positioned behind text, does not interfere with readability)

---

## RESPONSIVE BREAKPOINTS

### Mobile First Approach
Build mobile layout first (320px), then enhance with:

```
Mobile:   320px — 767px   (single column, full-width)
Tablet:   768px — 1023px  (2-column, centered content)
Desktop:  1024px+         (3-column, content in center)
```

### Key Mobile Considerations
- Touch targets: 48px × 48px minimum
- Input fields: Full width, single column
- Images: 100% width of container
- Directory mockup: 100% width on mobile, full height (scrollable if needed)
- Text: Never smaller than 16px body, 24px+ headlines

---

## BACKGROUND ELEMENTS

### Ghosted DAW Visual
- **Section:** Features & Objections (or another section)
- **Opacity:** 10–15%
- **Color:** Grey (#cccccc or similar)
- **Position:** Absolute, top-right or bottom-right corner
- **Size:** 200–300px width, should NOT interfere with text readability
- **Implementation:** SVG or CSS illustration (very subtle, almost watermark)

### Sheet Music Pattern
- **Section:** Why Profit-Sharing Wins (or another section)
- **Opacity:** 10–15%
- **Color:** Grey (#cccccc or similar)
- **Pattern:** Repeating musical staff lines (or musical notation silhouette)
- **Position:** Absolute, top-left or bottom-left corner
- **Size:** 200–300px width
- **Implementation:** SVG pattern or CSS background-image

### Rule: Background Elements Must Not Reduce Readability
- If text becomes hard to read over background, reduce opacity further or reposition
- Test with actual text on top before finalizing

---

## IMAGERY SPECS

### Founder Photo
- **Size:** 400×400px (square, for circular crop)
- **Style:** Placeholder initially, will be replaced with candid photo
- **Position:** Centered, above Founder's Note section
- **Border:** None
- **CSS Filter:** None (show raw photo)

### Profile Avatars
- **Size:** 80×80px
- **Style:** Black & white placeholder photos (3–5 variations)
- **Crop:** Circular (border-radius: 50%)
- **Border:** 2px solid #0066ff
- **Filter:** None (show unmodified)

### Directory Mockup
- **Size:** Responsive (100% width on mobile, 500–600px desktop)
- **Cards:** Use the profile card spec above
- **Count:** 3–5 cards visible at once
- **Layout:** Horizontal scroll on mobile, grid layout on desktop

---

## LAYOUT EXAMPLES

### Above the Fold (Mobile)
```
┌─────────────────────┐
│    Headline (32px)  │  (32px top margin)
├─────────────────────┤
│  Subtitle (18px)    │  (16px margin)
├─────────────────────┤
│                     │
│  Directory Mockup   │  (100% width, 300px height)
│  (3 cards stacked)  │
│                     │
├─────────────────────┤
│  Founder Story      │  (16px margin)
│  (16px body text)   │
├─────────────────────┤
│  [Join the Beta]    │  (Orange button, 48px height)
│     Button          │
├─────────────────────┤
```

### Section (Desktop)
```
┌────────────────────────────────────────┐
│ Section Title (36px)                   │  (80px top margin)
│                                        │
│ Section body copy (18px, max 800px)    │
│                                        │
│ - Feature 1                            │  (16px list margin)
│ - Feature 2                            │
│ - Feature 3                            │
│                                        │
│                    [CTA Button]        │  (Right-aligned or centered)
└────────────────────────────────────────┘
                                            (80px bottom margin)
```

---

## IMPLEMENTATION NOTES

### HTML Structure
- Use semantic HTML: `<header>`, `<section>`, `<article>`, `<footer>`
- No div-itis; keep markup clean
- Use BEM naming for CSS classes if using preprocessor

### CSS Approach
- Mobile-first: Base styles are mobile, media queries add desktop styles
- CSS variables for colors, spacing, typography (see above)
- No Tailwind—write plain CSS or SCSS
- Grid system: CSS Grid (native, not Bootstrap)

### JavaScript
- Minimal JS: Form submission only
- Klaviyo form integration via script tag (provided by Klaviyo)
- Optional: Smooth scroll, scroll-triggered reveals (low priority)

### Performance
- Mobile-first: Minimal CSS for mobile, progressively enhance
- Images: Optimized (WebP + fallback), lazy-loaded if needed
- No heavy animations or decorative scripts
- Target: < 3 seconds load time on 3G

### Accessibility
- Color contrast: 4.5:1 for all text (WCAG AA)
- Form labels: Always associated with inputs (`<label for="email">`)
- Images: Alt text for all images
- Buttons: Semantic `<button>` elements, not divs
- Focus states: Visible on all interactive elements

---

## DESIGN DECISIONS & RATIONALE

1. **Orange CTA only:** Makes every action clear. User's eye goes straight to orange button.
2. **Zero border-radius:** Matches "bold" aesthetic. Angular, confident, not friendly/rounded.
3. **Two fonts max:** Limits cognitive load. Display serif + body sans creates enough contrast.
4. **No gradients:** Keeps design clean, trustworthy. Flat colors are easier to scan.
5. **Ghosted backgrounds:** Adds thematic depth (music production) without competing with content.
6. **Mobile-first:** Ensures simplicity first, enhancement on larger screens.
7. **One button per section:** Prevents decision fatigue. One action per scroll.

---

## REVIEW BEFORE BUILD

- [ ] Typography scale locked (DM Sans Bold + Lora)
- [ ] Color palette locked (#0066ff, #ff6b35, #000000, white only)
- [ ] Spacing scale locked (8px base, multiples)
- [ ] Responsive breakpoints confirmed (320, 768, 1024)
- [ ] Form input specs ready for Klaviyo integration
- [ ] Background elements (DAW + sheet music) sourced or designed
- [ ] Profile avatar placeholders ready (5 variations, B&W)
- [ ] Founder photo placeholder sourced
- [ ] Directory mockup component spec finalized

---

## NEXT STEP

Ready to build. Ask Rachel for any clarifications before starting HTML/CSS.
