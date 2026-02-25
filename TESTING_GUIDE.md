# LOCAL TESTING GUIDE - NEW BUILD
## Complete Testing Checklist Before Deployment

---

## 📁 SETUP INSTRUCTIONS

### **1. Create Test Folder Structure:**
```
test-priscilla/
├── index.html
├── search.html
└── images/
    └── priscilla-logo.png
```

### **2. Download Files:**
1. Download `index.html` from outputs
2. Download `search.html` from outputs  
3. Download `priscilla-logo.png` (already provided)
4. Place in structure above

### **3. Open in Browser:**
- Open `index.html` in Chrome, Firefox, or Safari
- Keep browser console open (Press F12 → Console tab)
- Watch for any JavaScript errors

---

## ✅ TESTING CHECKLIST - HOMEPAGE (index.html)

### **TEST 1: Navigation Structure**
Open index.html in browser.

**Check:**
- [ ] Logo "Priscilla Yeboah" is on the **FAR LEFT** of navigation bar
- [ ] Menu items (About, Services, etc.) are on the **FAR RIGHT**
- [ ] Logo font is Jost (clean sans-serif, NOT fancy serif)
- [ ] No "Schedule Consultation" button anywhere
- [ ] Hover over menu items → should turn dusty blue color

**How to verify logo is LEFT:**
1. Right-click on logo → Inspect
2. Check CSS: `justify-content: space-between` on nav-container
3. Logo should be first element, menu should be last

**PASS CRITERIA:** Logo is visibly on left edge, menu on right edge

---

### **TEST 2: Hero Section Text**
Scroll to top of page.

**Check:**
- [ ] Eyebrow text: **"Premier Real Estate Service"** (NOT "Delaware's Premier Realtor")
- [ ] Headline: **"Your Home Search Starts Here"** (NOT "Your home journey starts here")
- [ ] Headline font is Jost (sans-serif, NOT Cormorant Garamond serif)
- [ ] Description mentions "buy, sell, or rent" without Delaware reference
- [ ] Two buttons visible: "Browse Listings" + "Get in Touch"

**How to verify:**
1. Read the text on screen carefully
2. Right-click headline → Inspect
3. Font-family should be 'Jost', sans-serif

**PASS CRITERIA:** Exact text as specified, Jost font used

---

### **TEST 3: Hero Slideshow Images**
Watch the hero section background images.

**Check:**
- [ ] Image 1: Cozy modest single-family home (NOT luxury mansion)
- [ ] Image 2: Charming townhouse (NOT upscale property)
- [ ] Image 3: Modern apartment (this one is fine)
- [ ] Images auto-advance every 5 seconds
- [ ] Three dots at bottom of hero - clicking changes image
- [ ] Active dot turns gold color

**How to verify:**
1. Watch slideshow for 15 seconds (should cycle through all 3)
2. Click the dots manually
3. Images should clearly show modest, family-oriented homes

**PASS CRITERIA:** Modest homes shown, NOT luxury estates

---

### **TEST 4: About Section - Priscilla's Logo**
Scroll down to "Dedicated to Your Success" section.

**Check:**
- [ ] Priscilla's logo image displays in circular frame
- [ ] Circular gradient background (champagne → dusty blue)
- [ ] Logo has drop shadow effect (subtle depth)
- [ ] White padding/background around logo
- [ ] Professional, polished appearance

**If logo doesn't load (no /images/ folder):**
- [ ] Fallback placeholder appears (champagne circle with "Priscilla Yeboah Real Estate" text)
- [ ] Placeholder has same circular gradient background

**How to verify:**
1. Look at About section
2. You should see either: actual logo OR champagne placeholder
3. Should NOT see broken image icon

**PASS CRITERIA:** Image displays OR fallback shows (not broken image)

---

### **TEST 5: Back-to-Top Button - CRITICAL**
This is the most important test.

**Steps:**
1. Open index.html
2. **SCROLL DOWN** past hero section (scroll at least halfway down page)
3. Look at **BOTTOM-RIGHT corner** of screen
4. Circular dusty blue button with "↑" should appear
5. Click the button
6. Page should smoothly scroll back to top

**Check:**
- [ ] Button is **HIDDEN** when at top of page (opacity: 0, visibility: hidden)
- [ ] After scrolling 300px down, button **APPEARS** (fades in)
- [ ] Button is bottom-right corner, circular, dusty blue background
- [ ] White "↑" arrow inside button
- [ ] Clicking button scrolls smoothly to top
- [ ] Hovering button makes it lift up slightly

**How to verify in console (F12):**
1. Open browser console
2. Look for log: "✅ Back to top button shown (scrollY: XXX)"
3. Click button, look for: "🔝 Back to top clicked - scrolling to top"

