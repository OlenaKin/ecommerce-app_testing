ecommerce-app
Test Summary Report — E-commerce App

Project: e-commerce app
Document Version: 2.0
Author: Olena Onyshkiv
Date: 02/10/2026 (testing period: 15/08/2026 – 24/08/2026)
Related Document: Test Plan — E-commerce App (v2.0)
App under test: ecommerce-app
Backend: Fake Store API (https://fakestoreapi.com)

Revision History
Version Date Change
1.0 24/08/2026 Initial report
2.0 02/10/2026 Figures aligned with the test case workbook (13 executed, 1 failed). Defects linked to TC_013. Coverage aligned with Test Plan v2.0. Exit criteria check and limitations added.

1. Introduction

This Test Summary Report summarises the testing activities performed on the e-commerce web application built with Vue 3, TypeScript, and the FakeStore API. It reports the scope covered, the results of executed test cases, the defects identified, and an overall assessment of the tested areas.

2. Summary of Testing
   Item Detail
   Total test cases executed 13
   Passed 12
   Failed 1 (TC_013)
   Blocked / Not run 0
   Pass rate 92.3%
   Bugs identified 2 (both from TC_013)
   Testing period 15/08/2026 – 24/08/2026

Note: The single failing test case (TC_013, mobile navigation menu) produced the 2 UI/UX defects listed in Section 5.

3. Test Coverage
   Feature Status Notes
   Login functionality Tested TC_001–TC_005. All passed.
   Wishlist & Cart — access control (protected routes) Tested TC_006–TC_009. All passed. Adding/removing items and totals were not tested.
   Session management Tested TC_010–TC_012. All passed.
   Mobile navigation / UI Tested TC_013. Failed — 2 defects raised.

Areas planned but not tested in this cycle are listed in Section 9.2.

4. Test Results

Test cases are documented in test-cases.xlsx.

4.1 Login Functionality
Test Case ID Description Priority Result
TC_001 Verify login with valid credentials High Pass
TC_002 Verify login with invalid password High Pass
TC_003 Verify login with invalid username High Pass
TC_004 Verify login with empty username field Medium Pass
TC_005 Verify login with empty password field Medium Pass
4.2 Wishlist & Cart (access control)
Test Case ID Description Priority Result
TC_006 Verify access to Wishlist when not logged in High Pass
TC_007 Verify access to Cart when not logged in High Pass
TC_008 Verify access to Wishlist when logged in High Pass
TC_009 Verify access to Cart when logged in High Pass
4.3 Session Management
Test Case ID Description Priority Result
TC_010 Verify session persists after page refresh Medium Pass
TC_011 Verify logout functionality Medium Pass
TC_012 Verify protected route access after logout Medium Pass
4.4 Navigation / UI
Test Case ID Description Priority Result
TC_013 Verify mobile navigation menu functions correctly on smaller screens High Fail

Result: 12 / 13 test cases passed (92.3%).

5. Defects Identified
   Bug ID Title Type Severity / Priority Linked Test Case Status
   BUG_001A Hamburger icon does not transform to 'X' when mobile menu is open UI/UX, Visual Low / Low TC_013 Open
   BUG_001B Mobile menu does not close automatically after selecting an item UI/UX, Functional Medium / Medium TC_013 Open

BUG_001A: On Chrome mobile view, opening the menu leaves the header hamburger unchanged, while a second close ("X") control appears inside the menu, resulting in duplicate close controls.

BUG_001B: After selecting a menu item (e.g., "jewelery"), navigation occurs but the menu stays open and overlays the page content, forcing the user to close it manually.

6. Environment
   Item Details
   Browser Google Chrome 152.0.7977.54 (Official Build, 64-bit)
   Desktop viewport 1440px
   Mobile viewports 375x667, 430x932 (Chrome DevTools)
   Operating System Windows 11 Pro 25H2
   API Fake Store API (https://fakestoreapi.com)
7. Exit Criteria Check

Criteria defined in Test Plan v2.0, Section 7:

Exit criterion Status
All in-scope test cases executed Met (13 of 13)
All failures have a bug report with reproduction steps Met (TC_013 → BUG_001A, BUG_001B)
Test Summary Report complete Met
No open High-severity defects Met (open defects: 1 Medium, 1 Low) 8. Overall Assessment

No blocking defects were found within the tested scope. Login, protected-route access control, and session management worked as expected: 12 of 13 test cases passed. The single failure (TC_013) concerns the mobile navigation menu and does not prevent task completion; the menu still opens and closes, but not with the expected visual and automatic behaviour.

Recommendation: fix BUG_001B (Medium priority) before release; BUG_001A (Low priority) can be deferred to a later release.

These results apply only to the areas listed in Section 3. The areas in Section 9.2 were not tested and carry unknown risk.

8.1 Limitations and Risks
Testing was performed in Google Chrome only; behaviour in other browsers is unverified.
Mobile layouts were simulated with Chrome DevTools, not tested on physical devices.
Only the mobile navigation menu was checked at small screen widths.
Wishlist and cart were tested for access control only, not for item handling.
Login testing used the FakeStore API public demo account.
The FakeStore API is an external service and may change independently of the application. 9. Recommendations
9.1 Fixes for identified defects
Fix BUG_001A so the header hamburger transforms into an 'X', and remove the duplicate close control inside the menu.
Fix BUG_001B so the mobile menu closes automatically after a menu item is selected.
Re-test TC_013 after the fixes to confirm both defects are resolved.
9.2 Recommended future testing (not covered in this cycle)
Home view — product grid rendering, routing, product card click behaviour
Product detail view — correct product display and refresh behaviour
Header components — logo, store name, dynamic category loading
Category filtering and URL deep linking
Accessibility checks — alt attributes, semantic HTML, keyboard navigation
Wishlist and cart item functionality (adding, removing, quantities, totals)
Cross-browser testing (Firefox, Safari, Edge)
Cross-device testing on physical mobile and tablet hardware
