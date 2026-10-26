---
name: Kinetic Obsidian
colors:
  surface: '#111317'
  surface-dim: '#111317'
  surface-bright: '#37393e'
  surface-container-lowest: '#0c0e12'
  surface-container-low: '#1a1c20'
  surface-container: '#1e2024'
  surface-container-high: '#282a2e'
  surface-container-highest: '#333539'
  on-surface: '#e2e2e8'
  on-surface-variant: '#e4bfb1'
  inverse-surface: '#e2e2e8'
  inverse-on-surface: '#2f3035'
  outline: '#ab897d'
  outline-variant: '#5b4137'
  surface-tint: '#ffb599'
  primary: '#ffb599'
  on-primary: '#5a1c00'
  primary-container: '#ff5e00'
  on-primary-container: '#531900'
  inverse-primary: '#a63b00'
  secondary: '#d3fbff'
  on-secondary: '#00363a'
  secondary-container: '#00eefc'
  on-secondary-container: '#00686f'
  tertiary: '#ffba20'
  on-tertiary: '#412d00'
  tertiary-container: '#c08a00'
  on-tertiary-container: '#3c2900'
  error: '#ffb4ab'
  on-error: '#690005'
  error-container: '#93000a'
  on-error-container: '#ffdad6'
  primary-fixed: '#ffdbce'
  primary-fixed-dim: '#ffb599'
  on-primary-fixed: '#370e00'
  on-primary-fixed-variant: '#7f2b00'
  secondary-fixed: '#7df4ff'
  secondary-fixed-dim: '#00dbe9'
  on-secondary-fixed: '#002022'
  on-secondary-fixed-variant: '#004f54'
  tertiary-fixed: '#ffdea8'
  tertiary-fixed-dim: '#ffba20'
  on-tertiary-fixed: '#271900'
  on-tertiary-fixed-variant: '#5e4200'
  background: '#111317'
  on-background: '#e2e2e8'
  surface-variant: '#333539'
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
  headline-lg:
    fontFamily: Space Grotesk
    fontSize: 32px
    fontWeight: '700'
    lineHeight: 40px
    letterSpacing: -0.02em
  headline-lg-mobile:
    fontFamily: Space Grotesk
    fontSize: 24px
    fontWeight: '700'
    lineHeight: 32px
    letterSpacing: -0.01em
  headline-md:
    fontFamily: Space Grotesk
    fontSize: 22px
    fontWeight: '600'
    lineHeight: 28px
    letterSpacing: -0.01em
  headline-sm:
    fontFamily: Space Grotesk
    fontSize: 18px
    fontWeight: '600'
    lineHeight: 24px
    letterSpacing: 0em
  body-lg:
    fontFamily: Space Grotesk
    fontSize: 16px
    fontWeight: '400'
    lineHeight: 24px
    letterSpacing: 0em
  body-md:
    fontFamily: Space Grotesk
    fontSize: 14px
    fontWeight: '400'
    lineHeight: 20px
    letterSpacing: 0.005em
  body-sm:
    fontFamily: Space Grotesk
    fontSize: 12px
    fontWeight: '400'
    lineHeight: 16px
    letterSpacing: 0.01em
  telemetry-counter:
    fontFamily: Space Mono
    fontSize: 24px
    fontWeight: '700'
    lineHeight: 28px
    letterSpacing: -0.02em
  label-caps:
    fontFamily: Space Mono
    fontSize: 11px
    fontWeight: '700'
    lineHeight: 14px
    letterSpacing: 0.12em
  label-code:
    fontFamily: Space Mono
    fontSize: 12px
    fontWeight: '400'
    lineHeight: 16px
    letterSpacing: 0.02em
spacing:
  gutter: 1rem
  gutter-desktop: 1.5rem
  margin: 1rem
  margin-tablet: 1.5rem
  margin-desktop: 2.5rem
  space-xs: 0.25rem
  space-sm: 0.5rem
  space-md: 1rem
  space-lg: 1.5rem
  space-xl: 2.5rem
---

## Brand & Style

This design system targets competitive esports tournament organizers, production crews, broadcast directors, and elite players. The aesthetic communicates ruthless precision, high-velocity data throughput, and arena-grade intensity.

