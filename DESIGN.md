```markdown
# Design System Strategy: The Guardian Protocol

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Terminal Bastion."** 

This system rejects the soft, approachable aesthetics of consumer software in favor of military-grade authority and technical precision. We are building for "The Guardian"—a persona that is secure, vigilant, and uncompromising. To achieve this, the design breaks from standard "web" templates by utilizing a high-density, instrumentation-heavy layout. 

While the typography remains rigid and monospace, the visual depth is achieved through sophisticated glassmorphism and tonal layering. We avoid the "flat" look by treating the UI as a series of heads-up display (HUD) layers, where information isn't just displayed—it is monitored.

## 2. Colors & Surface Architecture
The palette is rooted in the "Citadel Sentinel" environment: a deep, nocturnal base punctuated by **Tactical Amber (#FFB000)**. This primary accent is reserved for high-priority data and critical interaction points.

### The "No-Line" Rule
Standard UI relies on borders to separate content. This design system prohibits the use of 1px solid borders for sectioning. Boundaries must be defined solely through background color shifts or subtle tonal transitions. For example, a `surface-container-low` section should sit directly against a `background` or `surface` area, creating a "seam" through color value alone.

### Surface Hierarchy & Nesting
Depth is built through "stacking" the surface tiers. Instead of a flat grid, treat the UI as physical layers of glass:
- **Base Layer:** `surface` (#131313)
- **Primary Workspaces:** `surface-container-low` (#1C1B1B)
- **Active Modules:** `surface-container-high` (#2A2A2A)
- **Floating Overlays:** `surface-container-highest` (#353534)

### The "Glass & Gradient" Rule
90% of the UI should feel translucent. Use semi-transparent variants of the surface colors paired with heavy `backdrop-blur` (20px–40px). To provide visual "soul," use subtle linear gradients for CTAs, transitioning from `primary` (#FFD597) to `primary-container` (#FFB000). This mimics the glow of a high-end phosphorescent display.

## 3. Typography: Technical Rigidity
The typography is the backbone of the "Guardian" personality. We use **JetBrains Mono** exclusively to maintain a developer-centric, engineered feel.

- **Display & Headline:** Used for high-level data visualization and status headers. These should feel like a command-line interface, commanding authority.
- **Body & Titles:** Information density is high. Use `body-sm` (0.75rem) for secondary telemetry and `body-md` (0.875rem) for standard logs.
- **Labels:** Always capitalized when used for data keys (e.g., STATUS: OPERATIONAL) to reinforce the military-grade aesthetic.

The contrast between the rigid, fixed-width characters and the fluid glass surfaces creates a sophisticated, bespoke tension that "off-the-shelf" systems cannot replicate.

## 4. Elevation & Depth
In a world without lines, depth is our only organizational tool.

### The Layering Principle
Achieve "lift" by nesting. Place a `surface-container-lowest` card inside a `surface-container-low` section. This creates a "recessed" or "cut-out" effect, suggesting the UI is carved out of a singular piece of hardware.

### Ambient Shadows
Shadows are rarely used, but when floating elements (like modals) are required, use "Long-Range Ambient Shadows." These must be extra-diffused (60px-80px blur) at extremely low opacity (4%-8%). The shadow color should be a tinted version of `on-surface` (#E5E2E1), mimicking light refracting through glass rather than a generic black shadow.

### The "Ghost Border" Fallback
If a visual separator is mandatory for accessibility, use a **Ghost Border**. This is a 1px stroke using the `outline-variant` (#524533) at 15% opacity. It should feel like a faint laser-etching, not a structural line.

## 5. Components & Atomic Configuration

### Hard-Edge Geometry
Following the `0px` roundedness scale, every component—from buttons to cards—must have **0px corner radius**. Sharp edges communicate precision, risk, and a lack of compromise.

### Buttons (Tactical Trigger)
- **Primary:** Background `primary-container` (#FFB000), text `on-primary-fixed` (#281800). No border. On hover, add a subtle outer glow using the primary color.
- **Secondary:** Transparent background, `ghost-border` (15% opacity), text `primary`. 
- **Tertiary/Ghost:** Text `on-surface-variant`, no background.

### Tactical Chips
Small, high-density indicators. Use `surface-container-highest` with `label-sm` text. Chips should feel like metadata tags in a code editor.

### Input Fields (Data Entry)
Inputs are "recessed" boxes using `surface-container-lowest`. The label (JetBrains Mono) sits above the field in `on-surface-variant`. The active state is indicated by a bottom-aligned 2px bar in `Tactical Amber`.

### Cards & Lists
Prohibit divider lines. Separate list items using a 4px or 8px vertical gap or by alternating background tints (`surface-container-low` vs `surface-container-high`). This maintains a clean, high-density technical "stack."

### Additional Component: The "Status Bar"
A persistent, high-density strip at the top or bottom of the screen using `surface-container-lowest`. It should contain real-time telemetry (CPU, Latency, Auth Level) in `label-sm`, acting as the "heartbeat" of the Guardian environment.

## 6. Do's and Don'ts

- **DO** use asymmetry. Shift your columns and modules intentionally to avoid a "template" feel.
- **DO** use `Tactical Amber` sparingly. If everything is amber, nothing is important. 
- **DO** lean into high-density grids. Information is power; don't be afraid of "busy" technical layouts as long as the hierarchy is clear.
- **DON'T** use rounded corners. Even a 2px radius destroys the "Citadel" rigidity.
- **DON'T** use 100% opaque borders. They clutter the technical precision of the glass layers.
- **DON'T** use standard "drop shadows." They feel like 2010s web design, not a 2024 tactical interface.