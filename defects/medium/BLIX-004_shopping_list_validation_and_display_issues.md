# Bug Report: BLIX-004

## Summary

**Title:** Shopping List - Lack of name validation and long name display issues  
**Severity:** Medium  
**Priority:** P2

## Environment

- **Device:** Samsung Galaxy S21 FE 5G (SM-G990B2/DS)
- **OS:** Android 13 (One UI 5.1)
- **App Version:** Blix Test APK
- **Network State:** WiFi
- **Session Reference:** Test sessions timestamp 00:00-03:00 (Charter2)

## Reproduction

### Steps to Reproduce

1. Navigate to "Listy zakupów" (Shopping Lists)
2. Tap "Utwórz nową listę" (Create new list)
3. Try various naming scenarios:
   - Enter extremely long name
   - Enter name consisting only of special characters (@#$&-()=%"\*:'/!?+)
   - Enter a name identical to an existing list
4. Save the list and observe the results

### Expected Behavior

1. Names should have reasonable character limits with validation
2. Special characters should be either restricted or properly handled
3. Duplicate names should be prevented or warned about
4. Full name should be visible throughout the application, not just in edit mode

### Actual Behavior

1. System accepts names with extremely long strings without validation or limits
2. System accepts names consisting entirely of special characters
3. System allows duplicate list names without warnings
4. Full list names are only visible on the edit screen, truncated elsewhere

## Evidence & Analysis

![Screenshot of long list name](/evidence/screenshots/long_list_name.jpg)
![GIF of long list name](/evidence/screenshots/long_list_name.gif)
![Screenshot of special characters list](/evidence/screenshots/special_chars_list.jpg)
![Screenshot of duplicate lists](/evidence/screenshots/duplicate_lists.jpg)

> **Video Reference:** Session recording [00:00-03:00]

### Technical Impact Assessment

1. **UX Problem:** Difficult management of multiple lists with similar or unreadable names
2. **Data Management Issue:** Potential issues with processing long names in the database
3. **UI Clarity Issue:** Difficulties in identifying lists after creation
4. **User Confusion Risk:** Duplicate names may lead to user mistakes

## Recommended Resolution

1. Implement appropriate list name validation with reasonable character limits
2. Add warnings for duplicate names
3. Improve UI to display full names or implement proper truncation with tooltips
4. Create consistent name display across all application screens
5. Consider adding unique icons or color codes for faster list identification
