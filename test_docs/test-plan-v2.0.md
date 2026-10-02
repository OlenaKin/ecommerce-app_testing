Test Plan — E-commerce App
Project: e-commerce app
Document Version: 2.0 — Revised after execution
Author: Olena Onyshkiv
Original Date: 15/08/2026
Revision Date: 02/10/2026
App under test: ecommerce-app (Vue 3 + TypeScript front end, FakeStore API as backend) [the link to be added]

Revision History
Version Date Change
1.0 15/08/2026 Initial plan
2.0 02/10/2026 Scope reduced to match executed testing. Home view, product detail, category filter, and accessibility moved to "Not tested in this cycle (deferred)". Environment updated to Chrome 152. Test approach corrected to reflect what was actually performed.

1. Introduction
   This Test Plan defines the testing strategy, scope, environment, and deliverables for the e-commerce web application built with Vue 3, TypeScript, and the FakeStore API. Version 2.0 reflects the scope as executed and is issued after the testing cycle, alongside the Test Summary Report.

2. Scope
   2.1 In Scope (tested)
   Functional:
   Login functionality — valid credentials, invalid credentials, empty fields
   Protected routes — Wishlist and Cart access control only (redirect when unauthenticated, access when authenticated)
   Session persistence after page refresh
   Logout functionality
   Protected route access after logout

Non-Functional:
Mobile navigation behaviour on small screens

2.2 Out of Scope (deliberate exclusions)
Payment processing
Performance testing
Security testing
Backend reliability (FakeStore API is external and treated as a fixed dependency)

2.3 Not Tested in This Cycle (deferred)
These areas were part of the original project scope but were not covered by formal test cases in this cycle:
Home view — product grid rendering, routing, product card click behaviour
Product detail view — correct product display and refresh behaviour
Header components — logo, store name, dynamic category loading
Category filtering and URL deep linking
Accessibility checks — alt attributes, semantic HTML, keyboard navigation
Wishlist and cart item functionality (adding, removing, quantities, totals) — only access to these pages was tested

Cross-browser and cross-device testing on physical devices

3. Objectives
   a) Verify login works correctly with valid, invalid, and empty credentials.
   b) Test protected routes (Wishlist, Cart) before and after authentication.
   c) Confirm the session persists across a page refresh.
   d) Verify logout ends the session and re-locks protected routes.
   e) Validate mobile navigation behaviour on small screens.
   f) Identify defects and document them with clear reproduction steps and evidence.

4. Features to Test
   Feature Details
   Login Functionality Valid login redirects to home page. Invalid credentials show "Login failed". Empty fields show "Please fill out this field".
   Wishlist & Cart (Protected Routes) Unauthenticated users are redirected to login. Authenticated users can access Wishlist and Cart pages.
   Session & Security Session persists after refresh. Logout ends the session and re-locks protected routes.
   Mobile Navigation / UI Hamburger menu opens correctly on mobile viewports. Menu closes properly and navigation behaves as expected.
5. Test Approach
   Method Description
   Manual Functional Testing Interactive features tested step-by-step, as a real user would.
   Responsive Testing Using Chrome DevTools to check mobile viewports (375x667 and 430x932).
   Note: Exploratory testing and API validation via the Network tab were not performed as separate activities in this cycle. The two defects found came from the failure of TC_013, not from free exploration.

6. Test Environment
   Item Details
   Browser Google Chrome 152.0.7977.54 (Official Build) (64-bit)
   Desktop Viewport 1440px (default browser window — used for login, wishlist, cart, and session tests)
   Mobile Viewports 375x667, 430x932 (Chrome DevTools — used for TC_013)
   Operating System Windows 11 Pro 25H2
   API Fake Store API (https://fakestoreapi.com)
7. Entry and Exit Criteria
   Entry criteria:
   Application is deployed and reachable.
   FakeStore API is responding.
   Test cases for the in-scope features are reviewed and approved.
   Test environment (browser and viewports) is available.

Exit criteria:

All in-scope test cases have been executed.
All failures have a corresponding bug report with reproduction steps.
Test Summary Report is complete.
No open High-severity defects (current cycle: none).

8. Risks and Assumptions
   Assumptions:
   The FakeStore API behaves consistently throughout the cycle.
   Chrome 152 is representative of the target browser for the tested features.
   The public demo account credentials are stable and remain valid.

Risks:

Testing was limited to Chrome; cross-browser behaviour is unverified.
Only mobile navigation was tested on small screens; other features were not re-checked at mobile widths.
Features listed under "Not tested in this cycle" carry untested risk into production.

9. Severity and Priority Definitions
   Severity Definition
   Critical Prevents core use of the application (e.g., cannot log in at all).
   High Major feature is broken or unusable; no workaround.
   Medium Feature works but with significant degradation; workaround exists.
   Low Minor visual or cosmetic issue; does not affect task completion.
   Priority Definition
   High Must be fixed before release.
   Medium Should be fixed before release if possible.
   Low Can be deferred to a future release.
10. Deliverables
    Test Plan (this document)
    Test Cases — Login, Wishlist & Cart, Session & Security, UI
    Bug Report Log (BUG_001A, BUG_001B)
    Test Summary Report
    Screenshots of defects

11. Test Data
    Product data is fetched dynamically from the Fake Store API. Login testing used the FakeStore API public demo account:

Valid credentials: mor*2314 / 83r5^*

Invalid username variant: mor*2315 / 83r5^*

Invalid password variant: mor*2314 / 85r5^*

These are publicly documented demo values, not real credentials. No mock or manually generated datasets were used.
