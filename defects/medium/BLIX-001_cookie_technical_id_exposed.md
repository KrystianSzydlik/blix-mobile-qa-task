# Bug Report: BLIX-001

## Summary

**Title:** Cookie Settings - Technical cookie identifier "\_cmpconsentx105796" exposed to end users  
**Severity:** Medium  
**Priority:** P2

## Environment

- **Device:** Samsung Galaxy S21 FE 5G (SM-G990B2/DS)
- **OS:** Android 13 (One UI 5.1)
- **App Version:** Blix Test APK
- **Network State:** WiFi
- **Session Reference:** Test session timestamp 02:40

## Reproduction

### Steps to Reproduce

1. Install and launch the Blix application
2. Tap "Dostosuj" on the initial privacy consent dialog
3. Observe the data management section under cookie settings
4. Note the technical cookie identifier displayed in the text

### Expected Behavior

The cookie storage mechanism should be described using user-friendly terminology without exposing internal technical identifiers (e.g., "Your preferences will be stored securely for 365 days").

### Actual Behavior

The raw technical cookie identifier "\_cmpconsentx105796" is directly exposed to the end user in the data management information text, creating a confusing and unprofessional user experience.

## Evidence & Analysis

### Visual Evidence

![Cookie Settings Technical Identifier](/evidence/screenshots/cookie_settings_technical_id.jpg)

> **Video Reference:** Session recording [02:40-03:10]

### Technical Impact Assessment

1. **User Experience Issue:** Technical implementation details should remain invisible to end users
2. **Professional Appearance:** Exposes implementation details that undermine application credibility
3. **Potential Security Concern:** Reveals information about the underlying consent management platform implementation
4. **Compliance Risk:** Potentially violates GDPR Article 12 requirement for "clear and plain language" in privacy communications
5. **Localization Issue:** Technical identifiers create translation inconsistencies across languages

### Root Cause Analysis

The issue likely stems from either:

- Missing string resource localization for cookie description
- Direct usage of API variable names in UI text without proper abstraction
- Incomplete implementation of the CMP integration
- Debug information accidentally left in production build

## Recommended Resolution

Replace the technical identifier with user-friendly language that explains the purpose of the cookie storage in plain language appropriate for the target audience.

## Additional Notes

This issue appears consistently across the cookie management interface. The technical implementation details should be abstracted away from the user interface entirely, not just for this specific instance.
