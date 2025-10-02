# Keyboard Accessibility Testing

## Problem Statement

Many interactive elements on websites are not accessible via keyboard, creating barriers for users who cannot use a mouse or prefer keyboard navigation.

## Best Practice

Test your web applications for keyboard accessibility issues to ensure all interactive elements are accessible to keyboard-only users and meet WCAG guidelines.

## Testing Method

### Using Firefox DevTools Accessibility Inspector

1. Open Firefox DevTools (F12 or right-click → Inspect)
2. Navigate to the Accessibility tab
3. Click the Check for issues dropdown
4. Select keyboard from the options
5. Firefox will highlight all nodes with keyboard accessibility issues
6. Hover over or click each highlighted node to see:
   - Description of the issue
   - "Learn more" link for guidance on fixing it

## Benefits

- Ensures applications are usable by keyboard-only users
- Helps meet WCAG compliance requirements
- Improves overall accessibility and user experience

## Browser Support

- **Firefox:** Dedicated keyboard accessibility checker (as described above)
- **Chrome/Edge:** Lighthouse for general accessibility audits, but no dedicated keyboard-specific checker

## References

- [Firefox 70 Release Notes](https://hacks.mozilla.org/2019/10/firefox-70-a-bountiful-release-for-all/)

---

_Configuration tested on Firefox 143.0.3 (64-bit), Chrome 141.0.7390.55 (Official Build) (64-bit), and Edge 140.0.3485.94 (Official build) (64-bit)_\
_Last updated: October 2025_
