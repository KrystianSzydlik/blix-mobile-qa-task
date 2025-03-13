# Bug Report: BLIX-007

## Summary

**Title:** Flyer View - Incorrect page scrolling and erroneous product indication  
**Severity:** Medium  
**Priority:** P2

## Environment

- **Device:** Samsung Galaxy S21 FE 5G (SM-G990B2/DS)
- **OS:** Android 13 (One UI 5.1)
- **App Version:** Blix Test APK
- **Network State:** WiFi
- **Session Reference:** Test sessions timestamp 15:00-23:00 (Charter2)

## Reproduction

### Steps to Reproduce

**Problem 1: Unnecessary swiping on single page**

1. Navigate to a flyer view that has only one page
2. Perform a "swipe" gesture left or right
3. Observe that the page refreshes despite no additional pages

**Problem 2: Incorrect product indication in flyer**

1. Search for product "butter"
2. Select the first position from Selgros store
3. Observe that the system points to the advertisement "More Offers in ONLINE Flyers" instead of the actual product
4. Select the second position of the same product
5. Observe that this time the system correctly points to Finu Butter

### Expected Behavior

1. When a flyer has only one page, swipe gestures should be disabled or ignored
2. The system should accurately indicate the specific product location on the flyer page

### Actual Behavior

1. It is possible to perform swipe gestures even with a single page, causing unnecessary refreshing of the same content
2. The first position of the "butter" product from Selgros incorrectly points to the "More Offers in ONLINE Flyers" advertisement instead of the product itself

## Evidence & Analysis

![Screenshot of incorrect product indication](/evidence/screenshots/incorrect_product_indication.jpg)
![Screenshot of correct product indication](/evidence/screenshots/correct_product_indication.jpg)

> **Video Reference:** Session recording [15:30-16:10] & [21:00-23:00]

### Technical Impact Assessment

1. **UX Inefficiency:** Unnecessary page refreshing with single-page flyers
2. **User Confusion:** Incorrect product indication may mislead users
3. **Product Discovery Issue:** Difficulties in finding desired products in flyers

## Recommended Resolution

1. Deactivate swipe gestures for flyers containing only one page
2. Improve the product recognition and indication algorithm in flyers
3. Add alternative methods for product identification on flyer pages
4. Implement a verification mechanism for the accuracy of product indications
