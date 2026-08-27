**BUG_001A**

**Title: 
Hamburger icon does not transform to 'X' when mobile menu is open on Chrome mobile view

**Bug Type**: 
UI/UX, Visual

**Severity:** 
Low, Priority: Low (It's a visual inconsistency which does not prevent the user from using the app)

**Steps to Reproduce:** 

1. Open the application in Chrome responsive/mobile view.
2. Click the hamburger menu icon in the header.
3. Observe the hamburger icon and the opened mobile menu.
4. Observe the menu controls.

**Expected Result:** 

1. The menu opens when hamburger is clicked
2. The hamburger turns into an X icon 
3. Only one close control should be displayed

**Actual Result:** 
 The header shows a hamburger that doesn't turn into an X icon. Additionally, the toggle menu shows an X icon (right below the hamburger).

**Environment details:** 

- Browser: Chrome 152.0.7977.54 (Official Build) (64-bit)
- OS: Windows 11 Pro 25H2
- View: Responsive/mobile view

**Suggested Fix:**
When the mobile menu is open, the hamburger icon in the header should transform into an “X” icon, and the additional “X” inside the menu should be removed to avoid duplicate close controls.

<img width="316" height="463" alt="Image" src="https://github.com/user-attachments/assets/5a78c7ce-599c-4fd4-9348-519138bd63b4" />

 