The visual direction merges **High-Contrast Tactical Futurism** with **Modern Kinetic Energy**:
- **Foundations:** Deep, light-absorbing volcanic slates and matte obsidians that create infinite depth without wash-out.
- **Accents:** High-voltage energy signatures—molten thermite ambers transitioning to razor-sharp electric cyans—signaling live states, critical events, and match telemetry.
- **Geometry:** 45-degree chamfered geometry, clipped telemetry corners, razor borders, and ultra-dense data arrays reminiscent of military glass cockpits and performance sports telemetry.
- **Texture:** Semi-translucent carbon-tinted composites, subtle grid reticles, and fine edge-glows that trace perimeter boundaries without standard rounded softening.

## Colors

The palette establishes a high-contrast battle ground where dark tones stay cold and neutral, while energetic tokens operate under functional severity.

### Palette Architecture
- **Primary (`#ff5e00`):** Molten kinetic amber. Denotes live active matches, kill-feed actions, primary CTAs, destructive decisions, and critical telemetry anomalies.
- **Secondary (`#00f0ff`):** Electric ice-blue strike. Denotes network telemetry, tactical shields, real-time sync states, verified status badges, and secondary analytics.
- **Tertiary (`#ffb800`):** Core radiant amber. Serves as warning states, match countdowns, tournament seeds, and trophy milestones.
- **Neutral Foundations:**
  - `obsidian-950` (`#07080b`): Canvas void and broadcast letterboxing.
  - `obsidian-900` (`#0b0d11`): Base application viewport and root frame.
  - `obsidian-800` (`#12151c`): Surface containers, stage card foundations, and panel groupings.
  - `obsidian-700` (`#1a1e27`): Elevated surfaces, hovering tactical rails, and modal canvases.
  - `obsidian-600` (`#242a36`): Structural borders, grid dividers, and inactive slots.
  - `obsidian-100` (`#d5dde8`): High-legibility telemetry readouts and headline values.
  - `obsidian-400` (`#6b798e`): De-emphasized labels, bracket connectors, and timestamps.

### Semantic Rules
- Never use pure black (`#000000`) for surfaces; retain the cold mineral cast of `#0b0d11`.
- Gradients must be linear and directional (predominantly 135deg), transitioning sharply from `#ff5e00` to `#ff8800` for kinetic active states.
- Ambient borders must maintain a strict 1px boundary width using `#242a36` in rested states and `#00f0ff` or `#ff5e00` at 60% opacity for focused/live states.

## Typography

Typography functions as a structural grid element rather than passive prose. 

### Typographic Hierarchy
- **Primary Voice (`Space Grotesk`):** Chosen for its aggressive technical cuts, geometric terminals, and mechanical posture. Used across all titles, match headers, and interaction nodes.
- **Tactical Telemetry (`Space Mono`):** Dedicated to critical data readout: scorelines, round clocks, ping rates, seed indices, and uppercase system labels.

### Usage Directives
- **All-Caps Telemetry:** Labels below 14px must use `Space Mono` with uppercase casing and expanded letter-spacing (`0.12em`) to ensure legibility across dense dashboard configurations and broadcast displays.
- **Tabular Figures:** Monospace metrics apply strictly to all changing match statistics, team KDAs, timers, and tournament payouts to avoid baseline jitter during active streaming.

## Layout & Spacing

The layout is engineered around high-density operational workspaces and structural bracket visualization.

### Grid & Density
- **Desktop (>= 1280px):** 12-column fluid grid with `gutter-desktop` (1.5rem) and `margin-desktop` (2.5rem). Tournament views support multi-pane cockpit configurations: side bracket tree (3 cols), stage detail/telemetry engine (6 cols), and real-time incident/veto logs (3 cols).
- **Tablet (768px - 1279px):** 8-column layout with 1.5rem margins and 1rem gutters. Side modules collapse into slide-out HUD drawers.
- **Mobile (< 768px):** 4-column layout with 1rem margins and gutters. Telemetry streams stack vertically with horizontal-swipe match brackets.

### Alignment Rhythms
- Layout utilizes strict 4px/8px incremental spacing steps.
- Margins and paddings prioritize immediate structural compactness (`space-xs` and `space-sm`) inside components to maintain maximal visible data without scroll latency.

## Elevation & Depth

Depth is defined through physical materiality and luminescence rather than natural shadow casting. The environment mimics a darkened stage with backlit tactical instruments.

