What location is your travel guide about?
Ans: Nepal

Why did you choose it? (grew up there, dream destination, hidden gem?)
Ans: Grew up there





2. Your Audience
Who is this guide for? (e.g. backpackers, families, solo travelers, luxury travelers, students)
Ans: First time visitors

What do you want visitors to feel when they land on your site?
Ans: Cozy and warm(similar to the redbricks vibe in durbar squares in Kathmandu) , mystic, nature and ethereal





3. Home Page
What heading/tagline will welcome visitors? (e.g. "Discover the Magic of Kathmandu")
ANs:Discover the Magic of Kathmandu

Will you use a photo, video, or hero background for your visual?
Ans: I want to use all of them

Do you have a vibe/mood in mind? (e.g. adventurous, cozy, tropical, cultural)
Ans: Mix of cozy and nature and warmth





4. Top Attractions Page
What are your 3+ attractions? List them:
- Attraction 1: Patan Durbar Square
- Attraction 2: Lumbini
- Attraction 3: Everest
- Attraction 4: Bandipur
- Attraction 5:  Upper Mustang-The Desert-Himalayan "Glamping" & Ancient Cave Circuit
- Attraction 6: Chitwan National Park
- Attraction 7: The Tsum Valley- A Spiritual Wellness Haven

How do you want them laid out? (horizontal row, vertical stack, grid of cards?)
Ans:gird of carsa





5. Guide Page — Pick One:

Accommodations Guide
List your 3 entries:
- Entry 1: (Ghar+ fits someone who is looking for a homestay vibe)
- Entry 2: (Swarga + fits high end luxury clinets)
- Entry 3: (Pauna + fits mid range customers)
- Entry 4: (bas + somebody looking for cheap or affordable stay)





6. Photo Gallery
How many photos are you planning? (min 5)
ANs: 10
Layout preference: (grid, masonry, horizontal scroll, slideshow?)
ANs: scroll

Do you have the photos already, or are placeholders fine for now?
Ans: No pictures rn





7. Navigation Bar
Preferred nav style: (top horizontal bar, side drawer, hamburger menu on mobile?)
Ans: top

Any logo or site name for the nav?
Ans: Darsan

Color preference for the nav? (dark, light, transparent over hero?)
Ans:Color = warm light brick color similar to the brick monuments in Kathmandu that gives warm and cozy feeling.



8. Design & Style
Any color palette in mind? (e.g. earthy tones, ocean blues, vibrant/bold)
Ans: Earthy mud

Any websites that inspire your design? (e.g. Airbnb, Lonely Planet, National Geographic)
 https://www.shutterstock.com/video/clip-17080396-patan-nepal--may-31-2016-walk-on?dd_referrer=https%3A%2F%2Fwww.google.com%2F

Font vibe: (modern & clean, elegant & serif, bold & playful?)
ANs: Modern and with the theme





9. Stretch Features (check any you plan to do)
Embed a map, video, or song : video
CSS Grid layout on a page
Dropdown navigation menu
Newsletter signup form
Deploy the site publicly : yes
Google Font + custom CSS: can try



10. Anything Else?
Any specific interactions or details you want the wireframe to capture?: not as of now
Any features you want to avoid?: not as of now

---

## Design Intent (Added for Milestone 2)

**Color palette that reflects Nepal:**
Three words: **Warm, Earthy, Heritage**
- Primary: #c65d3b (warm brick red - inspired by Kathmandu's red brick monuments)
- Secondary: #a0522d (sienna brown - earthy mountain tones)
- Background: #f5f0e8 (soft cream - warm and inviting)
- Accent: #9c6644 (terracotta - cultural warmth)

**Typography (heading font / body font):**
- **Headings:** Playfair Display & Cinzel (serif fonts that evoke elegance, tradition, and cultural heritage)
- **Body:** Poppins (modern, clean sans-serif for excellent readability)
- **Subtext/Descriptions:** Lora (readable serif for longer content, balances modern and traditional)

**One visual choice that connects to destination's identity:**
Hero video background of Everest with prayer flags - immediately communicates Nepal's spiritual essence and natural grandeur. The video creates movement and life, reflecting the dynamic culture while the overlay ensures text remains readable.

---

## Flexbox Layout Plan (Added for Milestone 3)

### Home Page Layout:

**Navigation Section:**
- **Content:** Logo on left, 5 navigation links on right
- **Arrangement:** Horizontal flex container with space-between
- **Desktop:** All links visible in a row with gaps
- **Mobile:** Hamburger menu replaces links, which slide in as vertical drawer

**Hero Section:**
- **Content:** Full-width video background with centered text overlay
- **Arrangement:** Flexbox for vertical and horizontal centering of text
- **All screens:** Maintains aspect ratio, video scales responsively

**Welcome Section:**
- **Content:** Heading and two paragraphs of text
- **Arrangement:** Centered text block, max-width 900px
- **Mobile:** Reduced font sizes and padding

