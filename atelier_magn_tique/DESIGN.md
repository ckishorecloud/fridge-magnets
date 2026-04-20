# Design System Documentation: High-End Editorial E-Commerce

## 1. Overview & Creative North Star
**Creative North Star: The Curated Gallery**
This design system is built to transform the humble fridge magnet from a souvenir into a piece of curated art. We are moving away from the rigid, "templated" look of traditional e-commerce. Instead, we embrace the spirit of a high-end photo gallery or an independent boutique magazine. 

By leveraging **intentional asymmetry**, **tactile rotations**, and **tonal layering**, we create a digital experience that feels as physical and premium as the products themselves. The layout should feel "arranged" rather than "gridded," mimicking the organic way magnets are placed on a kitchen surface, while maintaining the sophisticated polish of a luxury printing house.

---

## 2. Colors & Surface Philosophy
The palette is rooted in a warm, organic foundation of cream and forest green, designed to feel inviting yet authoritative.

### The "No-Line" Rule
**Explicit Instruction:** You are prohibited from using 1px solid borders to define sections or containers. Traditional borders create a "boxed-in" feel that contradicts our boutique aesthetic. 
- **Sectioning:** Define boundaries solely through background color shifts. For example, a section using `surface-container-low` (#f9f2ee) should sit directly against a `surface` (#fff8f4) background.
- **Visual Breathing Room:** Use generous whitespace (from the spacing scale) to allow content to "own" its territory without needing a cage.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers—stacked sheets of fine cardstock or frosted glass.
- **Layer 1 (Background):** `surface` (#fff8f4)
- **Layer 2 (Content Areas):** `surface-container-low` (#f9f2ee)
- **Layer 3 (Floating Elements/Cards):** `surface-container-lowest` (#ffffff)
Use these tiers to create "nested" depth. An inner container should always be a slightly different tier than its parent to define importance through tone rather than structure.

### The "Glass & Gradient" Rule
To elevate the experience beyond flat design:
- **Glassmorphism:** Use for floating navigation bars or overlays. Utilize `surface` at 70-80% opacity with a `backdrop-filter: blur(20px)`.
- **Signature Textures:** For primary CTAs and hero sections, use a subtle linear gradient transitioning from `primary` (#062513) to `primary-container` (#1d3b27). This adds a "visual soul" and a velvet-like depth that a flat hex code cannot achieve.

---

## 3. Typography
Our typography pairing balances the bold, expressive nature of **Epilogue** with the functional clarity of **Manrope**.

- **Display & Headlines (Epilogue):** These are our "editorial voices." Use `display-lg` for hero moments to create high-contrast, magazine-style layouts. The bold weight of Epilogue communicates quality and craftsmanship.
- **Body & Labels (Manrope):** All functional text—descriptions, prices, and navigation—must use Manrope. It provides a clean, neutral counterpoint to the headlines, ensuring readability in dense product information.
- **Hierarchy as Identity:** Use extreme scale differences. A `display-md` headline paired with a `label-md` uppercase caption creates the "Boutique" look.

---

## 4. Elevation & Depth
In this system, depth is felt, not seen. We avoid the heavy, muddy shadows of legacy web design.

- **The Layering Principle:** Stacking `surface-container` tiers (Lowest to Highest) creates a natural, soft lift. This is our primary method of elevation.
- **Ambient Shadows:** When a card must float (e.g., a product card on hover), use an extra-diffused shadow. 
    - **Specs:** `Y: 12px, Blur: 32px, Color: rgba(29, 27, 25, 0.06)`. 
    - The shadow color must be a low-opacity version of `on-surface` (#1d1b19) to mimic natural light.
- **The "Ghost Border" Fallback:** If a border is required for accessibility (e.g., an input field), use the `outline-variant` (#c2c8c0) at **20% opacity**. Never use 100% opaque borders.
- **Tactile Rotation:** To mimic the "magnet" feel, product cards in a grid should have subtle, alternating rotations (e.g., `-1.5deg` and `+1.5deg`). This breaks the "digital" perfection and adds a friendly, tactile charm.

---

## 5. Components

### Buttons
- **Primary:** Gradient from `primary` to `primary-container`. White text (`on-primary`). Roundedness: `xl` (1.5rem).
- **Secondary:** `surface-container-high` background with `primary` text. No border.
- **Tertiary:** Pure text with a subtle underline using `surface-tint`.

### Product Cards (The "Magnet" Component)
- **Shape:** `md` (0.75rem) corner radius.
- **Layout:** Asymmetric. Image should bleed to the top and sides, with product info in a `surface-container-lowest` area at the bottom.
- **Interaction:** On hover, the rotation should reset to `0deg` and the ambient shadow should slightly deepen.

### Input Fields
- **Style:** Background set to `surface-container-highest`. No border.
- **States:** On focus, transition the background to `surface-container-lowest` and add a "Ghost Border" using `surface-tint` at 20%.

### Navigation (Glass Header)
- **Style:** `surface` at 80% opacity, `backdrop-blur: 16px`.
- **Layout:** Asymmetric logo placement (far left) with navigation links clustered to the right, creating a sense of "arranged" balance.

---

## 6. Do's and Don'ts

### Do:
- **Do** use "offset" layouts. If an image is on the left, let the text overlap it slightly using a `surface-container` card to create a 3D effect.
- **Do** use the `primary-fixed-dim` (#accfb3) for subtle accent backgrounds or "New Arrival" tags.
- **Do** prioritize high-quality, lifestyle photography. The design system is a frame; the photos are the art.

### Don't:
- **Don't** use dividers or horizontal rules. Use a 48px or 64px vertical gap instead.
- **Don't** use pure black for text. Always use `on-surface` (#1d1b19) to maintain the warm, organic feel.
- **Don't** align everything to a rigid center. Experiment with "weighted" layouts where one side of the screen feels heavier than the other.
- **Don't** use sharp corners. Every element should have at least the `sm` (0.25rem) radius to maintain the "friendly" tone.