**PASS CRITERIA:** Button appears after scrolling, clicking scrolls to top

**COMMON MISTAKE:** Not scrolling down far enough. You MUST scroll down!

---

### **TEST 6: Services Section**
Scroll to "Complete Real Estate Services" section.

**Check:**
- [ ] Three service cards: Home Buying, Home Selling, Rental Properties
- [ ] Cards have emoji icons: 🏡 💰 🔑
- [ ] Hovering cards makes them lift up (transform effect)
- [ ] Clean, professional appearance

**PASS CRITERIA:** Three cards visible with hover effects

---

### **TEST 7: Featured Properties - HIDDEN**
Scroll through entire page carefully.

**Check:**
- [ ] **NO "Featured Properties" section visible anywhere**
- [ ] Page jumps from Services → Testimonials (no properties between)
- [ ] NO placeholder properties
- [ ] NO "coming soon" message for properties
- [ ] Section is completely absent

**How to verify in code:**
1. Right-click page → View Page Source
2. Search for "properties" class
3. Should have `display: none` in CSS

**PASS CRITERIA:** Featured Properties section does not exist on page

---

### **TEST 8: Testimonials - Auto-Rotating**
Scroll to "What My Clients Say" section.

**Steps:**
1. Look at testimonials when page loads
2. Note which 4 testimonials are showing
3. Wait 8 seconds
4. Testimonials should fade out and NEW ones appear
5. Wait another 8 seconds - should rotate again

**Check:**
- [ ] Shows 4 testimonials in 2x2 grid
- [ ] Testimonials auto-rotate every 8 seconds
- [ ] Smooth fade-in animation when rotating
- [ ] 6 total testimonials cycling: Teju Adelagunja, Emeka Boka, Abiodun Kalejaiye, EA K, Wole Legend, O U
- [ ] Dark background (dusty-blue-dark)

**How to verify in console:**
1. Look for log: "💬 Showing testimonials: 0 to 3"
2. After 8 seconds: "🔄 Testimonials rotated"

**PASS CRITERIA:** Testimonials automatically rotate every 8 seconds

---

### **TEST 9: Contact Section**
Scroll to "Let's Connect" section.

**Check:**
- [ ] Phone: +1 (302) 898-6379 (clickable)
- [ ] Email: contact@priscillayeboah.com (clickable)
- [ ] Address: 2706 Kirkwood Highway, Wilmington, Delaware
- [ ] Hours: Monday-Friday 8:00 AM - 5:00 PM
- [ ] Contact form with: Name, Email, Phone, Message fields
- [ ] Submit button: "Send Message"

**Test form submission:**
1. Fill out all fields
2. Click "Send Message"
3. Should see alert: "Message received! (Note: Form backend will be configured during deployment.)"
4. Form should reset (fields clear)

**PASS CRITERIA:** All contact info correct, form submits with alert

---

### **TEST 10: Mobile Responsive**
Resize browser window to mobile size (375px width).

**Check:**
- [ ] Navigation logo still on left
- [ ] Hamburger menu (☰) appears
- [ ] Clicking hamburger opens menu below
- [ ] Menu items stack vertically
- [ ] Hero title readable (smaller font)
- [ ] All sections stack single-column
- [ ] Back-to-top button still works
- [ ] All text readable (not too small)

**PASS CRITERIA:** Site works on mobile without breaking

---

## ✅ TESTING CHECKLIST - SEARCH PAGE (search.html)

### **TEST 11: Search Page Navigation**
Click "Search Properties" in navigation OR open search.html directly.

**Check:**
- [ ] Logo "Priscilla Yeboah" on **FAR LEFT** (same as homepage)
- [ ] Menu items on **FAR RIGHT** (same as homepage)
- [ ] Navigation looks identical to homepage
- [ ] Clicking menu items goes to homepage sections

**PASS CRITERIA:** Navigation identical to homepage

---

### **TEST 12: Back to Home Button**
Look at top-right area of search page.

**Check:**
- [ ] "← Back to Home" button visible (fixed position, top-right)
- [ ] Button has champagne gold background
- [ ] Hovering changes to dusty blue
- [ ] Clicking returns to homepage (index.html)

**PASS CRITERIA:** Button visible and functional

---

### **TEST 13: Search Interface**
Look at search card on search.html.

**Check:**
- [ ] Three tabs: "For Sale", "For Rent", "Recently Sold"
- [ ] "For Sale" tab is active (colored) by default
- [ ] Clicking tabs changes active state
- [ ] Three input fields: ZIP Code, City, Address/Keyword
- [ ] "Search Properties" button at bottom

