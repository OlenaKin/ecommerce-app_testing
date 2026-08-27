# Test Plan — E-commerce App

**Project:** e-commerce app  
**Document Version:** 1.0  
**Author:** Olena Onyshkiv  
**Date:** 15/08/2026

---

## 1. Introduction

This Test Plan outlines the testing strategy, scope, and objectives for the e-commerce web application built using Vue 3, TypeScript, and the FakeStore API.

## 2. Scope

### In Scope

**Functional:**
- Home view (product grid, filtering, routing)
- Product detail view
- Header (logo, store name, dynamic categories)
- Category filtering
- URL updates and deep linking
- Authentication flow
- Wishlist functionality
- Shopping cart functionality
- Authentication & protected routes (Wishlist, Cart)

**Non-Functional:**
- Responsive layout (mobile/tablet/desktop)
- Accessibility basics

### Out of Scope

- Payment processing
- Performance testing
- Security testing
- Backend reliability (FakeStore API is external)

## 3. Objectives

a) Verify that product data is fetched and displayed correctly from the Fake Store API.  
b) Test protected routes (Wishlist, Cart) after authentication.  
c) Ensure users can filter products by category.  
d) Confirm that product detail pages show accurate information.  
e) Validate that the app is responsive and usable on tablet and mobile screen sizes.  
f) Identify defects and document them with clear reproduction steps and evidence.

## 4. Features to Test

| Feature | Details |
|---------|---------|
| **Home View** | Product grid displays images, names, and prices. Product cards are clickable. Data loads from FakeStore API. |
| **Category Filter** | Categories load dynamically in header. Clicking a category filters products. URL updates accordingly. Deep linking loads correct filtered state. |
| **Product Detail** | Displays name, image, price, description. Loads correct product on refresh. |
| **Authentication & Protected Routes** | Wishlist and Cart accessible only after login. Unauthenticated user → redirected to login. Authenticated user → page loads normally. |
| **Responsiveness** | Layout adapts on mobile, tablet, and desktop. |
| **Accessibility (Basic)** | Images have alt attributes. Semantic HTML elements used. Basic keyboard navigation works. |

## 5. Test Approach

| Method | Description |
|--------|-------------|
| **Manual Functional Testing** | To test interactive features step-by-step, like a real user. |
| **Exploratory Testing** | To discover unexpected bugs by freely interacting with the app. |
| **Responsive Testing** | Using Chrome DevTools to check mobile (375px), tablet (768px), and desktop (1440px). |
| **Accessibility Checks** | Using browser tools to verify alt attributes, semantic HTML, and keyboard navigation. |
| **API Validation** | Using the Network tab to confirm correct communication with FakeStore API. |

## 6. Test Environment

| Item | Details |
|------|---------|
| Browser | Google Chrome 151.0.7922.138 |
| Devices | Desktop 1440px, Tablet 768px, Mobile 375px |
| Operating System | Windows 11 Version 25H2 |
| API | Fake Store API (https://fakestoreapi.com) |

## 7. Deliverables

- Test Plan
- Test Cases (Excel/Sheets)
- Bug Report Log
- Test Summary Report
- Screenshots of defects

## 8. Test Data

All test data will be fetched dynamically from the Fake Store API. No static test data, mock data, or manual test datasets are required.