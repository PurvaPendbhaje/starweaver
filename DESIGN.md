---
name: Cosmic Luminescence
colors:
  surface: '#0d1224'
  surface-dim: '#0d1224'
  surface-bright: '#34384c'
  surface-container-lowest: '#080d1f'
  surface-container-low: '#161b2d'
  surface-container: '#1a1f31'
  surface-container-high: '#24293c'
  surface-container-highest: '#2f3448'
  on-surface: '#dde1fb'
  on-surface-variant: '#b9cacb'
  inverse-surface: '#dde1fb'
  inverse-on-surface: '#2b3043'
  outline: '#849495'
  outline-variant: '#3a494b'
  surface-tint: '#00dce6'
  primary: '#e0fdff'
  on-primary: '#00373a'
  primary-container: '#00f2fe'
  on-primary-container: '#006a70'
  inverse-primary: '#00696f'
  secondary: '#ddb7ff'
  on-secondary: '#490080'
  secondary-container: '#6f00be'
  on-secondary-container: '#d6a9ff'
  tertiary: '#fff5f5'
  on-tertiary: '#670022'
  tertiary-container: '#ffcfd4'
  on-tertiary-container: '#b5254a'
  error: '#ffb4ab'
  on-error: '#690005'
  error-container: '#93000a'
  on-error-container: '#ffdad6'
  primary-fixed: '#6ff6ff'
  primary-fixed-dim: '#00dce6'
  on-primary-fixed: '#002022'
  on-primary-fixed-variant: '#004f53'
  secondary-fixed: '#f0dbff'
  secondary-fixed-dim: '#ddb7ff'
  on-secondary-fixed: '#2c0051'
  on-secondary-fixed-variant: '#6900b3'
  tertiary-fixed: '#ffd9dd'
  tertiary-fixed-dim: '#ffb2bb'
  on-tertiary-fixed: '#400012'
  on-tertiary-fixed-variant: '#910033'
  background: '#0d1224'
  on-background: '#dde1fb'
  surface-variant: '#2f3448'
  space-void: '#070913'
  surface-glass: '#121933'
  energy-cyan: '#00F2FE'
  energy-flow: '#4FACFE'
  nebula-violet: '#A855F7'
  starlight-coral: '#FF5E7E'
  celestial-node: '#FACC15'
  star-white: '#F8FAFC'
  stardust-muted: '#94A3B8'
typography:
  display-hero:
    fontFamily: Space Grotesk
    fontSize: 56px
    fontWeight: '700'
    lineHeight: 64px
    letterSpacing: -0.03em
  display-hero-mobile:
    fontFamily: Space Grotesk
    fontSize: 36px
    fontWeight: '700'
    lineHeight: 44px
    letterSpacing: -0.02em
  headline-xl:
    fontFamily: Space Grotesk
    fontSize: 32px
    fontWeight: '700'
    lineHeight: 40px
    letterSpacing: -0.02em
  headline-xl-mobile:
    fontFamily: Space Grotesk
    fontSize: 26px
    fontWeight: '700'
    lineHeight: 34px
    letterSpacing: -0.01em
  headline-md:
    fontFamily: Space Grotesk
    fontSize: 22px
    fontWeight: '600'
    lineHeight: 28px
  body-lg:
    fontFamily: Outfit
    fontSize: 18px
    fontWeight: '400'
    lineHeight: 28px
  body-md:
    fontFamily: Outfit
    fontSize: 16px
    fontWeight: '400'
    lineHeight: 24px
  body-sm:
    fontFamily: Outfit
    fontSize: 14px
    fontWeight: '400'
    lineHeight: 20px
  label-lg:
    fontFamily: Plus Jakarta Sans
    fontSize: 16px
    fontWeight: '600'
    lineHeight: 22px
    letterSpacing: 0.01em
  label-md:
    fontFamily: Plus Jakarta Sans
    fontSize: 13px
    fontWeight: '700'
    lineHeight: 18px
    letterSpacing: 0.04em
  label-counter:
    fontFamily: Space Grotesk
    fontSize: 20px
    fontWeight: '700'
    lineHeight: 24px
    letterSpacing: 0.02em
rounded:
  sm: 0.25rem
  DEFAULT: 0.5rem
  md: 0.75rem
  lg: 1rem
  xl: 1.5rem
  full: 9999px
