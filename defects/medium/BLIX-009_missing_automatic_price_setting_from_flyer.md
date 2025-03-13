# Bug Report: BLIX-009

## Summary

**Title:** Shopping List - Missing automatic price setting from flyer  
**Severity:** Medium  
**Priority:** P2

## Environment

- **Device:** Samsung Galaxy S21 FE 5G (SM-G990B2/DS)
- **OS:** Android 13 (One UI 5.1)
- **App Version:** Blix Test APK
- **Network State:** WiFi
- **Session Reference:** Test sessions timestamp 29:30 (Charter2)

## Reproduction

### Steps to Reproduce

1. Search for any product (e.g., milk)
2. Select a variant from a specific store with a price from the flyer
3. Add the product to the shopping list
4. Check if the product price in the shopping list matches the price visible in the flyer

### Expected Behavior

The product price in the shopping list should be automatically set to the value from the selected flyer offer.

### Actual Behavior

The product price is not automatically set according to the value from the flyer - it must be entered manually.

## Evidence & Analysis

![Screenshot of product from flyer](/evidence/screenshots/product_in_flyer.jpg)
![Screenshot of product in shopping list](/evidence/screenshots/product_in_list_no_price.jpg)

> **Video Reference:** Session recording [29:30]

### Technical Impact Assessment

1. **Usability Issue:** The need to manually enter prices reduces application usage efficiency
2. **UX Inconsistency:** Users would expect automatic transfer of price information
3. **Core Functionality Gap:** Does not fully utilize the potential of integration between promotional flyers and shopping lists

## Recommended Resolution

1. Implement automatic price transfer from flyers to shopping lists
2. Add option to modify price after automatic setting
3. Display information about price source (e.g., "Price from Żabka flyer")
4. Test accuracy of price extraction from various flyer formats
