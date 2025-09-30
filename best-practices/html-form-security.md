# HTML Form Security Best Practices

## Password Fields for New Credentials

### Problem

Password managers and browsers need clear signals to know when to generate/suggest new passwords vs. autofill existing ones.

### Solution

Use `autocomplete="new-password"` on password fields for registration and password change forms.

### Implementation

```html
<!-- For new password registration/change forms -->
<input type="password" autocomplete="new-password" />
```

### Benefits

- Triggers secure password generation in browsers
- Better UX for users with password managers
- Clear semantic meaning for assistive technologies

### Browser Support

- Firefox, Chrome, Edge
- Haven't tested in other browsers

### References

- [Firefox 70 Release Notes](https://hacks.mozilla.org/2019/10/firefox-70-a-bountiful-release-for-all/)

---

_Configuration tested on Firefox 143.0.1 (64-bit), Chrome 140.0.7339.208 (Official Build) (64-bit), and Edge 140.0.3485.94 (Official build) (64-bit)_\
_Last updated: September 2025_