spacing:
  gutter: 1rem
  gutter-mobile: 0.75rem
  margin: 2rem
  margin-mobile: 1rem
  space-xs: 0.25rem
  space-sm: 0.5rem
  space-md: 1rem
  space-lg: 1.5rem
  space-xl: 2.5rem
---

## Brand & Style

This design system expresses a vibrant, wonder-filled cosmic arcade experience. It blends deep astrophysical midnight backdrops with radiant, phosphorescent neon conduits and inviting celestial warmth. The emotional tone evokes playful discovery, curiosity, and high-satisfaction spatial problem-solving.

The visual style synthesizes **Glassmorphism** with **Tactile / Neon Arcade** aesthetics:
- **Depth & Atmosphere:** Multi-layered midnight-indigo planes layered with diffused nebula glows and ethereal, frosted-glass HUD modules.
- **Luminosity & Energy:** High-contrast electric conduits (cyan, turquoise, violet) that visually charge and pulse when circuits connect.
- **Friendly Tangibility:** Soft, rounded geometric forms, tactile interactive controls with subtle bottom-inset shadows, and playful micro-interactions that make tile rotation feel magnetic and satisfying.
- **Universal Clarity:** Uncompromising contrast ratios ensuring board tiles, celestial conduits, and progress metrics are instantly readable for casual players across all demographics.

## Colors

The palette relies on a pitch-black to midnight-indigo foundation, elevating chromatic energy conduits and luminous interactive states:

- **Primary (`#00F2FE` - Electric Cyan):** Active energy pathways, primary CTAs (e.g., "Launch Starway"), active node conduits, and high-intensity feedback pulses.
- **Secondary (`#A855F7` - Nebula Violet):** Dimensional portals, secondary interactive states, and cosmic atmospheric gradients.
- **Tertiary (`#FF5E7E` - Starlight Coral):** Dynamic goal points, energy sinks, alert/warning badges, and celebratory victory fireworks.
- **Neutral (`#0D1224` & `#070913`):** Atmospheric space void and base container surfaces.
- **Accent Gold (`#FACC15` - Celestial Node):** Stars, key collectible nodes, completion stars, and scoring metrics.

### State Rules
- **Tile Inactive/Unconnected:** Surface fill in `rgba(18, 25, 51, 0.7)` with conduit strokes in `rgba(148, 163, 184, 0.3)`.
- **Tile Active/Energized:** Conduit strokes transition to `#00F2FE` backed by a multi-stop gradient to `#4FACFE` with an outer soft glow of `rgba(0, 242, 254, 0.5)`.
- **Success / Goal State:** Portal rings glow in `#A855F7` pulsing outward to `#FF5E7E`.

## Typography

Typography balances futuristic precision with soft, approachable arcade warmth:

- **Space Grotesk (Headlines & Numerics):** Geometric tech-inspired letterforms add identity to game branding, level banners, score counters, and major celebration titles.
- **Outfit (Body & Descriptions):** Clean, geometric humanist curves that stay legible against dark, luminous backgrounds, ensuring zero reading strain on instructions.
- **Plus Jakarta Sans (HUD, Labels & Controls):** Sturdy, highly legible grotesque sans used for micro-labels, pill button text, tooltips, and directional hints.

All numbers in game HUDs (moves, timers, stars) should leverage tabular figures (`font-variant-numeric: tabular-nums`) to prevent jittering during active play.

## Layout & Spacing

The layout is built upon an adaptive container model tuned for arcade immersion:

- **Board Centering:** The puzzle grid anchors dead center of the viewport on both desktop and mobile viewports. Max board footprint stays clamped (`min(80vw, 540px)`).
- **Responsive Viewport Distribution:**
  - **Desktop (>= 1024px):** A three-tier column layout with top-anchored header HUD (level title, move counter, pause/audio), centered gameplay matrix, and bottom tactile dock (Hint, Undo, Restart).
  - **Tablet (768px - 1023px):** Fluid vertical flow with compact 1rem gutters and sticky floating top/bottom HUD bars.
  - **Mobile (< 768px):** Single-column layout. The puzzle board occupies maximum screen width with 16px lateral padding. Controls switch to an ergonomic thumbs-friendly bottom dock.
- **Rhythm:** Spacing between game action cards and HUD chips scales on a strict 8px/16px harmonic rhythm.

## Elevation & Depth

Visual hierarchy is crafted using **Glassmorphism and Luminous Ambient Glows** rather than generic drop shadows:

