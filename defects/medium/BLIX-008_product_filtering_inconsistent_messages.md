# Bug Report: BLIX-008

## Summary

**Title:** Product Filtering - Incorrect "too many filters" message  
**Severity:** Medium  
**Priority:** P3

## Environment

- **Device:** Samsung Galaxy S21 FE 5G (SM-G990B2/DS)
- **OS:** Android 13 (One UI 5.1)
- **App Version:** Blix Test APK
- **Network State:** WiFi
- **Session Reference:** Test sessions timestamp 27:00-27:15 (Charter2)

## Reproduction

### Steps to Reproduce

1. Add "Pork loin" product to shopping list
2. Enter the product filtering options for this list
3. Observe available categories: "meat" and "Grocery items"
4. Select the "Grocery items" category
5. Observe the message "You have too many filters. Try reducing their number."

### Expected Behavior

1. The system should display filtered results or notify that no products matching the filter were found
2. Inactive filter categories should not be displayed or should be marked as unavailable

### Actual Behavior

When selecting the "Grocery items" category, an incorrect message appears: "You have too many filters. Try reducing their number.", despite only one filter being selected.

## Evidence & Analysis

![Screenshot of filter error message](/evidence/screenshots/filter_error_message.jpg)

> **Video Reference:** Session recording [27:00-27:15]

### Technical Impact Assessment

1. **UX Confusion:** Message suggests too many filters when actually only one was selected
2. **Feature Usability Issue:** Limited usefulness of the filtering function
3. **Product Categorization Problem:** Potential issues with assigning products to appropriate categories

## Recommended Resolution

1. Correct error messages for the filtering system
2. Display only those filter categories that can return results
3. Implement more informative messages, e.g., "No products in Grocery items category"
4. Review and correct product assignments to appropriate categories
