# Phishing-Detection-Tool
Software Engineering Fundamentals project – Umm Al-Qura University, College of Computing (Group 20, Dr. Foziah Hasan Gazzawe).
A web-based tool that checks whether a URL looks safe or suspicious using predefined rule-based checks.

## Features

- Enter any URL and click **Analyze Now**
- Rule-based checks: excessive length, special characters, IP-based addresses
- Clear result: green **Status: Safe** or red **Warning: Suspicious Link**
- No URLs or personal data are stored

**Out of scope:** AI/ML detection, browser extension, mobile app, external threat-intelligence feeds.

## Architecture (Layered)

1. Presentation Layer – web interface
2. Business Logic Layer – detection rules and decisions
3. Persistence Layer – temporary data flow (nothing stored permanently)
4. Database Layer – detection rules and criteria

Classes: `phishingUI` (captureURL, displayResult) → uses → `DetectionEngine` (analyzeURL, validateRules).

## Requirements

- **Functional:** analyze URL → output `DetectionStatus` and `AlertMessage`; input must be non-empty.
- **Non-functional:** easy to use, fast, consistent results, privacy-preserving, clean UI.

## Testing

| ID | Scenario | Result |
|---|---|---|
| TC01 | `http://192.168.1.1/login?secure=false&redirect=paypal.com` shows warning | Pass |
| TC02 | `https://www.google.com` shows Safe | Pass |
| B01 | Empty input is not rejected (no validation message) | **Open bug** |

## Timeline

5 weeks: Planning → Design → Development 1 → Development 2 → Testing & finalizing.

## References

OWASP – Phishing; IBM – What is phishing?; NIST – Cybersecurity Framework.
