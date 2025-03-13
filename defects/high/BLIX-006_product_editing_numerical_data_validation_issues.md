# Bug Report: BLIX-006

## Summary

**Title:** Product Editing - Numerical data validation issues and incorrect mathematical operations  
**Severity:** High  
**Priority:** P1

## Environment

- **Device:** Samsung Galaxy S21 FE 5G (SM-G990B2/DS)
- **OS:** Android 13 (One UI 5.1)
- **App Version:** Blix Test APK
- **Network State:** WiFi
- **Session Reference:** Test sessions timestamp 07:00-13:00 (Charter2)

## Reproduction

### Steps to Reproduce

**Problem 1: Incorrect price handling**

1. Add any product to the shopping list
2. Edit the product price, entering a value with cents, e.g., 2.01
3. Save changes
4. Observe that the price changes to 2.00

**Problem 2: Quantity value limit**

1. Edit product quantity
2. Enter value 1000
3. Observe that the value changes to 999.999

**Problem 3: Incorrect quantity reduction**

1. Set product quantity to 1
2. Use the "-" button to decrease the value
3. Observe that the value changes to 0.001 instead of 0

**Problem 4: Accepting non-integer values for quantity**

1. Edit product quantity
2. Enter value 1.5
3. Observe that the system accepts non-integer product quantity

### Expected Behavior

1. Prices should be accurately recorded with the entered cent values
2. Application should handle appropriate maximum values or inform about limits
3. Decreasing quantity below 1 should result in 0 or a minimum value established in the system
4. Product quantity should be validated as an integer, if the product is not sold by weight

### Actual Behavior

1. Prices with cent values (e.g., 2.01, 4.02, 5.02) are rounded down (2.00, 4.01, 5.01)
2. Entering a quantity value of 1000 changes to 999.999
3. Decreasing a quantity of 1 results in a value of 0.001
4. The system accepts non-integer values for product quantities (e.g., 1.5)

## Evidence & Analysis

![Screenshot of price rounding issue](/evidence/screenshots/price_rounding_bug.jpg)
![Screenshot of price rounding issue](/evidence/screenshots/price_rounding_bug2.jpg)
![Screenshot of quantity limit issue](/evidence/screenshots/quantity_limit_bug.jpg)
![Screenshot of quantity limit issue](/evidence/screenshots/quantity_limit_bug_2.jpg)
![Screenshot of decimal quantity accepted](/evidence/screenshots/decimal_quantity_bug.jpg)

> **Video Reference:** Session recording [07:00-13:00]

### Technical Impact Assessment

1. **Critical Business Logic Failure:** Incorrect price calculations can lead to errors in shopping cost estimation
2. **Data Integrity Issue:** Storing incorrect values affects application reliability
3. **UX Frustration:** Users may be confused by changes to entered values
4. **Potential Financial Miscalculations:** Erroneous data can lead to incorrect budget expectations for users

## Recommended Resolution

1. Fix the handling of decimal values in prices to accurately preserve entered values
2. Implement appropriate validation for numeric fields with clear limit messages
3. Correct the increment/decrement logic for quantities
4. Add appropriate data type validation (integers vs. decimals) depending on context
5. Comprehensive testing of all mathematical operations in the application
