# Test Session Report: Blix Mobile Application - Shopping List Functionality

## Session Overview

| Attribute         | Value                                          |
| ----------------- | ---------------------------------------------- |
| **Session Focus** | Shopping List Functionality and Product Search |
| **Charter**       | Charter2                                       |
| **Duration**      | 45 minutes                                     |
| **Tester**        | Krystian Szydlik                               |
| **Date**          | 2025.03.13                                     |

## Scenarios Tested

### 1. SHOPPING LIST MANAGEMENT

**Status:** ✅ Completed

#### Areas Covered

- List creation with various naming patterns
- List editing and renaming
- Icon selection and customization
- List sharing functionality
- List deletion and subsequent navigation
- Input validation and boundary testing

#### Results

> **Observations:**
>
> - Application accepts list names with excessive character lengths without validation
> - Application accepts names consisting entirely of special characters
> - Application allows duplicate list names without warning
> - Application truncates long list names with no method to view full name except in edit mode
> - List renaming functionality consistently fails across both default and user-created lists
> - Name suggestion logic is inconsistent between creating and editing lists
> - Icon selection and saving functions properly
> - List deletion shows inconsistent navigation behavior, sometimes redirecting to flyers, other times to home screen
>
> **Defects Found:** [BLIX-003](../../defects/medium/BLIX-003_shopping_list_issues.md), [BLIX-004](../../defects/medium/BLIX-004_shopping_list_validation_and_display_issues.md), [BLIX-005](../../defects/medium/BLIX-005_shopping_list_name_suggestion_logic_problems.md), [BLIX-010](../../defects/medium/BLIX-010_incorrect_navigation_after_shopping_list_deletion.md)

---

### 2. PRODUCT EDITING AND NUMERICAL DATA HANDLING

**Status:** ✅ Completed

#### Areas Covered

- Product price entry and validation
- Product quantity management
- Numerical boundaries testing
- Decimal value handling

#### Results

> **Observations:**
>
> - Critical price rounding issues observed: values like 2.01, 4.02, 5.02 are incorrectly rounded to 2.00, 4.01, 5.01 respectively
> - Quantity value of 1000 is automatically changed to 999.999
> - Decreasing quantity from 1 results in 0.001 instead of 0
> - System accepts non-integer values for product quantities where integers would be appropriate
>
> **Defects Found:** [BLIX-006](../../defects/high/BLIX-006_product_editing_numerical_data_validation_issues.md)

---

### 3. PRODUCT FILTERING AND SEARCH

**Status:** ✅ Completed

#### Areas Covered

- Product search functionality
- Category filtering mechanism
- Error handling for filters with no results
- Filter combinations testing

#### Results

> **Observations:**
>
> - Search functionality returns relevant products
> - Category filtering shows UI/UX issues when selecting certain categories
> - When filtering "Schab" (pork loin) with "Art. spożywcze" (Grocery items) category, system incorrectly displays "You have too many filters" message
> - Filter categories with no matching products are presented as available options without indication
>
> **Defects Found:** [BLIX-008](../../defects/medium/BLIX-008_product_filtering_inconsistent_messages.md)

---

### 4. FLYER AND PROMOTION INTERACTION

**Status:** ✅ Completed

#### Areas Covered

- Product-to-flyer connections
- Flyer navigation and visualization
- Offer indication accuracy
- Price synchronization between flyers and shopping lists

#### Results

> **Observations:**
>
> - Single-page flyers allow unnecessary swipe gestures causing page refreshes
> - Product indication in flyers can be inaccurate, pointing to advertisements instead of actual products
> - Prices from promotional flyers are not automatically transferred to shopping lists
> - "Butter" search shows inconsistent product indication between first and second result from same store
>
> **Defects Found:** [BLIX-007](../../defects/medium/BLIX-007_flyer_view_and_product_indication_issues.md), [BLIX-009](../../defects/medium/BLIX-009_missing_automatic_price_setting_from_flyer.md)

---

### 5. STORE MANAGEMENT AND LOCATION FEATURES

**Status:** ✅ Completed

#### Areas Covered

- Favorite stores functionality
- Location-based store discovery
- Location change impact on displayed offers
- Location accuracy and updates

