# Debugging Typography with Firefox DevTools Fonts Panel

## Diagnosing Font Rendering Issues

### Problem

Typography debugging is often guesswork: Why isn't my custom font loading? Which font in my stack is actually rendering? What variable font axis values work best? Developers waste time switching between code editor and browser, editing CSS blindly without knowing what values will work.

### Solution

Use Firefox DevTools Fonts panel to inspect applied fonts, test font properties in real-time, and explore variable font axes before committing to CSS.

### Implementation

#### Accessing the Fonts Panel:

1. Open Firefox DevTools (F12 or right-click → Inspect)
2. Select the element with text you want to debug
3. Click the **Fonts** tab in the right-hand panel

#### Key Features:

**1. Fonts Used (Top Section)**

Shows which fonts are actually applied to the inspected element:
- Displays font-family identifier and rendered font name
- Groups fonts by family
- Shows fonts from CSS declarations, browser defaults, and system fallbacks

**Practical use:**
- Verify your @font-face loaded correctly (shows actual rendered name)
- Identify which font in your font-family stack is active
- Detect unexpected fallback fonts

**2. Font Editor (Middle Section)**

Live controls for testing typography values:
- **Size:** Adjust with slider or input (supports px, rem, em, %, vh, vw)
- **Line height:** Test ratios for readability (unitless, em, %, px)
- **Weight:** Slide through available weights (100-900 for standard fonts)
- **Italic:** Toggle italic/normal instantly

Changes apply inline styles immediately - see results live on the page.

**Practical use:**
- Find optimal line-height for different font sizes
- Test font-weight values before hardcoding (especially useful for variable fonts)
- Experiment with size/weight/line-height combinations

**3. All Fonts on Page (Bottom Section)**

Inventory of every font used in the document:
- Lists font-family and full font name
- Shows font source: URL for web fonts or "System" for local fonts
- Displays @font-face descriptor (expandable to see full syntax)
- Live preview with customizable sample text

**Practical use:**
- Copy font URLs quickly (click icon next to URL)
- Verify @font-face declarations loaded correctly
- Preview fonts with custom text before applying

#### Variable Fonts Support:

For variable fonts, the Font Editor expands with additional controls:

**Instance Presets:**
- Dropdown shows predefined variations (if font designer included them)
- Example: "Hi Yeast Hi Gravity" instance in Cheee Variable font

**Custom Axes:**
- Sliders for each variation axis the font defines
- Registered axes: Weight (wght), Width (wdth), Optical Size (opsz), Slant (slnt), Italic (ital)
- Custom axes: Font designer can add any axes (Yeast, Gravity, etc.)

**Practical use:**
- Discover what axes a variable font supports (they vary dramatically)
- Test axis ranges before writing font-variation-settings
- Find optimal values for responsive typography

#### Bonus Tips:

**See which font in your stack is active:**
- Hover over `font-family` property in Rules view
- Tooltip shows font preview
- Actually applied font is underlined in the stack

**Three-pane workflow:**
- Use Page Inspector's 3-pane mode
- View CSS rules + Fonts panel simultaneously
- Edit CSS rules while testing font values live

### Benefits

- **Faster debugging** - instantly see which fonts loaded and which are rendering
- **Confident decisions** - test values before committing to CSS
- **Variable font exploration** - discover available axes and ranges without documentation
- **Learning tool** - understand font fallback behavior and @font-face mechanics

### Browser Support

**Fonts Panel:** Firefox DevTools only

Chrome and Edge have basic font inspection but lack the comprehensive editing capabilities shown here.

### References

- [Firefox DevTools: Edit Fonts](https://firefox-source-docs.mozilla.org/devtools-user/page_inspector/how_to/edit_fonts/)

---

_Tested on Firefox 147.0 (64-bit)_\
_Last updated: January 2026_