### Material Stacks & Tiers
- **Tier 0 (Backdrop Void):** Base obsidian (`#07080b`) covered with an ultra-faint 24px micro-grid pattern in `#12151c` at 40% opacity.
- **Tier 1 (Tactical Frame):** Solid `#0b0d11` panels bordered by 1px solid `#1a1e27`.
- **Tier 2 (Interactive Modules):** Translucent carbon surfaces (`rgba(18, 21, 28, 0.85)`) supported by `backdrop-filter: blur(12px)` and a 1px top-highlight line (`rgba(255, 255, 255, 0.08)`).
- **Tier 3 (Active Hover / Elevated Sheets):** Solid `#1a1e27` with razor-thin structural borders (`#242a36`).

### Glowing Edge & Kinetic Telemetry
- Avoid diffuse, cloudy shadows.
- Active states deploy directed edge-glows using hard-line inner borders combined with tight outer radiance:
  - **Live State Glow:** `box-shadow: 0 0 0 1px #ff5e00, 0 0 16px -2px rgba(255, 94, 0, 0.45);`
  - **Tactical Focus Glow:** `box-shadow: 0 0 0 1px #00f0ff, 0 0 16px -2px rgba(0, 240, 255, 0.4);`

## Shapes

The design system is strictly sharp-edged (`0px` roundedness). It rejects soft, consumer-grade curved surfaces in favor of mechanical precision.

### Geometric Principles
- **Absolute Razor Corners:** All corners are standard 90-degree orthogonal joints or explicit 45-degree angle cuts (chamfers).
- **Chamfer Accents:** Primary buttons, bracket headers, and live match cards employ dynamic cut-corners via CSS clip-path: `polygon(0 0, calc(100% - 10px) 0, 100% 10px, 100% 100%, 0 100%)`.
- **Structural Framing:** Panels may use corner brackets—miniature 4px L-shaped tick marks rendered at outer edges to frame critical tournament information.

## Components

### Buttons
- **Primary Kinetic:** Background is gradient `linear-gradient(135deg, #ff5e00, #ff8800)`. Text is `#07080b` with `Space Grotesk` Bold uppercase. Sharp corners with top-right 8px chamfer. Hover state triggers a saturated molten glow (`0 0 20px rgba(255, 94, 0, 0.6)`).
- **Tactical Secondary:** Background is `rgba(0, 240, 255, 0.06)`, border is 1px solid `#00f0ff`, text is `#00f0ff`. Hover converts the background to solid `#00f0ff` with `#0b0d11` text.
- **Ghost Obsidian:** Background is transparent, 1px border in `#242a36`, text in `#d5dde8`. Hover border shifts to `#ff5e00` with text color shift.

### Chips & Match Badges
- **Status Tags:** Height 22px, `Space Mono` 11px uppercase. 0px border radius.
- **LIVE Chip:** Solid `#ff5e00` background with pulsating `#0b0d11` text and an animated kinetic dot.
- **Scheduled Chip:** `#12151c` background, 1px border `#242a36`, `#6b798e` text.
- **Map Pick/Ban Chips:** Neutral dark background with electric cyan strike border indicating chosen side (Attack/Defense).

### Bracket Nodes & Match Cards
- Dual-tier team slots housed within an `#12151c` slab. 1px perimeter border in `#1a1e27`.
- Winner seed indicators highlighted with a 2px vertical neon stripe on the extreme left border.
- Score counters displayed in `Space Mono` 14px bold within dedicated `#0b0d11` embedded blocks.
- Active live match node displays perimeter border in `#ff5e00` with telemetry pulse.

### Inputs & Search Fields
- Monolithic surface in `#0b0d11`. 1px border in `#242a36`.
- Typography is `Space Grotesk` 14px for user input, placeholder in `#6b798e`.
- Focus state instantly replaces border with 1px solid `#00f0ff` accompanied by a 4px ice-blue lateral inset accent line on the left edge.

### Checkboxes & Radios
- Sharp 14px square housings with 1px border `#242a36`.
- Checked state fills center with a sharp 8px diamond or square in `#ff5e00`.
- Radio selectors use a sharp diamond outline (rotated 45deg) rather than a circular ring.

### Tactical Telemetry HUD (Custom Component)
- Real-time tournament stat banners combining server ticks, latency ping, spectator headcount, and stream health.
- Monospace labels with color-keyed status pings: Green/Cyan (<30ms), Amber (30-80ms), Molten Orange (>80ms/incident).