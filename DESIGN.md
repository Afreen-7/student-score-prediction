# Design System Document

## 1. Overview & Creative North Star: "The Precision Editor"
This design system moves beyond the "utilitarian dashboard" and enters the realm of **Precision Editorial**. While inspired by the technical clarity of Streamlit and modern data science tools, this system rejects the cluttered "widget-heavy" look. 

The Creative North Star is **The Precision Editor**: a high-end interface that treats data like a fine-print publication. It balances the raw power of technical analysis with the sophisticated breathing room of an architectural journal. We achieve this through:
- **Asymmetric Weighting:** Heavy sidebars contrasted against sprawling, airy main canvases.
- **Tonal Depth:** Replacing harsh grid lines with subtle shifts in surface color.
- **Micro-Typography:** Using `Space Grotesk` for technical metadata to provide a "engineered" feel against the "humanist" `Inter` body text.

---

## 2. Colors & Surface Philosophy
Our palette is a sophisticated "Cool Industrial" range, punctuated by a surgical "Signal Red" (`primary`).

### The "No-Line" Rule
**Explicit Instruction:** 1px solid borders are prohibited for sectioning. To separate the sidebar from the main content or a table from a background, use background shifts only. 
*   **Sidebar:** `surface_container_low` (#f2f4f8)
*   **Main Canvas:** `surface` (#f7f9fd)
*   **Content Cards:** `surface_container_lowest` (#ffffff)

### Surface Hierarchy & Nesting
Treat the UI as physical layers. An analysis card (`surface_container_lowest`) should sit atop the main canvas (`surface`). Within that card, a code snippet or sub-section should use `surface_container` (#eceef2) to "recess" into the page.

### The "Glass & Gradient" Rule
For floating modals or pop-over filters, use Glassmorphism. Apply `surface_container_lowest` at 80% opacity with a `24px` backdrop blur. For primary CTAs, use a subtle linear gradient from `primary` (#b81120) to `primary_container` (#dc3135) at a 135-degree angle to add "soul" and dimension to the action.

---

## 3. Typography
We use a dual-typeface system to bridge the gap between "Readability" and "Technicality."

*   **Primary Typeface:** `Inter` (Sans-serif) - Used for all headers and body text to ensure maximum legibility and a modern, neutral tone.
*   **Technical Typeface:** `Space Grotesk` - Used exclusively for `label-md` and `label-sm`. This mono-spaced influence signals to the user that they are looking at "data" or "system outputs."

| Level | Token | Font | Size | Weight | Intent |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Display** | `display-lg` | Inter | 3.5rem | 700 | Hero metrics / High-impact data |
| **Headline** | `headline-sm`| Inter | 1.5rem | 600 | Section headers |
| **Title** | `title-md` | Inter | 1.125rem| 500 | Card titles |
| **Body** | `body-md` | Inter | 0.875rem| 400 | Standard prose and descriptions |
| **Label** | `label-md` | Space Grotesk| 0.75rem | 500 | Table headers, chip labels, metadata |

---

## 4. Elevation & Depth
In this system, elevation is conveyed through **Tonal Layering**, not shadows.

*   **The Layering Principle:** To highlight a data table, do not draw a box around it. Instead, change the background of the table area to `surface_container_lowest` against the `surface` background.
*   **Ambient Shadows:** If an element must float (e.g., a tool-tip or dropdown), use a shadow color of `on_surface` (#191c1f) at **4% opacity** with a `32px` blur and `8px` Y-offset. It should feel like a soft glow, not a dark smudge.
*   **The "Ghost Border" Fallback:** For input fields where a boundary is required for clarity, use `outline_variant` at **20% opacity**. It should be barely perceptible.

---

## 5. Components

### Buttons
*   **Primary:** Gradient (`primary` to `primary_container`). `0.375rem` (md) radius. White text (`on_primary`).
*   **Secondary:** No background. `outline` text and a `0.125rem` (sm) bottom-border that only appears on hover.
*   **Tertiary:** `surface_container_high` background with `on_surface` text for low-priority actions.

### Data Tables (The "Editorial" Table)
*   **Header:** `label-md` (Space Grotesk), uppercase, tracking 0.05em. 
*   **Rows:** No horizontal lines. Use a `surface_container_low` background on hover.
*   **Padding:** Aggressive vertical padding (16px+) to give data room to breathe.

### Inputs & Sliders
*   **Sidebar Inputs:** Use `surface_container_highest` for the track of sliders to provide high contrast against the `surface_container_low` sidebar.
*   **Focus State:** A `2px` ring of `surface_tint` at 40% opacity.

### Chips
*   **Filter Chips:** `surface_container_high` with no border. When active, use `primary` background with `on_primary` text.

### Charts & Data Viz
*   **Trend Lines:** Use `primary` (#b81120) for the main data thread.
*   **Comparison Lines:** Use `tertiary` (#00685a) for secondary metrics.
*   **Grid Lines:** Use `outline_variant` at 10% opacity. If possible, remove Y-axis lines entirely and use only sparse X-axis markers.

---

## 6. Do's and Don'ts

### Do
*   **DO** use `surface_container_low` for the entire sidebar to create a clear functional split from the main canvas.
*   **DO** use "Negative Space" as a structural tool. If two sections feel too close, increase padding rather than adding a divider line.
*   **DO** align technical labels (`label-sm`) to the top-right of data points for a "blueprinted" look.

### Don't
*   **DON'T** use pure black (#000000) for text. Always use `on_surface` (#191c1f) to maintain the premium, soft-technical feel.
*   **DON'T** use 100% opaque borders. They break the "The Precision Editor" aesthetic and make the UI feel like a legacy enterprise app.
*   **DON'T** use "Standard" blue for links. Use `primary` or `tertiary` to stay within the signature palette.