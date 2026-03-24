# Design System Specification: The Academic Atelier

## 1. Overview & Creative North Star: "The Digital Curator"
This design system moves away from the sterile, "template-box" feel of traditional educational platforms. Instead, it adopts the persona of **The Digital Curator**—an editorial-inspired, high-end environment that treats educational resources like featured gallery pieces. 

The aesthetic is **Soft Minimalism**. We break the rigid grid through intentional asymmetry: headlines may offset from body copy, and primary actions float with a physical, paper-like presence. By prioritizing white space as a functional element rather than a "gap," we provide educators and students with the cognitive "breathing room" required for deep learning.

---

## 2. Color & Surface Architecture
The palette transitions from a crisp, professional white to a rejuvenating mint green, grounded by sophisticated slate grays.

### The "No-Line" Rule
**Prohibit 1px solid borders for sectioning.** To create a premium feel, boundaries must be defined solely through background color shifts or subtle tonal transitions. 
- Use `surface-container-low` (#f2f4f6) to distinguish a sidebar from the `surface` (#f7f9fb) main content area.
- Use `surface-container-lowest` (#ffffff) to make a resource card "pop" against a `surface-container` (#eceef0) gallery background.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. 
- **Base Layer:** `surface` (#f7f9fb)
- **Secondary Sectioning:** `surface-container-low` (#f2f4f6)
- **Interactive Elements/Cards:** `surface-container-lowest` (#ffffff)
- **Active/Hover States:** `surface-container-high` (#e6e8ea)

### The "Glass & Gradient" Rule
To avoid a flat "Bootstrap" appearance, use **Glassmorphism** for navigation bars and floating resource drawers. Apply `surface` with a 70% opacity and a `backdrop-blur` of 12px.
- **Signature Texture:** Primary CTAs should utilize a subtle linear gradient: `primary` (#006b55) to `primary-container` (#4fb094) at a 135-degree angle. This adds a "jewel-toned" depth that feels custom and high-end.

---

## 3. Typography: Editorial Authority
We use a dual-sans-serif pairing to distinguish between "Display" (inspirational) and "Utility" (functional) text.

*   **Display & Headlines (Plus Jakarta Sans):** Chosen for its modern, slightly wider stance. Use `display-lg` (3.5rem) with `-0.02em` letter spacing for hero headers to create an authoritative, editorial impact.
*   **Body & Labels (Inter):** The industry standard for legibility. Use `body-md` (0.875rem) for general resource descriptions to maintain a clean, high-density information flow.

**Hierarchy Note:** Always maintain a high contrast between `headline-lg` and `body-md`. If a resource title is `title-lg`, ensure the metadata (author, date) uses `label-md` in `on-surface-variant` (#3e4945) to create clear visual "lanes" for the eye.

---

## 4. Elevation & Depth: Tonal Layering
Traditional drop shadows are often messy. This system uses **Tonal Layering** and **Ambient Light** to convey importance.

*   **The Layering Principle:** Place a `surface-container-lowest` card on a `surface-container-low` background. The slight shift from white to off-white creates a "soft lift" that is felt rather than seen.
*   **Ambient Shadows:** For "Floating Action Buttons" or "Active Modals," use a shadow with a 20px blur and 4% opacity, using the `on-surface` color (#191c1e). This mimics natural light rather than digital "glow."
*   **The "Ghost Border" Fallback:** If a border is required for accessibility in input fields, use `outline-variant` (#bdc9c3) at **20% opacity**. Never use 100% opaque borders.

---

## 5. Components

### Buttons
*   **Primary:** Gradient fill (`primary` to `primary-container`), white text, `rounded-md` (0.75rem). No shadow on rest; 4% ambient shadow on hover.
*   **Secondary:** `primary-fixed-dim` (#78d8ba) background with `on-primary-fixed-variant` (#005140) text.
*   **Tertiary:** Ghost style. No background/border. Text in `primary`. Underline appears only on hover.

### Resource Cards (Custom Component)
*   **Structure:** No borders. Background: `surface-container-lowest`. 
*   **Elevation:** On hover, transition background to `surface-bright` and apply a 2px vertical offset (translateY).
*   **Content:** Forbid divider lines. Separate the "Resource Type" tag from the "Title" using a `spacing-4` (1rem) vertical gap.

### Input Fields
*   **Style:** `surface-container-low` fill. No border. On focus, a 2px "Ghost Border" of `primary` at 40% opacity appears.
*   **Corners:** `rounded-md` (0.75rem).

### Chips (Filters)
*   **Unselected:** `secondary-container` (#d5e3fc) with `on-secondary-container` (#57657a) text.
*   **Selected:** `primary` (#006b55) with `on-primary` (#ffffff) text.

---

## 6. Do’s and Don’ts

### Do:
*   **Do** use asymmetrical margins. A hero image can be wider than the text container to create a "magazine" feel.
*   **Do** use `spacing-12` and `spacing-16` for section vertical padding to emphasize a "luxury of space."
*   **Do** use `primary-fixed` (#94f5d6) for subtle highlights in "Success" states instead of harsh greens.

### Don't:
*   **Don't** use 1px dividers to separate list items. Use `spacing-3` of vertical white space or a subtle `surface-variant` background shift.
*   **Don't** use pure black (#000000) for text. Always use `on-surface` (#191c1e) to maintain the "Soft Professional" aesthetic.
*   **Don't** use the `default` (0.5rem) corner radius for large containers. Use `xl` (1.5rem) for main content areas and `md` (0.75rem) only for small components like buttons/inputs.