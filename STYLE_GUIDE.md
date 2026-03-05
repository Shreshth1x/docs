# BasicsOS Landing Page Style Guide

## 1. Typography

**Font Family:** [DM Sans](https://fonts.google.com/specimen/DM+Sans) (via `next/font/google`)

| Element | Size (Mobile/Desktop) | Weight | Tracking | Line Height | Color | Usage |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **H1** | 32px / 52px | Normal (400) | -1.56px | 1.05 | `text-primary` | Hero titles |
| **H2** | 36px / 48px | Normal (400) | -1.39px | 1.05 | `text-primary` | Section headers |
| **H3** | 20px (xl) | Normal (400) | Normal | Normal | `text-primary` | Card titles |
| **Body** | 16px (base) | Normal (400) | Normal | Relaxed | `text-secondary` | Main descriptions |
| **Small** | 14px (sm) | Normal (400) | Normal | Normal | `text-secondary` | Meta info, footers |
| **Button**| 14px (sm) | Medium (500) | Normal | Normal | White / `text-primary` | Actions |

**Notes:**
- Headings are generally `font-normal` (400 weight), relying on size and tight tracking for impact.
- Body text is often `text-secondary` for a softer look.

## 2. Color Palette

Colors are defined in `globals.css` as CSS variables and Tailwind theme extensions.

### Backgrounds
- **Primary:** `#f3f3f3` (`var(--color-bg-primary)`) - Main page background.
- **Secondary:** `#e8e8e6` (`var(--color-bg-secondary)`) - Cards, UI elements, scrollbar track.
- **Medium:** `#d4d4d2` (`var(--color-bg-medium)`) - Deeper backgrounds.
- **Soft:** `#c5c5c3` (`var(--color-bg-soft)`) - Scrollbar thumb.

### Text
- **Primary:** `#050505` (`var(--color-text-primary)`) - Headings, high-contrast text.
- **Secondary:** `rgba(0,0,0,0.56)` (`var(--color-text-secondary)`) - Body text, inactive states.
- **Tertiary:** `rgba(0,0,0,0.72)` (`var(--color-text-tertiary)`) - Subtitles (less common).

### Accents (Green)
- **Mid:** `#22955C` (`var(--color-accent-mid)`) - **Primary Brand Color**. Buttons, active states, highlights.
- **Strong:** `#1B7D4E` (`var(--color-accent-strong)`) - Hover states for interactive elements.
- **Soft:** `#E8F5EE` (`var(--color-accent-soft)`) - Background highlights (rare).

### Borders
- **Border:** `#e2e2e2` (`var(--color-border)`) - Dividers, card borders.

## 3. Spacing & Layout

- **Container Width:** `max-w-[1200px] xl:max-w-[1400px] 2xl:max-w-[1600px]` (Responsive scaling).
- **Horizontal Padding:** `px-6` (24px) or `px-[30px]`.
- **Vertical Spacing:**
  - Section Padding: `py-[125px]` (Large, breathable spacing between sections).
  - Component Margins: `mb-[50px]` (e.g., Hero bottom margin).
- **Navbar Height:** `54px` (Fixed).

## 4. UI Elements

### Buttons
- **Primary:**
  ```tsx
  <button className="bg-accent-mid text-white rounded-[4px] px-6 h-9 text-sm font-medium hover:bg-accent-strong transition-colors">
    Action
  </button>
  ```
- **Secondary / Link:**
  ```tsx
  <button className="text-sm font-normal text-text-secondary hover:text-text-primary transition-colors flex items-center gap-2">
    Link Text &rarr;
  </button>
  ```
- **Border Radius:** Generally `rounded-[4px]` for buttons and small inputs.

### Cards
- **Background:** `bg-bg-secondary` or `bg-white` (for highlighted plans).
- **Border:** `border border-border`.
- **Radius:** `rounded-xl` (Larger radius than buttons).
- **Padding:** `p-8` is common.

### Navigation / Tabs
- **Active State:** Text becomes `text-text-primary` (Medium weight).
- **Inactive State:** Text is `text-text-secondary`.
- **Indicator:** Framer Motion `layoutId` underline (`h-[3px] bg-text-primary rounded-full`).

## 5. Visual Effects & Texture

- **Background Lines:** A decorative vertical grid (`BackgroundLines` component) sits behind content.
- **Scrollbar:** Custom styled scrollbar (8px width, `#c5c5c3` thumb, rounded).
- **Animations:**
  - **Transitions:** `transition-colors` used ubiquitously on interactive elements.
  - **Entrance:** `framer-motion` for opacity/layout transitions (e.g., tab switching in Hero).
  - **Marquee:** `animate-marquee` (30s linear infinite) defined in theme.
- **Terminal Effect:** Blinking cursor animation (`.terminal-cursor`) available in CSS.
