# Bug Report: BLIX-012

## Summary

**Title:** Location - Location data not updated  
**Severity:** Medium  
**Priority:** P2

## Environment

- **Device:** Samsung Galaxy S21 FE 5G (SM-G990B2/DS)
- **OS:** Android 13 (One UI 5.1)
- **App Version:** Blix Test APK
- **Network State:** WiFi
- **GPS State:** Tested with both enabled and disabled GPS
- **Session Reference:** Test sessions timestamp 12:00-13:25 (Charter2 Recording 2)

## Reproduction

### Steps to Reproduce

1. Go to location settings in the application
2. Manually enter a new location
3. Confirm the location change
4. Return to the main application screen
5. Observe if the displayed data (e.g., stores, offers) reflect the new location

### Expected Behavior

After changing the location and returning to the main screen, the application should update the displayed data according to the new location.

### Actual Behavior

Manually entering a location, switching to it, and returning to the main screen does not update the displayed data. The problem occurs regardless of GPS state (enabled/disabled).

## Evidence & Analysis

![Screenshot of location settings](/evidence/screenshots/location_settings.jpg)
![Screenshot of main screen after location change](/evidence/screenshots/main_screen_no_update.jpg)

> **Video Reference:** Session recording [12:00-13:25] (Recording 2)

### Technical Impact Assessment

1. **Core Functionality Issue:** Location is a key element for matching offers
2. **User Experience Impact:** Lack of data updates may suggest that location change is not working
3. **Potential Business Impact:** Outdated data may affect users' purchasing decisions
4. **Trust Issue:** May undermine trust in the accuracy of information in the application

## Recommended Resolution

1. Implement automatic data updates after location change
2. Add loading indicator during data updates
3. Enhance the mechanism for detecting location changes and triggering data refreshes
4. Comprehensive testing of location features in various scenarios
