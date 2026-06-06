# Milestone 0: Setup and Planning
- **Destination chosen:** Nepal (Kathmandu and surrounding regions)
- **Primary audience:** First-time visitors to Nepal looking for authentic cultural and natural experiences
- **One design decision that reflects the destination:** Used warm earthy brick colors (#c65d3b, #a0522d) inspired by the red-brick monuments in Kathmandu's Durbar Squares to evoke the cozy, warm feeling of Nepal's heritage architecture
- **Wireframe format used:** HTML-based interactive wireframe (darsan-wireframe.html) showing desktop and mobile layouts for all pages

## Milestone 1: HTML Structure

**One HTML structure choice and why:**
- Used `<article>` elements for attraction cards instead of generic `<div>` because each attraction is self-contained, independently distributable content with its own title, image, and description. This provides better semantic meaning for screen readers and SEO.

**One thing Claude generated that I changed:**
- Claude initially suggested a separate image in the Welcome section below the hero, but I removed it to keep the hero video as the main visual focal point, making the page cleaner and more impactful.

**One place where wireframe guided a decision:**
- The wireframe showed a 3-column grid layout for attractions cards on desktop. This guided me to use Flexbox with `flex: 1 1 calc(33.333% - 24px)` to create responsive cards that adapt to 2 columns on tablet and 1 column on mobile.

## Milestone 2: CSS Styling

**One color/font choice and why:**
- **Color:** Used #c65d3b (warm brick red) for the navigation bar and accent elements. This reflects the red brick architecture of Kathmandu's Durbar Squares and creates the warm, cozy feeling I wanted visitors to experience.
- **Fonts:** Combined Google Fonts - Playfair Display (elegant serif for main headings), Cinzel (classic serif for card titles), Poppins (modern sans-serif for body), and Lora (readable serif for longer text). This mix balances tradition with modernity, matching Nepal's blend of ancient culture and contemporary hospitality.

**One Claude suggestion I rejected:**
- Claude initially used Merriweather for all body text, but I switched to Poppins because it's more modern, legible on screens, and creates better contrast with the serif headings.

**One style that didn't look right at first:**
- The hero text overlay was hard to read against the video. I added a darker overlay (`rgba(0, 0, 0, 0.4)`) and increased text-shadow values to improve readability while keeping the video visible.

## Milestone 3: Flexbox Layout

**One Flexbox property choice made deliberately:**
- Used `flex-wrap: wrap` on the cards container with `gap: 24px` instead of margins. This creates consistent spacing between cards that automatically adjusts when cards wrap to new rows, making the layout truly fluid and responsive.

**One place where Claude generated layout didn't match my plan:**
- Claude initially created the highlights grid with fixed widths. I changed it to `flex: 1 1 300px` with `max-width: 350px` so cards grow to fill space but never become too wide, creating better visual balance.

**One layout challenge that required adjusting HTML structure:**
- The navigation bar needed `justify-content: space-between` for logo and links, but the links themselves needed their own flex container to arrange horizontally. This required nesting: `.navbar .container` gets flex for overall layout, and `.nav-links` gets flex for arranging individual link items.

## Milestone 4: Responsive Design

**Breakpoints chosen and why:**
- **768px (mobile):** Hamburger menu appears, navigation slides in from right, cards stack to 1 column. This is the standard mobile breakpoint where touch targets and single-column layouts work best.
- **900px (tablet):** Attraction cards shift from 3 columns to 2 columns. This intermediate breakpoint prevents cards from becoming too narrow on tablet screens.
- **480px (small mobile):** Further reduced font sizes and padding for phones. Hero height drops to 400px to show more content above the fold.

**One section where mobile needed to feel different:**
- The navigation completely transforms on mobile - instead of horizontal links, a hamburger menu triggers a slide-in drawer from the right. This isn't just "smaller desktop" but a genuinely different mobile-first interaction pattern with smooth animations.

**One Claude suggestion about breakpoints (accepted/rejected):**
- **Accepted:** Claude suggested using `playsinline` attribute on the hero video for iOS Safari compatibility. This prevents the video from forcing fullscreen on mobile Safari, crucial for the hero overlay design to work.

## Stretch Features

**1. Embedded Video (Hero Background)**
- Added Everest.mp4 as autoplay, looping hero background video
- **Why:** Creates an immersive, dynamic first impression that static images can't match. The moving prayer flags and mountain views immediately communicate Nepal's spiritual and natural beauty.
- **Technical:** Used `autoplay muted loop playsinline` attributes for cross-browser compatibility

**2. Google Fonts (Multiple Custom Fonts)**
- Imported 4 Google Fonts: Playfair Display, Cinzel, Poppins, Lora
- **Why:** Creates visual hierarchy and personality. Elegant serifs (Playfair, Cinzel) for headings evoke tradition, while modern sans-serif (Poppins) for body ensures readability.
- **CSS Property not covered:** `letter-spacing` used extensively (1-2px on headings) to create elegance and improve readability

**3. Enhanced Layouts - CSS Grid**
- Used CSS Grid for photo gallery (`grid-template-columns: repeat(3, 1fr)`) and food cards (`grid-template-columns: repeat(auto-fit, minmax(350px, 1fr))`)
- **Why:** Grid provides better control over gallery layout than Flexbox, and `auto-fit` with `minmax` creates truly responsive cards without media queries

**4. Google Maps Embeds**
- Embedded Google Maps iframes in accommodation cards showing hotel locations
- **Why:** Helps visitors understand proximity to attractions. Maps are 250px height, integrated seamlessly below accommodation info

**5. Interactive Navigation (Hamburger Menu with Animations)**
- Hamburger menu transforms into X when opened
- Slide-in animation from right with backdrop
- **CSS Property:** `transform: rotate(45deg) translate(8px, 8px)` for hamburger-to-X animation
- **JavaScript:** Event listeners for click-outside-to-close functionality

**6. Advanced CSS Properties Not Covered:**
- `backdrop-filter` considered (browser support issue)
- `object-fit: cover` on all images/video for consistent aspect ratios
- `text-transform: uppercase` on logo for brand consistency
- Box-shadow layering: `0 8px 24px rgba(0, 0, 0, 0.15)` for depth
- Gradient backgrounds: `linear-gradient(135deg, #c65d3b, #a0522d)` for badges

**7. Deployment Preparation**
- Local Python server for testing: `python3 -m http.server 8000`
- Ready for GitHub Pages, Netlify, or Vercel deployment






## Problem 1: Understanding Navigation Bar Placement
**What I Asked:** "How is navigation bar added in the HTML" and "Where is usually navigation bar added?"

**My Approach:** 
- I had a basic HTML file with just a heading
- I was confused about where to place the `<nav>` element

**What I Learned:**
- Navigation bars go **right after the opening `<body>` tag**, before main content
- The `<nav>` element is semantic HTML for navigation sections
- Structure: `<header>` → `<nav>` → main content

**Decision Made:** Place `<nav>` inside `<header>` at the top of every page for consistency

---

## Problem 2: "Cannot GET /top_attractions.html" Error
**What I Asked:** "Why am I not able to connect the different pages in home page"

**My Approach:** 
- I created navigation links in index.html
- Clicked on "Top Attractions" and got an error

**What I Learned:**
- Links in HTML point to files: `<a href="top_attractions.html">`
- If the file doesn't exist, browser shows "Cannot GET" error
- **Key concept:** Navigation creates a "doorway" but the "room" (file) must actually exist

**Decision Made:** Create all 4 HTML files (index, top_attractions, accomodation, photo_gallery) before testing navigation

---

## Problem 3: Understanding Page Connections
**What I Asked:** "How do I connect the different pages and make them consistent in styling?"

**My Approach:** 
- I wasn't sure how pages "talk to each other"
- I wondered about `#` vs filenames in href attributes

**What I Learned:**
- **`href="filename.html"`** = Loads a different page (new file)
- **`href="#section"`** = Jumps to a section on the SAME page
- **Shared CSS file** = All pages link to `css/styles.css` for consistent styling
- Each page needs the SAME navigation bar so users can move between pages

**Decision Made:** 
1. Use multi-page structure (separate HTML files)
2. Include identical navigation on all pages
3. Link all pages to the same CSS file

---

## Problem 4: Navigation Links Stacking Vertically
**What I Asked:** "How do I align my navbar to be in the top in horizontal?"

**My Approach:** 
- I set `display: flex` on `.navbar`
- Links were still stacking vertically, not horizontally

**What I Learned:**
- **Flexbox only affects direct children, not grandchildren**
- Structure was: `.navbar` → `.container` → `.nav-links` → `<li>` items
- The `<li>` items are children of `.nav-links`, NOT `.navbar`
- Need to set `display: flex` on `.nav-links` to make the list items horizontal

**HTML Structure I Used:**
```html
<nav class="navbar">              ← Has flex
    <div class="container">       ← Child of navbar
        <ul class="nav-links">    ← NEEDS flex to make <li> horizontal
            <li><a>Home</a></li>
            <li><a>Attractions</a></li>
        </ul>
    </div>
</nav>
```

**CSS Solution:**
```css
.navbar .container {
    display: flex;                    /* Logo left, nav-links right */
    justify-content: space-between;
    align-items: center;
}

.nav-links {
    display: flex;          /* THIS makes <li> items horizontal */
    flex-direction: row;
    gap: 2rem;
    list-style: none;
}
```

**Decision Made:** Use two flex containers - one for navbar layout (logo vs links), one for the links themselves

---

## Problem 5: Request for Complete HTML Structure
**What I Asked:** "Just write all my html code"

**My Approach:** 
- I was getting overwhelmed with questions and concepts
- I wanted to see the complete structure first

**What Happened:**
- Claude created all 4 HTML pages with proper semantic structure
- Each page has: `<header>`, `<nav>`, `<main>`, `<section>`, `<footer>`
- Content matched my planning.md specifications

**What I Should Have Done Differently:**
This was a **missed learning opportunity**. Better prompts would have been:

### 🎯 Better Prompting Strategies:

**Instead of:** "Just write all my html code"

**I Should Have Asked:**
1. **"Show me the HTML structure for ONE page (index.html) and explain each semantic element's purpose"**
   - Would have learned why `<header>`, `<main>`, `<section>` are used
   
2. **"Let me try creating top_attractions.html myself, then review my code and suggest improvements"**
   - Would have practiced writing HTML myself
   - Would have gotten feedback on my mistakes

3. **"Show me a template structure, then I'll fill in the content for each page"**
   - Would have understood the repeating pattern
   - Would have practiced writing content

4. **"Walk me through creating one attraction card, then I'll create the other 6"**
   - Would have learned the pattern once
   - Would have reinforced learning by repetition

---

## HTML Structure Decisions

### 1. Why I Used `<article>` for Attraction Cards
**Decision:** Each attraction card uses `<article class="attraction-card">`

**Why `<article>` instead of `<div>`?**
- An article is **self-contained** and **independently distributable**
- Each attraction can stand alone (has title, image, description)
- Semantically meaningful for screen readers and SEO
- Better than generic `<div>` which has no meaning

### 2. Why I Used `<figure>` and `<figcaption>` in Gallery
**Decision:** Gallery items use `<figure>` with `<figcaption>`

**Why this structure?**
```html
<figure class="gallery-item">
    <img src="..." alt="...">
    <figcaption>Caption text</figcaption>
</figure>
```

- `<figure>` is specifically for images with captions
- `<figcaption>` is semantically linked to the image
- Better accessibility than `<div>` + `<p>`
- The HTML itself communicates the relationship between image and caption

### 3. Navigation Structure Decision
**Decision:** Every page has identical navigation inside `<header>`

**Why?**
- **User expectation:** Navigation should be consistent across pages
- **Ease of maintenance:** Change once, update everywhere (later can use templates)
- **Accessibility:** Screen reader users expect navigation in the same place

---

## Things Claude Changed From My Original Planning

### 1. Changed "Local Food" to "Accommodations"
**Original plan:** One nav link said "Local Food"  
**What Claude did:** Changed to "Accommodations" to match the actual content  
**Why:** The guide page is about where to stay, not food  
**My reaction:** This made sense - content and navigation should match

### 2. Removed "Contact" Page
**Original plan:** Had a contact.html link  
**What Claude did:** Removed contact page from final structure  
**Why:** Not part of the core milestone requirements (Home, Attractions, Guide, Gallery)  
**My reaction:** Could add this later as a stretch feature

### 3. Added Semantic HTML5 Elements Throughout
**Original plan:** Didn't specify semantic vs div structure  
**What Claude did:** Used `<header>`, `<main>`, `<section>`, `<article>`, `<footer>`  
**Why:** Semantic HTML improves accessibility and SEO  
**My reaction:** Good practice I should continue

---

## How This Session Helped Me

### ✅ Concepts I Now Understand:
1. **Navigation architecture:** How multiple pages connect via href links
2. **File structure:** Each page = separate HTML file with same navigation
3. **CSS consistency:** One CSS file shared across all pages
4. **Flexbox hierarchy:** Parent flex doesn't affect grandchildren
5. **Semantic HTML:** Using meaningful tags (`<nav>`, `<article>`, `<figure>`)

### 🔄 What I Need More Practice With:
1. Writing HTML structure from scratch
2. Understanding when to use semantic elements vs `<div>`
3. Debugging CSS layout issues myself
4. Creating modular, reusable HTML patterns

### 💡 Better Learning Approach for Next Time:
1. **Ask for examples first, then try myself**
2. **Request explanations BEFORE seeing the code**
3. **Work on one small piece at a time** (one card, one section)
4. **Ask "why this approach over alternatives?"** when reviewing code
5. **Request "explain like I'm 5" breakdowns** of complex concepts

---

## What's Next

### Completed ✅
- [x] All 4 HTML pages created with proper structure
- [x] Navigation bar added to all pages
- [x] Basic navbar CSS (horizontal layout, fixed to top)

### Still To Do 📋
- [ ] Test all navigation links work by clicking through
- [ ] Add full page styling (hero section, cards, gallery)
- [ ] Create images folder and add placeholder images
- [ ] Apply earthy color palette throughout
- [ ] Make gallery horizontal scroll work
- [ ] Test responsive design on mobile

---

## Reflection: How I Could Have Prompted Better

### ❌ What I Did (Less Effective):
> "Just write all my html code"

**Why this was less effective:**
- Skipped understanding the structure myself
- Missed opportunity to practice
- Didn't learn the "why" behind decisions
- Can't replicate this on my own later

### ✅ What I Should Have Done (More Effective):

**Step 1: Understand Before Building**
> "Before we code, explain the structure of a multi-page website. What files do I need? How do they connect? Draw me a diagram."

**Step 2: Learn One Pattern**
> "Show me how to create ONE attraction card with proper semantic HTML. Explain why you chose each element."

**Step 3: Practice the Pattern**
> "Now I'll create the other 6 attraction cards myself using that same pattern. Review my code and tell me what I got wrong."

**Step 4: Build Understanding**
> "Why did you use `<article>` instead of `<div>` for the cards? What's the difference? When should I use each?"

**Step 5: Debug Together**
> "My navigation links aren't working. Help me debug by asking me questions so I learn how to troubleshoot this myself."

### 🎯 Key Principle for Better Learning:
**"Teach me to fish, don't just give me fish"**

- Ask for **explanations** before solutions
- Request **one example**, then practice the rest myself
- Ask **"why?"** questions about every decision
- Request **comparisons**: "Why X over Y?"
- Ask to **debug together** rather than getting fixes

---

## Final Note to Future Me

When I look back at this project, remember:
- **Fast ≠ Learning:** Getting code quickly doesn't mean I learned it
- **Struggle = Growth:** Being confused is part of learning
- **Ask "Why?":** Every time Claude makes a choice, ask why
- **Practice Matters:** Reading code ≠ writing code
- **Debug First:** Try to fix problems myself before asking for solutions

The goal isn't a finished website. The goal is **understanding how to build websites.** 


Topattraction Page: Used claude to learn how cards are generated, used that piece of code to replicate many cards in the page