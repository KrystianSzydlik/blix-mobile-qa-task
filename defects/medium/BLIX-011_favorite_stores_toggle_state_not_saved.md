# Bug Report: BLIX-011

## Summary

**Title:** Store Card - Favorite stores toggle state not saved  
**Severity:** Medium  
**Priority:** P2

## Environment

- **Device:** Samsung Galaxy S21 FE 5G (SM-G990B2/DS)
- **OS:** Android 13 (One UI 5.1)
- **App Version:** Blix Test APK
- **Network State:** WiFi
- **Session Reference:** Test sessions timestamp 02:56 (Charter2 Recording 2)

## Reproduction

### Steps to Reproduce

1. Navigate to the store card view
2. Change the "Favorite Store" toggle state
3. Exit the store card view
4. Return to the same store's card
5. Observe the toggle state

### Expected Behavior

The "Favorite Store" toggle state should be saved and persist after exiting and returning to the store card view.

### Actual Behavior

The toggle state is not saved when changed directly in the store card. The state change only occurs when the operation is performed in the "Favorite Stores" tab.

## Evidence & Analysis

![Screenshot of toggle in store card](/evidence/screenshots/toggle_store_card.jpg)
![Screenshot of toggle after return](/evidence/screenshots/toggle_state_not_saved.jpg)

> **Video Reference:** Session recording [3:30-3:4:00] (Recording 2)

### Technical Impact Assessment

1. **Data Persistence Issue:** User preference state not saved
2. **UX Inconsistency:** Different behavior of the same UI element in different parts of the application
3. **User Frustration Risk:** Users may repeatedly try to change the setting without success

## Recommended Resolution

1. Implement consistent toggle state saving regardless of location in the application
2. Add visual confirmation of saved change
3. Unify favorite stores management logic throughout the application
4. Test state synchronization between different application views