#### Results

> **Observations:**
>
> - Favorite store toggle state is not saved when changed directly in store card view
> - Toggle state only persists when changed in the dedicated "Favorite Stores" tab
> - Manually entering a new location does not update displayed data on main screen
> - Location update issues persist regardless of GPS state (enabled/disabled)
>
> **Defects Found:** [BLIX-011](../../defects/medium/BLIX-011_favorite_stores_toggle_state_not_saved.md), [BLIX-012](../../defects/medium/BLIX-012_location_data_not_updated.md)

---

### 6. INTERRUPTION TESTING

**Status:** ✅ Completed

#### Areas Covered

- Application behavior during incoming calls
- Background/foreground transitions
- State preservation during interruptions
- Receipt scanning interruption recovery

#### Results

> **Observations:**
>
> - Application handles minimization and restoration appropriately
> - Receipt scanning process recovers correctly after application restart
> - No significant issues observed during interruption testing
>
> **Defects Found:** None

---

## Testing Approach

- 🔍 Exploratory testing following Charter 2 objectives
- 👤 Focus on shopping list management and product search functionality
- 🎨 Emphasis on data validation and user experience consistency
- 📶 Testing conducted under both normal and interrupted connectivity conditions
- 🧮 Detailed testing of numerical data handling and validation
- 🗺️ Verification of location-based features functionality

## Technical Environment

- **Device:** Samsung Galaxy S21 FE 5G (SM-G990B2/DS)
- **OS:** Android 13 (One UI 5.1)
- **Network:** Alternating between WiFi and Mobile Data
- **Session Recording:** Full screen capture with timestamps
- **Resource Monitoring:** Android system tools

## Defect Summary

| Bug ID   | Title                                                                                    | Severity | Category   | Reference                                                                                     |
| -------- | ---------------------------------------------------------------------------------------- | -------- | ---------- | --------------------------------------------------------------------------------------------- |
| BLIX-004 | Shopping List - Lack of name validation and long name display issues                     | Medium   | UI         | [Details](../../defects/medium/BLIX-004_shopping_list_validation_and_display_issues.md)       |
| BLIX-005 | Shopping List - Incorrect list name suggestion logic                                     | Medium   | UI         | [Details](../../defects/medium/BLIX-005_shopping_list_name_suggestion_logic_problems.md)      |
| BLIX-006 | Product Editing - Numerical data validation issues and incorrect mathematical operations | High     | Functional | [Details](../../defects/high/BLIX-006_product_editing_numerical_data_validation_issues.md)    |
| BLIX-007 | Flyer View - Incorrect page scrolling and erroneous product indication                   | Medium   | Functional | [Details](../../defects/medium/BLIX-007_flyer_view_and_product_indication_issues.md)          |
| BLIX-008 | Product Filtering - Incorrect "too many filters" message                                 | Medium   | Functional | [Details](../../defects/medium/BLIX-008_product_filtering_inconsistent_messages.md)           |
| BLIX-009 | Shopping List - Missing automatic price setting from flyer                               | Medium   | Functional | [Details](../../defects/medium/BLIX-009_missing_automatic_price_setting_from_flyer.md)        |
| BLIX-010 | Shopping List - Incorrect navigation after list deletion                                 | Medium   | Functional | [Details](../../defects/medium/BLIX-010_incorrect_navigation_after_shopping_list_deletion.md) |
| BLIX-011 | Store Card - Favorite stores toggle state not saved                                      | Medium   | Functional | [Details](../../defects/medium/BLIX-011_favorite_stores_toggle_state_not_saved.md)            |
| BLIX-012 | Location - Location data not updated                                                     | Medium   | Functional | [Details](../../defects/medium/BLIX-012_location_data_not_updated.md)                         |

## Next Steps

- Test application behavior under poor network conditions
- Perform security testing on communication channels
- Conduct network traffic analysis using Charles Proxy (planned for Charter3)
- Investigate app behavior with very large shopping lists (performance testing)
- Test multi-user collaboration features more extensively
- Verify notification handling and push message processing

## Device Performance Notes

- Device remained responsive throughout testing
- No excessive battery drain observed during testing session
- No significant memory issues noted during testing period
