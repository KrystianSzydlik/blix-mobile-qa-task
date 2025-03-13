# Exploratory Testing Charter

## Charter Information

| Attribute        | Value                                                                |
| ---------------- | -------------------------------------------------------------------- |
| **CHARTER**      | Explore Blix Application Installation and First-Time User Experience |
| **SESSION TYPE** | Exploratory                                                          |
| **DURATION**     | 33 minutes                                                           |
| **TESTER**       | Krystian Szydlik                                                     |
| **DATE**         | 2025.03.11                                                           |

## Mission

> Investigate the installation process, startup behavior, and initial user flows with focus on detecting usability issues, UI anomalies, and functional defects during first-time app usage.

## Areas to Explore

1. Application installation process
2. App startup and splash screen behavior
3. Permission requests handling
4. First-time user onboarding flow
5. Initial navigation structure
6. First-use functionality accessibility

## Testing Techniques

- **Basic functionality verification**
- **UI/UX consistency assessment**
- **Error handling observation**

## Test Data Requirements

- Clean installation environment
- Test account credentials (if needed)

## Test Environment

Device: Samsung Galaxy S21 FE 5G (SM-G990B2/DS)
OS: Android 13 (One UI 5.1)
Network: WiFi connection
Storage: 46GB available

## Evidence Collection

- 📹 Screen recording of entire session
- 📸 Screenshots of defects observed
- 📝 Notes on timestamps of significant events

## Risks & Assumptions

- App may require specific permissions
- First-time setup may involve account creation
- Network connectivity may impact initial experience

---

### Session Notes

#### Timestamp [00:00-02:40]

- Application launches without visible issues
- Welcome screen displays with proper Blix branding
- Cookie consent management dialog appears
- Technical cookie identifier "\_cmpconsentx105796" exposed in user interface

#### Timestamp [02:40-10:00]

- Navigated to detailed cookie settings via "Customize" button
- In "Analytics & Statistics" > "Providers" > Google Analytics toggle unresponsive
- Toggles in sections "Ensuring security...", "Delivering and presenting ads..." and "Saving privacy decisions..." also unresponsive
- Group toggles for "Providers" in various sections consistently non-interactive
- Multiple tapping attempts do not change toggle states

#### Timestamp [10:00-28:00]

- Exploration of main interface and navigation
- Testing search functionality
- Browsing product categories
- Examining menu options and settings
- No significant issues identified in basic navigation

#### Timestamp [28:40-33:15]

- Accessed "Shopping Lists" functionality
- Attempted to rename default shopping list unsuccessfully - name not updated
- When editing a new shopping list name, system suggests "Shopping List X" (where X is incremented)
- After accepting suggested name and saving, system retains previous name instead
- List icon does not change despite rename attempt

### Defects Found

1. **[BLIX-001]** Cookie Settings - Technical cookie identifier "\_cmpconsentx105796" exposed to end users

   - Severity: Medium
   - Timestamp: [02:40]
   - Category: UX
   - Reproducibility: Always

2. **[BLIX-002]** Cookie Settings - Multiple toggle buttons unresponsive to user interaction across settings interface

   - Severity: Medium
   - Timestamp: [04:40-10:00]
   - Category: Functional
   - Reproducibility: Always

3. **[BLIX-003]** Shopping List - Inconsistent renaming functionality and behavior
   - Severity: Medium
   - Timestamp: [28:40-33:15]
   - Category: Functional
   - Reproducibility: Always

### Session Debrief

#### Test Coverage Assessment

- Successfully tested key elements of user's first contact with the application
- Thoroughly examined cookie consent management mechanism
- Verified basic navigation and functionality accessibility
- Partially tested shopping list functionality
- Verified location accuracy functionality

#### Areas Requiring Further Testing

- Product search and filtering functionality
- Complete process of creating and managing shopping lists
- Application behavior under limited connectivity conditions
- Performance aspects during intensive use

#### Critical Findings

1. Cookie consent management is defective, potentially violating GDPR requirements
2. Basic shopping list functionality exhibits inconsistent behavior
3. User interface contains technical elements that should be hidden

#### Recommendations

- Conduct dedicated test session focused on shopping list functionality
- Test application under various network conditions
- Perform network communication analysis using Charles Proxy
