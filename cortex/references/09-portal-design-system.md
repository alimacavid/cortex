# 09 - Cortex Portal Design System

## Golden Rules
1. Light mode ONLY (white/light gray background)
2. Livo colors + gray palette
3. Admin panel / command center feel (not a website, a control center)
4. No Tailwind - pure CSS only
5. Single HTML file - no build step
6. PRIVATE badge always visible in sidebar

## Typography
UI Body: Plus Jakarta Sans (400, 500, 600)
Headings: Syne (600, 700)
Serif accent: Instrument Serif (400)
Code/Mono: JetBrains Mono (400, 500)
Load via Google Fonts.

## Color Palette
Primary: Livo brand green
Background: #F8F9FA (light gray - not pure white)
Cards: #FFFFFF / #F1F3F5 (gray tint)
Text: #111 primary, #555 secondary, #999 muted
Border: #DEE2E6 / #CED4DA
Palette: Livo colors + structured gray system. Admin panel feel.

## Layout
Sidebar: Fixed left, 220px
Sidebar sections: Workspace (Dashboard, Ideas, Roadmap) + each business
Main content: Scrollable right panel
Cards: White with subtle border, rounded corners

## Do NOT
- Use dark mode or dark backgrounds
- Use orange (Ascentra color)
- Use Tailwind or any CSS framework
- Use React or any JS framework (vanilla only)
- Break single-file architecture
- Put Cortex files in the livo app folder