**Test search form:**
1. Enter ZIP code: 19801
2. Enter City: Wilmington
3. Click "Search Properties"
4. Should see alert: "Live property search will be available once Bright MLS integration is complete..."

**PASS CRITERIA:** Tabs work, form submits with alert

---

### **TEST 14: MLS Placeholder**
Scroll down on search page.

**Check:**
- [ ] Heading: "Live Property Search Coming Soon"
- [ ] Description explains what will happen
- [ ] Setup steps box (numbered list 1-6)
- [ ] Instructions for getting Bright MLS link
- [ ] Cost mentioned: ~$10/month
- [ ] Link back to contact Priscilla

**PASS CRITERIA:** Professional placeholder with instructions

---

### **TEST 15: Back-to-Top on Search Page**
**CRITICAL: Test this separately from homepage!**

**Steps:**
1. Open search.html
2. **SCROLL DOWN** to bottom of page
3. Look at **BOTTOM-RIGHT corner**
4. Circular dusty blue button should appear
5. Click button
6. Should scroll to top

**Check:**
- [ ] Button appears after scrolling down
- [ ] Same design as homepage (circular, dusty blue, "↑")
- [ ] Clicking scrolls to top smoothly
- [ ] Works independently from homepage version

**PASS CRITERIA:** Back-to-top works on search page

---

## 🐛 CONSOLE ERROR CHECK

**In browser console (F12 → Console tab), check for:**

### **Expected Console Logs (Good):**
```
=== PRISCILLA YEBOAH WEBSITE - DEBUG LOG ===
✅ DOM Content Loaded
🔍 Back to top button found: [object HTMLButtonElement]
🎬 Slideshow initialized with 3 slides
🖼️ Showing slide: 1
💬 Showing testimonials: 0 to 3
✅ All JavaScript initialized successfully
```

### **After scrolling down:**
```
✅ Back to top button shown (scrollY: 450)
```

### **After clicking back-to-top:**
```
🔝 Back to top clicked - scrolling to top
```

### **Errors to Look For (Bad):**
- ❌ "Cannot read property of null" → Element not found
- ❌ "Uncaught TypeError" → JavaScript error
- ❌ "Failed to load resource" → Missing file

**PASS CRITERIA:** No red error messages in console

---

## 📊 FINAL SUCCESS CRITERIA

**ALL must be TRUE before deployment:**

### **Homepage (index.html):**
- ✅ Logo positioned on FAR LEFT
- ✅ Menu items on FAR RIGHT
- ✅ Headline: "Your Home Search Starts Here" (Jost font)
- ✅ Eyebrow: "Premier Real Estate Service"
- ✅ Modest home images in slideshow
- ✅ Priscilla logo shows OR fallback placeholder shows
- ✅ Back-to-top button appears after scrolling 300px down
- ✅ Back-to-top button scrolls to top when clicked
- ✅ Testimonials auto-rotate every 8 seconds
- ✅ Featured Properties section completely hidden
- ✅ Contact form submits with alert
- ✅ NO console errors

### **Search Page (search.html):**
- ✅ Navigation identical to homepage
- ✅ Logo on LEFT, menu on RIGHT
- ✅ "Back to Home" button visible and working
- ✅ Back-to-top button appears when scrolling
- ✅ Search tabs functional
- ✅ Search form submits with alert
- ✅ MLS placeholder displays with instructions
- ✅ NO console errors

### **Mobile Responsive:**
- ✅ Hamburger menu works
- ✅ All sections stack properly
- ✅ Text readable on small screens

---

## 🎯 TESTING WORKFLOW

**Follow this order:**

1. **Setup** → Create folder, download files
2. **Open index.html** → Test homepage features (Tests 1-10)
3. **Open search.html** → Test search page features (Tests 11-15)
4. **Check console** → Verify no errors
5. **Mobile test** → Resize browser window
6. **Final review** → Compare against success criteria

---

## 📸 SCREENSHOT PROOF (Optional but Recommended)

Take screenshots of:
1. Homepage with logo on left, menu on right
2. Back-to-top button visible (scroll down first!)
3. About section with Priscilla logo
4. Testimonials section
5. Search page with back-to-home button
6. Browser console showing success logs (no errors)

---

## 🚀 AFTER PASSING ALL TESTS

**You're ready to deploy when:**
- All checkboxes above are checked ✅
- No red errors in console
- Screenshots show everything working
- Mobile view tested and working

**Next steps:**
1. Confirm all tests passed
2. Review deployment guide
3. Upload to cPanel
4. Test live site
5. Client approval

---

**Questions or issues? Check console logs for debugging clues!**