- **Level 0 (Cosmic Backdrop):** Deep radial gradients `#070913` with layered star particles and gentle CSS nebula blurs (`filter: blur(80px)`).
- **Level 1 (Surface Glass / Tiles & HUD Panels):** `background: rgba(18, 25, 51, 0.65)` layered with `backdrop-filter: blur(16px)` and a crisp 1px perimeter border (`rgba(255, 255, 255, 0.12)`).
- **Level 2 (Interactive Floating Controls):** `background: rgba(26, 36, 74, 0.85)` with top-edge highlight (`border-top: 1px solid rgba(255, 255, 255, 0.25)`) and bottom-shadow depth (`box-shadow: 0 4px 0 #070913, 0 8px 24px rgba(0, 0, 0, 0.4)`).
- **Level 3 (Energized Conduits & Modals):** Radiant multi-stop glow tokens:
  - Energy Pulse: `box-shadow: 0 0 20px rgba(0, 242, 254, 0.6), inset 0 0 12px rgba(79, 172, 254, 0.4)`
  - Portal Warp: `box-shadow: 0 0 32px rgba(168, 85, 247, 0.7)`
  - Victory Overlay: Glass backdrop blur (`backdrop-filter: blur(24px)`) over `#070913` at 80% opacity.

## Shapes

The design uses rounded geometry to create a tactile, non-intimidating toy-like feel:

- **Puzzle Tiles:** Medium rounded corners (`16px / 1rem`) with subtle inset bevels to emphasize individual rotating units.
- **HUD Badges & Quick Stats:** Full pill radius (`9999px`) to distinguish meta metrics (moves, stars) from interactive tiles.
- **Buttons & Control Docks:** `12px` to `16px` outer radius with interior padding that mirrors external curve proportions.
- **Modal Dialogs & Level Clear Panels:** Generous `24px / 1.5rem` (`rounded-xl`) curved containers to frame celebration graphics and score breakdowns.

## Components

### 1. Interactive Puzzle Path Tiles
- **Structure:** Square containers (`aspect-ratio: 1/1`) set within a CSS Grid layout.
- **Tile Base:** Frosted obsidian glass (`rgba(18, 25, 51, 0.75)`) with a rounded tactile bevel.
- **Rotation Interaction:** Smooth CSS transform `transform: rotate(Ndeg)` with spring-like timing (`cubic-bezier(0.34, 1.56, 0.64, 1)` at 260ms). Clicking causes a brief scale compression (`scale(0.94)`).
- **Conduit Lines:** 8px thick curved SVG paths. When dormant: muted slate (`#94A3B8`). When fully connected: vibrant electric cyan gradient with ambient light emission.

### 2. Arcade Action Buttons (Play, Next Level, Hint)
- **Primary Arcade CTA:** Electric cyan-to-turquoise gradient fill, white bold text, and a distinct 3D base bevel (`box-shadow: 0 5px 0 #0098a6, 0 12px 24px rgba(0, 242, 254, 0.35)`). On hover, brightness lifts 10%; on active/press, translate down 4px with bevel flattened to 1px.
- **Secondary Action (Undo / Restart / Audio):** Frosted glass pill button with subtle outline (`1px solid rgba(255, 255, 255, 0.15)`), centered icon, and tooltips for keyboard shortcuts (e.g., `[Z]`, `[R]`).

### 3. HUD Counters & Status Chips
- Pill-shaped HUD components positioned at top edge.
- Displays Level Number, Objective label, and Move Counter inside high-contrast translucent capsules (`rgba(7, 9, 19, 0.8)`).
- Move Counter flashes coral (`#FF5E7E`) briefly if a sub-optimal move cap is reached.

### 4. Level-Selection Nodes
- Hexagonal or circle nodes linked via glowing stardust constellations.
- **Unlocked:** Glowing cyan/violet node with star rating indicators (1-3 gold stars).
- **Locked:** Translucent slate with a miniature neon padlock icon and lowered opacity (0.4).

### 5. Mascot & Cosmic Companion
- Gentle floating ambient animation (`transform: translateY(-6px)` oscillating over 3s ease-in-out).
- Reactive expressions: neutral bobbing during puzzles, surprised wink on rotation, and ecstatic leap during level complete.

### 6. Success Modal & Celebration
- High-elevation glass card centered over board blur.
- Emits radial celebration fireworks in cyan, violet, and gold.
- Displays completed stats (Total Moves, Star Tier, Completion Time) and large primary button: "Enter Next Portal".