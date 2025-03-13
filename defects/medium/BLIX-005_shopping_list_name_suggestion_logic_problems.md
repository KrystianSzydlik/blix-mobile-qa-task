# Bug Report: BLIX-005

## Summary

**Title:** Shopping List - Incorrect list name suggestion logic  
**Severity:** Medium  
**Priority:** P2

## Environment

- **Device:** Samsung Galaxy S21 FE 5G (SM-G990B2/DS)
- **OS:** Android 13 (One UI 5.1)
- **App Version:** Blix Test APK
- **Network State:** WiFi
- **Session Reference:** Test sessions timestamp 03:00-03:40 (Charter2)

## Reproduction

### Steps to Reproduce

1. Navigate to "Listy zakupów" (Shopping Lists)
2. Note the existing number of lists (e.g., 5 lists)
3. Tap "Utwórz nową listę" (Create new list) - system suggests "Shopping List 12" (correct)
4. Cancel creating a new list
5. Edit an existing list
6. Delete the entire current name
7. Observe that system suggests "Shopping List 12" (incorrect)

### Expected Behavior

1. When creating a new list, the system should suggest "Shopping List X", where X = number of existing lists + 1
2. When editing an existing list, the system should not suggest a new number or should suggest the original list number

### Actual Behavior

The system suggests the same incremental value (X = number of lists + 1) both when creating a new list and when editing an existing list, despite editing not increasing the number of lists.

## Evidence & Analysis

![Screenshot of name suggestion when creating](/evidence/screenshots/new_list_suggestion.jpg)
![Screenshot of name suggestion when editing](/evidence/screenshots/edit_list_suggestion.jpg)

> **Video Reference:** Session recording [03:00-03:40]

### Technical Impact Assessment

1. **UX Inconsistency:** Illogical user interface behavior
2. **User Confusion:** Suggestions that do not correspond to the context of user action
3. **System Logic Flaw:** No distinction between creation and editing operations

## Recommended Resolution

1. Correct the name suggestion logic to be contextual:
   - When creating a new list: "Shopping List X" where X = number of lists + 1
   - When editing an existing list: do not suggest a new name or suggest the original name
2. Thoroughly test the name suggestion mechanism in various scenarios
3. Implement consistent list name management logic throughout the application
