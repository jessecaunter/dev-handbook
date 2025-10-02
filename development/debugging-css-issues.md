# Debugging CSS Issues

## Identifying Inactive CSS Rules

### Problem

CSS properties sometimes have no effect on elements, and it's not always obvious why. Developers waste time troubleshooting valid CSS that won't work due to context (e.g., trying to use `flex` properties on non-flex items).

### Solution

Use browser DevTools to identify inactive CSS rules and understand why they're not applying.

### Implementation

#### Using Browser DevTools:

1. Inspect the element with inactive CSS
2. Look for grayed-out/dimmed properties with an information icon (ℹ️)
3. Hover over or click the icon to see why the CSS isn't applying

#### Common inactive CSS scenarios:

- Applying `grid-auto-columns` to a non-grid container
- Using `flex` properties on elements whose parent isn't `display: flex`

#### Tracking your fixes (Firefox only):

- Use the Changes panel to see all CSS modifications
- Copy fixes from Changes panel into your codebase
- Ensures you don't lose debugging work

### Benefits

- Faster debugging - immediate feedback on why CSS isn't working
- Learn CSS rules - explanations help understand CSS behavior

### Browser Support

**Inactive CSS indicators:** Firefox, Chrome, Edge

**Changes panel (tracking modifications):** Firefox only

Haven't tested in other browsers

### References

- [Firefox 70 Release Notes](https://hacks.mozilla.org/2019/10/firefox-70-a-bountiful-release-for-all/)

---

_Configuration tested on Firefox 143.0.3 (64-bit), Chrome 141.0.7390.55 (Official Build) (64-bit), and Edge 140.0.3485.94 (Official build) (64-bit)_\
_Last updated: October 2025_
