# Extended UI Patterns Reference

Read this file when building complex, multi-section UIs or when the SKILL.md patterns
don't cover the specific component/layout needed.

## Table of Contents
1. [Navigation Patterns](#navigation)
2. [Dashboard Layouts](#dashboards)
3. [Data Display](#data-display)
4. [Modal & Overlay Patterns](#modals)
5. [Form Patterns](#forms)
6. [Empty & Loading States](#states)
7. [Dark Mode Design](#dark-mode)
8. [Mobile-First Adaptations](#mobile)

---

## Navigation Patterns <a name="navigation"></a>

### Top Nav (Marketing / Simple Apps)
```
height: 60–64px
logo: left-aligned, 24–32px height
links: center or right, 14–15px, medium weight, 24–32px gap
CTA: rightmost, primary button style
sticky: yes, with backdrop-blur on scroll
```

### Sidebar Nav (SaaS / Dashboards)
```
width: 220–260px (expanded), 56–64px (collapsed icon-only)
background: surface or slightly darker than page bg
items: 36–40px height, 8–12px h-padding, 8px border-radius
active: brand-tinted bg + brand text
icon: 16–18px, muted color (active: brand)
section headers: label style, 8px margin-top
bottom dock: user avatar + settings
```

### Breadcrumbs
```
font-size: 13–14px
color: text-muted with > separator
last item: text-primary (current page)
max items visible: 3–4, middle items collapse to "..."
```

---

## Dashboard Layouts <a name="dashboards"></a>

### KPI Cards Row
```
grid: 3–4 columns (repeat(auto-fit, minmax(200px, 1fr)))
card padding: 20–24px
metric: 28–32px, 700 weight
label: 12px, text-muted, uppercase
delta: 13px with colored arrow icon (green up, red down)
```

### Chart + Stats Layout
```
main chart: 60–70% width
side stats: 30–40% width, stacked vertically
chart padding: 24px all sides
axis labels: 11–12px, text-muted
gridlines: 1px, 5–8% opacity
tooltip: surface bg, border, 8px radius, 12px padding
```

---

## Data Display <a name="data-display"></a>

### Data Table Best Practices
```
Empty first column: 16–20px (visual anchor)
Column headers: sortable (show sort icon on hover, always show on active)
Row actions: appear on row hover, right-aligned
Bulk actions: appear above table when rows selected
Pagination: bottom, "Showing X–Y of Z", prev/next + page numbers
Filter bar: above table, inline chips for active filters
```

### List vs. Table Decision
- Use **table** when: comparing across multiple attributes
- Use **list/cards** when: each item has a primary identity and secondary details

---

## Modal & Overlay Patterns <a name="modals"></a>

### Standard Modal
```
backdrop: rgba(0,0,0,0.4) or rgba(0,0,0,0.6) dark mode
container: surface bg, 480–560px wide, 12–16px radius
padding: 24px
header: title (18px/600) + close button (top-right, 32px touch target)
body: scrollable if content exceeds ~60vh
footer: action buttons, right-aligned (destructive on left)
animation: scale(0.96)→scale(1) + fade, 150ms ease-out
```

### Confirmation Dialog (destructive)
```
max-width: 400px
icon: 40px warning/error icon at top
title: clear consequence ("Delete workspace?")
body: explain what can't be undone
buttons: Cancel (left/ghost) + Confirm action (right/destructive)
```

### Drawer / Side Panel
```
width: 400–480px (desktop), full-width (mobile)
slides from: right
backdrop: yes, but lighter (rgba(0,0,0,0.2))
close: X button + backdrop click + Escape key
```

---

## Form Patterns <a name="forms"></a>

### Field Layout
```
label: above input, 13–14px, 600 weight, 4–6px margin-bottom
input: full-width within form container
helper text: below input, 12–13px, text-muted, 4px margin-top
error text: below input, 12–13px, error color, with ✕ icon
```

### Multi-Step Forms
```
progress indicator: top, show step X of Y
navigation: Back (ghost) + Continue (primary) — never "Submit" until final step
validation: validate on blur, not on keystroke
summary step: show all entered data before final submit
```

### Inline Editing (Notion-style)
```
field: looks like plain text by default
hover: show subtle bg change + edit icon
focus: becomes input with border
save: on blur or Enter
cancel: Escape
```

---

## Empty & Loading States <a name="states"></a>

### Empty State Anatomy
```
illustration or icon: 80–120px, muted/brand color
title: 16–18px, 600 weight — describe the state, not "No data found"
description: 14px, text-muted — explain benefit or next action
CTA: primary button — one clear action
alignment: center, within the content area
```

### Loading States
```
skeleton screens: preferred over spinners for content areas
spinner: only for button actions or small inline loads
skeleton: match the shape of actual content (same height, widths)
shimmer animation: left-to-right gradient sweep, 1.5s loop
never show a blank white page — always show skeleton
```

### Error State
```
icon: 48px error/warning illustration
title: what went wrong (human language)
description: what the user can do about it
actions: Retry + Contact support (if applicable)
```

---

## Dark Mode Design <a name="dark-mode"></a>

Dark mode is NOT just inverting light mode. Use these principles:

### Surface Elevation (dark)
```
Level 0 (page bg):    #0a0a0b or #09090b
Level 1 (cards):      #111113 or #0f0f11  (+2-3% lightness)
Level 2 (modals):     #161618 or #141416  (+3-4% lightness)
Level 3 (tooltips):   #1c1c1f            (+5-6% lightness)
```
Use lightness to create depth, not shadows.

### Text in Dark Mode
```
Primary:  rgba(255,255,255,0.95)
Secondary: rgba(255,255,255,0.6)
Muted:    rgba(255,255,255,0.35)
```

### Borders in Dark Mode
```
Subtle:  rgba(255,255,255,0.06–0.08)
Default: rgba(255,255,255,0.10–0.12)
Strong:  rgba(255,255,255,0.16–0.20)
```

---

## Mobile-First Adaptations <a name="mobile"></a>

### Breakpoints
```
mobile:  < 640px  (design first here)
tablet:  640–1024px
desktop: > 1024px
```

### Mobile Navigation
```
Bottom tab bar: 4–5 items max, icon + label, 56–64px height
Hamburger: only if sidebar nav is required
Back button: top-left, always visible
```

### Touch Adaptations
```
All tap targets: min 44×44px
Form inputs: font-size ≥16px (prevents iOS zoom)
Swipe gestures: add as enhancement, never sole interaction
Modals: become full-screen bottom sheets on mobile
Tables: become scrollable cards or stacked list items
```

### Typography Scaling
```
Desktop H1 → Mobile: reduce 20–25%
Desktop body → Mobile: keep same (15–16px)
Never use display sizes on mobile without testing
```