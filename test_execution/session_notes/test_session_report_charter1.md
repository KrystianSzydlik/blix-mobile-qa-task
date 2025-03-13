# Test Session Report: Blix Mobile Application - First-Time User Experience

## Session Overview

| Attribute         | Value                      |
| ----------------- | -------------------------- |
| **Session Focus** | First-time User Experience |
| **Charter**       | Charter1                   |
| **Duration**      | 33 minutes                 |
| **Tester**        | Krystian Szydlik           |
| **Date**          | 2025.03.11                 |

## Scenarios Tested

### 1. APPLICATION INSTALLATION

**Status:** ✅ Completed

#### Areas Covered

- Download and installation process
- App permissions handling
- Initial launch sequence
- Initial permission requests

#### Results

> **Observations:** Installation completed successfully, permissions requested appropriately  
> **Defects Found:** None

---

### 2. COOKIE SETTINGS CONFIGURATION

**Status:** ✅ Completed

#### Areas Covered

- Navigation to cookie settings
- Toggle functionality
- Information presentation

#### Results

> **Observations:**
>
> - Technical cookie identifier "\_cmpconsentx105796" exposed to end users
> - Multiple toggle buttons unresponsive across different cookie setting sections:
>   - Google Analytics toggle button unresponsive [04:40]
>   - "Ensuring security, fraud prevention and error fixing" toggle unresponsive [06:05-08:12]
>   - "Delivery and presentation of ads and content" toggle unresponsive [09:10]
>   - "Saving privacy decisions and informing about them" toggle unresponsive [10:00]
>   - Group toggle buttons for "Providers" consistently unresponsive
>
> **Defects Found:** [BLIX-001](../../defects/medium/BLIX-001_cookie_technical_id_exposed.md), [BLIX-002](../../defects/medium/BLIX-002_cookie_toggles_unresponsive.md)

#### Defect Details

**[BLIX-001](../../defects/medium/BLIX-001_cookie_technical_id_exposed.md)**: Cookie Settings - Technical cookie identifier "\_cmpconsentx105796" exposed to end users

- **Severity**: Medium
- **Impact**: Compromises user experience by exposing technical implementation details
- **Location**: Data management section under cookie settings
- **Evidence**: [Screenshot](../../evidence/screenshots/cookie_settings_technical_id.jpg), Session recording [02:40-03:10]

**[BLIX-002](../../defects/medium/BLIX-002_cookie_toggles_unresponsive.md)**: Cookie Settings - Multiple toggle buttons unresponsive to user interaction

- **Severity**: Medium
- **Impact**: Prevents users from exercising control over data collection preferences
- **Location**: Multiple sections within cookie settings
- **Evidence**: [Screenshot](../../evidence/screenshots/cookie_toggles_unresponsive.jpg), Session recording [04:40-10:00]

---

### 3. ACCOUNT CREATION AND USER PROFILE MANAGEMENT

**Status:** ✅ Completed

#### Areas Covered

- Phone number verification process
- User profile creation
- Registration form validation

#### Results

> **Observations:**
>
> - Successfully completed phone number verification process
> - User profile creation functions properly
> - Form validation appears to work as expected
>
> **Defects Found:** None

---

### 4. SHOPPING LIST FUNCTIONALITY

**Status:** ✅ Completed

#### Areas Covered

- List creation
- Item addition
- List renaming functionality

#### Results

> **Observations:**
>
> - Default shopping list cannot be renamed - changes to name are not saved [28:40]
> - When editing default shopping list, icon remains unchanged after attempted rename
> - When creating a new shopping list, system suggests "Shopping List 2" in input field
> - After naming differently and then deleting entire name, system suggests "Shopping List 3" [31:20]
> - When accepting a suggested list name and saving, the previous name is retained instead of the suggestion [33:15]
>
> **Defects Found:** [BLIX-003](../../defects/medium/BLIX-003_shopping_list_issues.md)

#### Defect Details

**[BLIX-003](../../defects/medium/BLIX-003_shopping_list_issues.md)**: Shopping List - Inconsistent renaming functionality and behavior

- **Severity**: Medium
- **Impact**: Affects user ability to organize shopping lists effectively
- **Location**: Shopping list management screens
- **Evidence**: [Screenshot](../../evidence/screenshots/shopping_list_rename_issues.jpg), Session recording [28:40-33:15]

---

## Testing Approach

- 🔍 Exploratory testing following Charter 1 objectives
- 👤 Focus on first-time user experience
- 🎨 Emphasis on UI/UX consistency and functional reliability
- 📶 Testing conducted under normal connectivity conditions

## Technical Environment

- **Device:** Samsung Galaxy S21 FE 5G (SM-G990B2/DS)
- **OS:** Android 13 (One UI 5.1)
- **Network:** WiFi connection
- **Evidence:** Full session recording with timestamps

## Defect Summary

| Bug ID   | Title                                                           | Severity | Category   | Reference                                                               |
| -------- | --------------------------------------------------------------- | -------- | ---------- | ----------------------------------------------------------------------- |
| BLIX-001 | Technical cookie identifier exposed to end users                | Medium   | UI/UX      | [Details](../../defects/medium/BLIX-001_cookie_technical_id_exposed.md) |
| BLIX-002 | Multiple cookie toggle buttons unresponsive to user interaction | Medium   | Functional | [Details](../../defects/medium/BLIX-002_cookie_toggles_unresponsive.md) |
| BLIX-003 | Shopping list rename functionality issues                       | Medium   | Functional | [Details](../../defects/medium/BLIX-003_shopping_list_issues.md)        |

## Next Steps

- Test product search and categorization (planned for Charter2)
- Verify favorite stores functionality
- Test application behavior with network interruptions (planned for Charter2)
- Investigate checkout flow and payment methods
- Analyze network communication (planned for Charter3)

## Device Performance Notes

- Device temperature remained stable throughout the testing session
