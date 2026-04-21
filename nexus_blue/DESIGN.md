# Design System Strategy: The Architectural Order

## 1. Overview & Creative North Star
This design system is built upon the Creative North Star of **"The Architectural Order."** In the high-stakes world of B2B wholesale, "trust" is often misidentified as "boring." We are rejecting that premise. Instead, we are creating a digital environment that feels like a flagship corporate headquarters—structured, expansive, and expensive.

The system breaks the traditional "box-and-line" e-commerce template by utilizing **Intentional Asymmetry** and **Tonal Depth**. We move away from generic grids to a layout that feels curated. Expect large, confident typography scales to overlap subtle surface shifts, creating a tactile hierarchy that guides a professional buyer through high-volume tasks with zero friction and maximum prestige.

---

## 2. Colors & Surface Logic
The palette is anchored by the authoritative `primary` (#00327d) and supported by a sophisticated range of `surface` tones. 

### The "No-Line" Rule
Standard B2B UI is cluttered with 1px borders. **In this system, 1px solid borders are prohibited for sectioning.** Boundaries must be defined exclusively through background color shifts. 
*   Use `surface-container-low` for secondary content areas sitting on a `surface` background.
*   The transition between `surface` and `surface-container-high` provides enough visual friction to define a header or sidebar without the "cheapness" of a stroke.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. 
*   **Level 0:** `surface` (The base canvas).
*   **Level 1:** `surface-container-low` (Subtle content grouping).
*   **Level 2:** `surface-container-highest` (Interactive focal points or modals).
By nesting a `surface-container-lowest` card inside a `surface-container-low` section, you create a "recessed" or "elevated" feel that mimics architectural molding.

### The "Glass & Gradient" Rule
To elevate the "Professional Blue," avoid flat fills for large hero areas. Use a subtle linear gradient from `primary` (#00327d) to `primary-container` (#0047ab) at a 135-degree angle. For floating navigation or quick-action bars, apply **Glassmorphism**: use a semi-transparent `surface` color with a `backdrop-filter: blur(20px)` to create a high-end, frosted-glass effect.

---

## 3. Typography
We utilize **Inter** across all scales to maintain a singular, modernist voice. The hierarchy is designed to oscillate between "Editorial Statement" and "Data Precision."

*   **Display & Headline Scale:** Use `display-lg` and `headline-lg` for landing pages and category headers. These should feel intentional and spacious. Don't be afraid of generous letter-spacing (-0.02em) to give it a premium, "Swiss-style" look.
*   **Title & Body Scale:** `title-md` is your workhorse for card titles and section headers. `body-md` is optimized for readability in long-form descriptions.
*   **Label Scale:** `label-md` and `label-sm` are critical for B2B. These should be used for SKU numbers, stock status, and table headers. They represent the "Precision" side of the Architectural Order.

---

## 4. Elevation & Depth
We define importance through **Tonal Layering** rather than traditional drop shadows.

*   **The Layering Principle:** Depth is achieved by "stacking." A card does not need a shadow to be seen; it needs to be `surface-container-lowest` on a `surface-container-low` background. 
*   **Ambient Shadows:** If an element must float (e.g., a "Quick Add" FAB), use an extra-diffused shadow. 
    *   *Blur:* 24px–40px. 
    *   *Opacity:* 4%–6%. 
    *   *Color:* Use a tinted version of `on-surface` (#1b1c1c) rather than pure black.
*   **The Ghost Border Fallback:** For accessibility in form inputs, use a "Ghost Border." Apply the `outline-variant` token at 15% opacity. It should be felt, not seen.

---

## 5. Components

### Wholesale Registration Forms
*   **Layout:** Move away from single-column forms. Use a two-column asymmetric layout where the left side uses `headline-sm` to explain *why* the data is needed, and the right side contains the inputs.
*   **Inputs:** Use the `surface-container-low` fill with a `sm` (0.125rem) rounding. No borders. On focus, transition the background to `surface-container-high` and add a 2px `primary` bottom-bar indicator.

### Data Tables for Bulk Orders
*   **The Rule:** No vertical or horizontal lines. 
*   **Structure:** Use `surface-container-low` for the header row. Use alternating `surface` and `surface-container-lowest` for rows (zebra striping) but with zero-contrast transitions. 
*   **Interaction:** On hover, a row should shift to `primary-fixed` at 10% opacity. This provides a "highlight" feel that is sophisticated, not jarring.

### Product Category Grids
*   **Editorial Layout:** Avoid the "equal-sized box" grid. Use a masonry-inspired layout where "Featured Categories" take up 2/3 of the width, and secondary categories stack vertically.
*   **Imagery:** Images should be inset within cards using `md` (0.375rem) rounding. Use a subtle `surface-variant` overlay on empty states to maintain the "Architectural" solidity.

### Buttons & Chips
*   **Primary Button:** `primary` fill, `on-primary` text. No border. Use `lg` (0.5rem) rounding for a modern feel.
*   **Chips:** For "In Stock" or "Bulk Discount," use `secondary-container` with `on-secondary-container` text. These should be `full` (9999px) rounded to contrast against the sharper architectural lines of the rest of the UI.

---

## 6. Do’s and Don’ts

### Do:
*   **Use Whitespace as a Component:** Treat empty space as a structural element that separates high-density data.
*   **Embrace Tonal Contrast:** Use the `tertiary` tokens (#651f00) sparingly for "Sale" or "Urgent" alerts to create a high-fashion pop against the professional blue.
*   **Align to the Grid, then Break it:** Ensure text is perfectly aligned, then allow a product image to "bleed" over the edge of a container for a custom, editorial feel.

### Don’t:
*   **Don't use 100% Black:** Always use `on-surface` (#1b1c1c) for text to keep the interface feeling "deep" rather than "stark."
*   **Don't use Default Shadows:** Avoid the "Material Design" standard floating look. We want "Architectural Stacking," not "App Levitation."
*   **Don't use Dividers:** If you feel the need to add a line, try adding 16px of `padding` or a subtle color shift instead. Only use `outline-variant` at low opacity if the logic truly breaks without it.