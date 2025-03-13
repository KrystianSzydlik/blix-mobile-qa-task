# Exploratory Testing Charter

## Charter Information

| Attribute        | Value                                                       |
| ---------------- | ----------------------------------------------------------- |
| **CHARTER**      | Explore Blix Shopping List and Product Search Functionality |
| **SESSION TYPE** | Exploratory                                                 |
| **DURATION**     | 45 minutes                                                  |
| **TESTER**       | Krystian Szydlik                                            |
| **DATE**         | 2025.03.13                                                  |

## Mission

> Investigate the shopping list creation, editing, and product search functionality with focus on data persistence, UI consistency, error handling during critical operations, and application resilience under suboptimal conditions. Additionally, explore expense tracking, loyalty cards management, and location-based features.

## Areas to Explore

1. Shopping list creation, editing, and deletion workflows
2. Product search and addition to shopping lists
3. List sharing and collaboration features
4. Category navigation and product browsing
5. Application behavior under network fluctuations and interruptions
6. Expense tracking and receipt management features
   - Receipt scanning functionality
   - Multiple receipt addition methods (photo, e-receipt)
   - Receipt data extraction accuracy
   - Expense categorization and visualization
   - Period filtering (week, month, 6 months, year)
7. Loyalty cards management
   - Adding popular loyalty cards
   - Adding custom loyalty cards
   - Barcode scanning functionality
   - Cards accessibility during shopping
8. Location-based features
   - Location change impact on displayed offers
   - Store availability based on location
   - Location accuracy and precision

## Testing Techniques

- **Functional verification** of core shopping list CRUD operations
- **UI/UX consistency assessment** across list manipulation flows
- **Error handling observation** during critical operations
- **Interruption testing** during list creation and editing
  - Incoming calls while saving changes
  - Push notifications during critical operations
  - App backgrounding/foregrounding during active processes
- **System resource usage monitoring** using Android profiling tools
- **Boundary testing** on list item quantities and text input fields
- **Camera functionality testing** for receipt and loyalty card scanning
- **Permission flow testing** for camera and location access

## Test Data Requirements

- Multiple shopping list templates (empty, partially filled, maximum capacity)
- Various product types for adding to lists
- Long text strings for name fields (boundary testing)
- Special characters for input validation
- Sample receipts for scanning tests
- Physical loyalty cards for scanning tests
- Multiple location settings for location-based testing

## Test Environment

- **Device:** Samsung Galaxy S21 FE 5G (SM-G990B2/DS)
- **OS:** Android 13 (One UI 5.1)
- **Network:** Alternating between WiFi and Mobile Data
- **Resource Monitoring:** Android Profiler for memory and CPU usage tracking

## Evidence Collection

- 📹 Screen recording of entire session
- 📸 Screenshots of defects observed
- 📝 Notes on timestamps of significant events
- 📊 Resource usage metrics at key interaction points

## Risks & Assumptions

- List operations may require backend synchronization
- Product search likely depends on network connectivity
- Complex interactions may reveal performance bottlenecks
- Interrupted operations might lead to data inconsistency
- Receipt scanning accuracy may depend on lighting conditions
- OCR functionality for receipts may not handle all formats equally

---

### Session Notes

[To be completed during testing]

### Defects Found

[To be completed during testing]

### Session Debrief

[To be completed after testing]
