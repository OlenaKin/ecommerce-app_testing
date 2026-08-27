**BUG_001B**

**Title:**
Mobile menu does not close automatically after selecting an item on Chrome mobile view

**Bug Type:**
UI/UX, Visual

**Severity / Priority:**
Medium, Medium (Impacts user flow and navigation; user must manually close the menu to see the destination page)

**Steps to Reproduce:**
1. Open the application in Chrome responsive/mobile view.
2. Click the hamburger menu icon in the header.
3. Observe the opened mobile menu options.
4. Click on a menu item (e.g., "Wishlist" or "Cart").
5. Observe the page behavior and the menu state.

**Expected Result:**
1. The mobile menu automatically closes.
2. The application navigates to the selected page.

**Actual Result:**
The application navigates to the selected page, but the mobile menu remains open and overlays the page content. The user is required to manually click the "X" icon to close the menu and view the selected page.

**Environment Details:**
- Browser: Chrome 152.0.7977.54 (Official Build) (64-bit)
- OS: Windows 11 Pro 25H2
- View: Responsive/mobile view

**Suggested Fix:**
Update the menu component's click handler to trigger the closeMenu() function immediately after a menu item link is clicked. Ensure the state for the menu (open/close) is reset to false upon route navigation.

**Screenshot** (after clicking the link "jewelery"):
<img width="189" height="322" alt="Image" src="https://github.com/user-attachments/assets/52c1e7e3-79b0-475b-815a-369c3c2602ea" />