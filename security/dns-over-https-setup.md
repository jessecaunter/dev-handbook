# DNS over HTTPS (DoH) Setup

Essential browser security configuration to protect against DNS tracking and spoofing attacks.

## What This Protects Against

**DNS Tracking:** ISPs, coffee shop networks, and malicious actors can see every website you visit through DNS requests, even when browsing HTTPS sites.

**DNS Spoofing:** Attackers can redirect you to fake websites by providing false IP addresses for legitimate domains.

## Solution: DNS over HTTPS + Trusted Recursive Resolver

1. **DNS over HTTPS (DoH) -** Encrypts DNS queries to prevent eavesdropping
2. **Trusted Recursive Resolver -** Uses a privacy-focused DNS provider instead of potentially untrustworthy network defaults

### Recommended DNS Provider: Cloudflare (1.1.1.1)

- Commits to deleting personally identifiable data after 24 hours
- No third-party data sharing
- Regular privacy audits
- Same provider Mozilla partnered with for Firefox

## Firefox Setup (Recommended)

1. Open Firefox Settings → Privacy & Security
2. Scroll to "DNS over HTTPS"
3. Enable "Max Protection"
4. Provider should default to Cloudflare

## Chrome Setup (Alternative)

1. Open Chrome Settings → Privacy and Security → Security
2. Scroll to "Advanced" section
3. Enable "Use secure DNS"
4. Choose "Cloudflare (1.1.1.1)" from the "Select DNS provider" dropdown

## Verification

Test your setup at: <https://1.1.1.1/help>

- Should show "Connected to 1.1.1.1: Yes"
- Should show "Using DNS over HTTPS (DoH): Yes"

## What This Doesn't Fix

**Server Name Indication (SNI):** Your ISP can still see initial connections to websites through unencrypted SNI headers. This limitation affects all DNS configurations.

**IP Address Visibility:** Direct IP connections are still visible to ISPs and network operators.

## References

Based on Mozilla's "DNS over HTTPS" implementation and security research. For technical details, see Mozilla's [DNS-over-HTTPS documentation](https://support.mozilla.org/en-US/kb/firefox-dns-over-https "Firefox DNS over HTTPS").

---

_Configuration tested on Chrome 140.0.7339.185 (Official Build) (64-bit) and Firefox 143.0.1 (64-bit)_\
_Last updated: September 2025_
