Test Plan - E-commerce App
Project: e-commerce app
Document Version: 2.0
Author: Olena Onyshkiv
Date: 15/08/2026

1. Introduction
   This Test Plan outlines the testing strategy, scope, and objectives for the e-commerce web application built using Vue 3, TypeScript, and the FakeStore API. It defines the testing strategy, scope, environment, and deliverables required to validate the core functionality and usability of the application as actually tested.

2. Scope
   In Scope
   The following features were tested during this cycle:

Functional:

-Login functionality (valid and invalid credentials, empty fields)
-Protected routes — Wishlist and Cart access control
-Wishlist access when authenticated
-Cart access when authenticated
-Session persistence after page refresh
-Logout functionality
-Protected route access after logout

Non-Functional:
-Mobile navigation / UI behaviour on small screens

Out of Scope (not tested in this cycle):

-Home view (product grid, filtering, routing)
-Product detail view
-Header components (logo, store name, dynamic categories)
-Category filtering and URL deep linking
-Accessibility checks (alt attributes, semantic HTML, keyboard navigation)
-Payment processing
-Performance testing
-Security testing
-Backend reliability (FakeStore API is external)

Items marked "Out of Scope" were either not part of this testing cycle or were not covered by formal test cases. They are listed as recommendations for future testing in the Test Summary Report.

3. Objectives
   a) Verify that login works correctly with valid, invalid, and empty credentials.
   b) Test protected routes (Wishlist, Cart) before and after authentication.
   c) Confirm that the session persists across a page refresh.
   d) Verify that logout ends the session and re-locks protected routes.
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
   Manual Functional Testing To test interactive features step-by-step, like a real user.
   Exploratory Testing To discover unexpected bugs by freely interacting with the app without predefined test cases.
   Responsive Testing Using Chrome DevTools to check mobile (375px) viewport behaviour.
   API Validation Using the Network tab to confirm correct communication with FakeStore API.
6. Test Environment
   Item Details
   Browser Google Chrome 152.0.7977.54 (Official Build) (64-bit)
   Devices Mobile viewport (375x667, 430x932)
   Operating System Windows 11 Pro 25H2
   API Fake Store API (https://fakestoreapi.com)
7. Deliverables
   Test Plan

Test Cases (Excel/Sheets) — Login, Wishlist & Cart, Session & Security, UI

Bug Report Log (BUG_001A, BUG_001B)

Test Summary Report

Screenshots of defects

8. Test Data
   Product data is fetched dynamically from the Fake Store API. Login credentials used during testing are the static test values provided by the FakeStore API documentation (mor*2314 / 83r5^*). No mock or manually generated datasets were used.
