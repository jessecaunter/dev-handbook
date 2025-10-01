# JavaScript Code Readability Best Practices

## Numeric Separators for Large Numbers

### Problem

Large numeric literals are hard to read and prone to errors.

### Solution

Use underscores as numeric separators (ES2021 feature).

### Implementation

```javascript
// Hard to read
let myNumber = 1000000000000;

// Easy to read
let myNumber = 1_000_000_000_000;

// Works with any kind of numeric literal
let myHex = 0xa0_b0_c0;
```

### Benefits

- Improved readability without runtime cost
- Works with all numeric literal types

### Browser Support

- Firefox, Chrome, Edge
- Haven't tested in other browsers/environments

### References

- [Firefox 70 Release Notes](https://hacks.mozilla.org/2019/10/firefox-70-a-bountiful-release-for-all/)

---

_Configuration tested on Firefox 143.0.3 (64-bit), Chrome 140.0.7339.208 (Official Build) (64-bit), and Edge 140.0.3485.94 (Official build) (64-bit)_\
_Last updated: October 2025_
