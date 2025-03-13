# README.md

## Project Overview

This document outlines the comprehensive testing strategy employed for the Blix mobile application QA assessment. The approach focuses on identifying, documenting, and analyzing both obvious and non-obvious quality issues through structured exploratory testing.

## Test Coverage Matrix (Updated)

The test approach was designed to ensure comprehensive coverage across all critical testing dimensions. The following matrix demonstrates how each charter addresses specific aspects of the application quality:

| Test Dimension  | Charter1 | Charter2 | Charter3 |
| --------------- | -------- | -------- | -------- |
| UI Verification | ✓        | ✓        | -        |
| Functionality   | ✓        | ✓        | ⚠️ [1]   |
| Error Handling  | ✓        | ✓        | ⚠️ [1]   |
| Performance     | -        | ✓        | ⚠️ [1]   |
| Security        | -        | -        | ⚠️ [1]   |
| Network         | -        | -        | ⚠️ [1]   |
| Interruptions   | -        | ✓        | ⚠️ [1]   |

[1] Testing strategy developed but not executed due to time constraints.

## Testing Methodology

### Structured Exploratory Testing

The testing approach employed structured exploratory testing guided by predefined charters, allowing for:

1. **Systematic Coverage**: Predefined focus areas ensured comprehensive testing
2. **Flexibility**: Adaptive exploration based on discovered behaviors
3. **Documentation**: Real-time recording of observations and defects
4. **Risk-Based Prioritization**: Focus on critical user journeys and core functionality

### Test Environment

- **Device**: Samsung Galaxy S21 FE 5G (SM-G990B2/DS)
- **OS**: Android 13 (One UI 5.1)
- **Screen Resolution**: 1080 x 2340 pixels
- **Available Storage**: 46 GB
- **Available RAM**: 2 GB
- **Screen Recording**: Default Android screen recorder

### Testing Charters

| Charter  | Focus Area                                   | Duration   | Date       | Completion            |
| -------- | -------------------------------------------- | ---------- | ---------- | --------------------- |
| Charter1 | First-Time User Experience                   | 33 minutes | 2025.03.11 | ✓ Complete            |
| Charter2 | Shopping List & Product Search Functionality | 45 minutes | 2025.03.13 | ✓ Complete            |
| Charter3 | Network Communication & API Functionality    | N/A        | 2025.03.13 | ⚠️ Strategy Developed |

## Key Findings Summary

### Critical Functional Issues

1. **Numerical Data Handling (BLIX-006)**
   - Price rounding issues: values like 2.01 incorrectly change to 2.00
   - Quantity value constraints: 1000 changes to 999.999
   - Decreasing quantity from 1 results in 0.001 instead of 0
   - Non-integer values accepted for product quantities

### User Experience Issues

1. **Configuration Controls (BLIX-001, BLIX-002)**

   - Technical cookie identifier exposed to users
   - Multiple toggle buttons unresponsive across settings interface

2. **Shopping List Management (BLIX-003, BLIX-004, BLIX-005, BLIX-010)**

   - Shopping list rename functionality fails consistently
   - List name validation issues (no length limits, accepts special characters)
   - Inconsistent name suggestion logic
   - Unpredictable navigation after list deletion

3. **Product Search and Display (BLIX-007, BLIX-008, BLIX-009)**

   - Unnecessary swipe gestures on single-page flyers
   - Incorrect product indication in flyers
   - Misleading filter error messages
   - Missing automatic price setting from flyers

4. **Location and Store Features (BLIX-011, BLIX-012)**
   - Favorite store toggle state not saved correctly
   - Location data not updated after manual changes

## Defect Distribution

| Severity | Count | Category    | Count |
| -------- | ----- | ----------- | ----- |
| Critical | 0     | UI          | 3     |
| High     | 1     | Functional  | 8     |
| Medium   | 11    | UX          | 1     |
| Low      | 0     | Performance | 0     |
| Total    | 12    | Security    | 0     |

## Testing Artifacts

1. **Test Session Reports**: Detailed documentation of each testing session
2. **Bug Reports**: Comprehensive defect documentation with steps to reproduce
3. **Test Journal**: Chronological record of test activities and observations
4. **Network Testing Strategy**: Detailed approach to analyzing API communication

## Evidence & Artifacts

### Screen Recordings

Complete session recordings are available in Google Drive: [Blix QA Test Sessions](https://drive.google.com/drive/folders/1JQ1HvrXrMKvdoYdDpobgDg7euxyaMFDD)

### Bug Evidence

Screenshots referenced in bug reports are timestamped and extracted from these recordings.

## Quality Assessment

Based on the testing conducted, the application demonstrates several quality concerns:

1. **Data Integrity**: Issues with numerical handling affect core shopping functionality
2. **User Experience**: Multiple UX inconsistencies impact ease of use
3. **Functional Reliability**: Core features like list renaming fail consistently

## Recommendations

### Short-Term Improvements

1. Address high-severity numerical handling issues in product editing
2. Fix unresponsive toggle buttons in cookie settings
3. Resolve shopping list renaming functionality
4. Correct navigation inconsistencies after list deletion

### Long-Term Quality Enhancements

1. Implement comprehensive input validation across the application
2. Enhance user feedback mechanisms for failed operations
3. Establish consistent navigation patterns throughout the application
4. Optimize network communication based on proposed testing strategy

## Test Execution Metrics

| Metric                  | Value               |
| ----------------------- | ------------------- |
| Total Test Duration     | 78 minutes          |
| Defects Identified      | 12                  |
| Test Scenarios Executed | 12                  |
| Test Sessions           | 3                   |
| Defect Density          | 0.15 defects/minute |

## Conclusion

The testing revealed several functional and UX issues that impact the application's quality and user experience. While some features work as expected, there are significant areas that require attention before the application can deliver a seamless shopping assistance experience. The combination of exploratory and structured testing approaches successfully uncovered both obvious and subtle quality concerns across multiple application dimensions.
