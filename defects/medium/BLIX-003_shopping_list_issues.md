# Bug Report: BLIX-003

## Summary

**Title:** Shopping List - Inconsistent renaming functionality and behavior  
**Severity:** Medium  
**Priority:** P2

## Environment

- **Device:** Samsung Galaxy S21 FE 5G (SM-G990B2/DS)
- **OS:** Android 13 (One UI 5.1)
- **App Version:** Blix Test APK
- **Network State:** LTE
- **Session Reference:** Test sessions timestamp 28:40-33:15 (Charter1) and 00:00-04:00 (Charter2)

## Reproduction

### Steps to Reproduce

**Issue 1: List Renaming Failure**

1. Navigate to "Listy zakupów" (Shopping Lists)
2. Tap on any shopping list (default or user-created) to enter the list view
3. Tap on the list name or settings to access editing options
4. Attempt to rename the shopping list (try both short and very long names)
5. Tap "Save" or confirm the change
6. Observe that the name does not update and icon remains unchanged

**Issue 2: Inconsistent Name Suggestions**

1. Create a new shopping list
2. Enter the edit mode for the new list
3. Delete the current name completely from the input field
4. Observe that system suggests "Lista Zakupów X" (where X is an incremented number)
5. Accept the suggestion and save changes
6. Notice the previous name is retained instead of the suggestion

**Issue 3: Anomaly in Name Suggestion Logic**

1. Note the current number of shopping lists (e.g., 10 lists)
2. When creating a new list, system suggests "Lista Zakupów 11" (correct)
3. When editing an existing list, system also suggests "Lista Zakupów 11"
4. This is illogical since editing doesn't increase the total number of lists

### Expected Behavior

**Issue 1:** All shopping lists should be renamable, with both name and icon updating properly after saving changes.

**Issue 2:** When accepting a suggested name and saving, the system should apply that exact name to the list.

**Issue 3:** The name suggestion logic should be context-aware - when creating a new list, suggest "Lista Zakupów X" where X = current number of lists + 1; when editing an existing list, suggest a name based on the current list or no suggestion at all.

### Actual Behavior

**Issue 1:** Attempting to rename any shopping list fails - the name doesn't update and the icon remains unchanged.

**Issue 2:** After accepting a suggested name and saving, the previous name is retained instead of applying the suggested name.

**Issue 3:** The system suggests the same incremented list number value regardless of whether creating a new list or editing an existing one, demonstrating a lack of context awareness in the suggestion logic.

## Evidence & Analysis

### Visual Evidence

![Default List Edit Screen](/evidence/screenshots/shopping_list_edit_default.jpg)
![New List Edit Screen](/evidence/screenshots/shopping_list_edit_new.jpg)
![Shopping List View](/evidence/screenshots/shopping_list_view.jpg)
![Multiple List Types](/evidence/screenshots/multiple_shopping_lists.jpg)

> **Video Reference:** Session recordings [28:40-33:15] and [00:00-04:00]

### Technical Impact Assessment

1. **Data Persistence Issue:** Changes to list names are not being properly saved to the database
2. **UI/Data Model Disconnect:** Possible disconnect between UI components and underlying data storage
3. **Suggestion Logic Flaw:** The list naming suggestion engine appears to have no awareness of context (new vs. edit)
4. **User Experience Impact:** Creates significant frustration when basic naming functionality doesn't work
5. **User Trust Issue:** Core functionality failure reduces user confidence in the application
6. **Data Integrity Concern:** Suggests potential underlying issues with broader data persistence mechanisms

### Root Cause Analysis

The issues likely stem from:

- Missing or incorrect implementation of update methods for shopping list objects
- Static counter for list numbering that doesn't account for contextual differences between create/edit operations
- Event handler implementation that doesn't properly commit changes to persistent storage
- Lack of validation between UI input and data storage layer
- Absence of proper feedback mechanisms when operations fail
- Potential race condition between UI state updates and database commits

## Recommended Resolution

1. Implement proper data persistence for name changes in shopping lists
2. Create context-aware name suggestion logic that behaves differently for new vs. existing lists
3. Add validation to ensure names are properly saved
4. Provide user feedback when list operations succeed or fail
5. Ensure consistent behavior across all list types (default and user-created)
6. Add comprehensive unit and integration tests for list naming operations

## Additional Notes

This is a critical user experience issue affecting a core functionality of the application. The pervasive nature of these issues across the shopping list management interface suggests fundamental implementation flaws rather than isolated bugs. Given that shopping lists are a primary feature of this application, addressing these issues should be considered high priority despite the Medium severity rating.
