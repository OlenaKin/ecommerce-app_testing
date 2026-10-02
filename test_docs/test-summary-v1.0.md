Test Summary Report — E-commerce App
Project: e-commerce app
Document Version: 1.0
Author: Olena Onyshkiv
Date: 24/08/2026
Related Document: Test Plan — E-commerce App (v1.0)

1. Introduction
   This Test Summary Report provides a summary of the testing activities performed on the e-commerce web application built with Vue 3, TypeScript, and the FakeStore API. It reports on the scope covered, the results of executed test cases, defects identified, and an overall assessment of the application's quality.

2. Summary of Testing
   Item Detail
   Total test cases executed 13
   Passed 12
   Failed 1
   Blocked / Not run 0
   Pass rate 92.3%
   Bugs identified 2
   Testing period 15/08/2026 – 24/08/2026
   Note: The single failing test case (TC_013, mobile navigation menu) produced the 2 UI/UX defects listed in Section 5. All other functional areas — login, protected routes, wishlist, cart, and session management — passed.

3. Test Coverage
   Testing covered the following features, as defined in the Test Plan:

Feature Status Notes
Home View (product grid, images, names, prices) Tested Data loaded correctly from FakeStore API.
Category Filter (header categories, URL updates, deep linking) Tested Filtering and URL updates behaved as expected.
Product Detail View Tested Correct product loaded, including on refresh.
Authentication (valid/invalid credentials, empty fields) Tested Login validation works; error messages display correctly.
Protected Routes (Wishlist, Cart) Tested Unauthenticated users redirected to login; authenticated users gain access.
Session & Security (session persistence, logout, protected route after logout) Tested Session persists on refresh; logout ends session; protected routes blocked after logout.
Responsiveness (mobile / tablet / desktop) Tested Layout adapts correctly; 2 UI defects found in mobile view.
Accessibility (basic) Tested Alt attributes and semantic HTML present; keyboard navigation functional. 4. Test Results
4.1 Login Functionality
Test Case ID Description Priority Result
TC_001 Verify login with valid credentials High Pass
TC_002 Verify login with invalid password High Pass
TC_003 Verify login with invalid username High Pass
TC_004 Verify login with empty username field Medium Pass
TC_005 Verify login with empty password field Medium Pass
4.2 Wishlist & Cart
Test Case ID Description Priority Result
TC_006 Verify access to Wishlist when not logged in High Pass
TC_007 Verify access to Cart when not logged in High Pass
TC_008 Verify access to Wishlist when logged in High Pass
TC_009 Verify access to Cart when logged in High Pass
4.3 Session & Security
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
   Details:

BUG_001A: On Chrome mobile view, opening the menu leaves the header hamburger unchanged, while a second close ("X") control appears inside the menu — resulting in duplicate close controls. Does not prevent use of the app.

BUG_001B: After selecting a menu item (e.g., "Jewelry"), navigation occurs but the menu stays open and overlays the page content, forcing the user to close it manually.

6. Environment
   Item Details
   Browser Google Chrome 152.0.7977.54 (Official Build) (64-bit) \*
   Devices Desktop 1440px, Tablet 768px, Mobile 375px (375x667, 430x932)
   Operating System Windows 11 Pro 25H2
   API Fake Store API (https://fakestoreapi.com)

- Discrepancy note: The Test Plan (v1.0) lists Chrome 151.0.7922.138. All bug evidence and responsive testing were captured on Chrome 152.0.7977.54. The Test Plan browser version should be updated to match the actual test environment, or the discrepancy explained in the next revision.

7. Overall Assessment
   The core functionality of the application is stable and working as expected. 12 of 13 test cases passed, covering authentication, protected routes, wishlist, cart, and session management. The single failure (TC_013) is limited to the mobile navigation menu's UI/UX behavior and does not block the user from completing any task — the menu still opens and closes, just not with the expected visual and automatic behavior.

Given the low-to-medium severity of the open defects and the 92.3% pass rate on core functionality, the application is considered ready for use in its current state, with the two UI issues recommended for a future fix.

8. Recommendations
   Fix BUG_001A so the header hamburger transforms into an 'X' and remove the duplicate close control inside the menu.

Fix BUG_001B so the mobile menu closes automatically after a menu item is selected.

Re-test TC_013 after fixes to confirm both defects are resolved.

Update the Test Plan (v1.0) browser version to match the actual test environment (Chrome 152.0.7977.54).
