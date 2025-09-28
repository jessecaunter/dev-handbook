# Browser Privacy Protection

Essential browser configuration to improve page load performance and reduce tracking across websites.

## What This Protects Against

**Performance Impact:** Tracking scripts significantly slow down page loads - Firefox testing showed 50% improvement with protection enabled.

**Cross-Site Tracking:** Third-party scripts collect browsing data across multiple websites to build profiles and display targeted advertisements.

## Solution: Enable Built-in Browser Privacy Protection

Both major browsers now include tracking protection features that block or limit third-party tracking scripts while maintaining site functionality.

## Firefox Enhanced Tracking Protection (Recommended)

1. Open Firefox Settings → Privacy & Security
2. Navigate to "Enhanced Tracking Protection" section
3. Select **"Strict"** for maximum protection

### Why Strict Mode?

- Blocks tracking content in all windows (not just private browsing)
- Blocks all cross-site (third-party) cookies
- Equivalent to Firefox's original "Always" setting that delivered 50% page load improvements
- May cause some sites to break, but provides maximum protection

## Chrome Third-Party Cookie Controls (Alternative)

1. Open Chrome Settings → Privacy and security → Third-party cookies
2. Select **"Block third-party cookies"**
3. Optional: Disable "Allow related sites to see your activity in the group"

### Advanced Chrome Option

Under "Advanced" settings, enable **"Send a 'Do Not Track' request"** - though sites use their discretion in responding to this request.

## Browser Protection Comparison

### Firefox Enhanced Tracking Protection (Standard/Strict)

- Social media trackers ✓
- Cross-site cookies in all windows ✓
- Tracking content (Strict: all windows, Standard: private only) ✓
- Cryptominers ✓
- Known and suspected fingerprinters ✓
- Total Cookie Protection (cookies isolated per site) ✓

### Chrome Third-Party Cookie Controls

- Third-party cookies ✓
- Related site activity groups (optional) ✓
- Do Not Track requests (optional) ✓
- Social media trackers ✗
- Cryptominers ✗
- Fingerprinters ✗

**Key Difference:** Firefox provides comprehensive tracking protection across multiple techniques, while Chrome focuses primarily on cookie-based tracking.

## Developer Implications

Firefox offers privacy protection by default with Enhanced Tracking Protection, while Chrome requires manual configuration but provides similar controls. **Developers should assume tracking scripts may be blocked** for significant portions of users. Testing with strict privacy settings enabled helps ensure applications work reliably across different user configurations while potentially revealing performance optimisation opportunities.

## What This Doesn't Fix

**First-Party Tracking:** Scripts loaded directly from the website you're visiting are generally not blocked, though Firefox may limit some cross-site tracking capabilities even through first-party cookies.

## References

Based on [Firefox's 2018 tracking protection performance research][Tracking Protection] and current browser privacy implementation standards.

[Tracking Protection]: https://blog.mozilla.org/en/firefox/tracking-protection-always-on/

---

_Configuration tested on Chrome 140.0.7339.208 (Official Build) (64-bit) and Firefox 143.0.1 (64-bit)_\
_Last updated: September 2025_