**Highlights Section:**
- **Content:** 3 feature cards (Ancient Heritage, Himalayan Wonders, Warm Hospitality)
- **Arrangement:** Flex container with wrap, gap 30px
- **Desktop (1200px+):** 3 cards in a row (flex: 1 1 300px, max-width 350px)
- **Tablet (768px):** Cards wrap naturally based on screen width
- **Mobile (480px):** Single column stack
- **Important:** Equal spacing between cards maintained by gap property

### Attractions Page Layout:

**Cards Container:**
- **Content:** 7 attraction cards with image, badge, title, description, button
- **Arrangement:** Flex wrap with 3 columns on desktop
- **Desktop:** 3 cards per row (flex: 1 1 calc(33.333% - 24px))
- **Tablet (900px):** 2 cards per row (flex: 1 1 calc(50% - 24px))
- **Mobile (600px):** 1 card per column (flex: 1 1 100%)
- **Spacing:** Gap 24px creates consistent spacing that adapts

### Accommodations Page Layout:

**Accommodations Container:**
- **Content:** 4 hotel cards with info section and embedded map
- **Arrangement:** Flex wrap with 2 columns on desktop
- **Desktop:** 2 cards per row (flex: 1 1 calc(50% - 24px))
- **Mobile (968px):** Single column (flex: 1 1 100%)
- **Important:** Each card uses flex-direction: column to stack info above map

### Food Page Layout:

**Food Container:**
- **Content:** Multiple food cards with image, badge, title, tagline, description, facts
- **Arrangement:** CSS Grid (not Flexbox) - auto-fit minmax(350px, 1fr)
- **Why Grid:** Better for equal-height rows, auto-fit handles responsiveness without media queries
- **All screens:** Cards flow naturally, always maintaining minimum 350px width

### Photo Gallery Layout:

**Gallery Grid:**
- **Content:** 6+ images with captions (figure/figcaption elements)
- **Arrangement:** CSS Grid 3 columns on desktop
- **Desktop:** grid-template-columns: repeat(3, 1fr)
- **Tablet (768px):** 2 columns
- **Mobile (480px):** Single column
- **Why Grid over Flexbox:** Gallery needs consistent grid structure, not flexible wrapping

---

## Breakpoints Plan (Added for Milestone 4)

**Three device sizes:**

1. **Mobile: max-width: 768px**
2. **Small Mobile: max-width: 480px** 
3. **Tablet: max-width: 900px** (for attraction cards)

### Major Section Changes at Each Breakpoint:

**Navigation Bar:**
- **Desktop (>768px):** Horizontal nav links visible, logo on left
- **Mobile (≤768px):** Hamburger menu appears, nav links hidden in slide-in drawer from right side
- **Why different:** Touch targets need to be larger on mobile, and horizontal space is limited

**Hero Section:**
- **Desktop:** 600px height, h1 at 3.5rem, p at 1.5rem
- **Tablet (≤768px):** 500px height, h1 at 2.5rem, p at 1.2rem
- **Mobile (≤480px):** 400px height, h1 at 2rem, p at 1rem
- **Why:** Reduces hero height on mobile to show more content above fold

**Welcome Section:**
- **Desktop:** Padding 80px, h2 at 2.5rem
- **Tablet (≤768px):** Padding 60px, h2 at 2rem
- **Mobile (≤480px):** Padding 40px, h2 at 1.8rem, body text 0.95rem
- **Why:** Maintains visual hierarchy while fitting smaller screens

**Attraction Cards:**
- **Desktop (>900px):** 3 columns
- **Tablet (≤900px):** 2 columns
- **Mobile (≤600px):** 1 column
- **Why:** 3 columns become too narrow on tablet, need intermediate breakpoint

**Photo Gallery:**
- **Desktop:** 3-column grid
- **Tablet (≤768px):** 2-column grid, images 200px height
- **Mobile (≤480px):** Single column, images 250px height
- **Why:** Maintains image impact while adapting to screen width

**Accommodations:**
- **Desktop:** 2-column layout
- **Mobile (≤968px):** Single column, map height reduced to 200px
- **Why:** Maps need adequate height to be useful, 2 columns on mobile would make them too small

### Mobile Experience That Feels Meaningfully Different:

**Navigation Interaction:**
- Desktop: Hover effects on nav links (underline animation)
- Mobile: Tap hamburger → smooth slide-in drawer from right with backdrop, tap outside or close icon to dismiss
- **Why different:** Mobile needs touch-optimized menu with clear open/close states

**Hero Video:**
- Desktop: Full 600px immersive video
- Mobile: Reduced to 400px with `playsinline` attribute to prevent iOS fullscreen takeover
- **Why different:** Mobile users scroll faster, need to see content sooner; also prevents video controls from dominating screen