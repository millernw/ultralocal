# Design Direction: Make goultralocal.com Look Made by a Person

The current site works, but it looks AI-generated. This file tells you why that happens and exactly what to change. It sits on top of `VIBE-CODER-INSTRUCTIONS.md` and `ultralocal-brandscript.md` in the repo. Keep all the copy, pages, forms, and requirements from those files. **This file overrides them on layout and visual style wherever they conflict**, including the layout ideas in brandscript Part 2 (tile rows, eyebrow labels, checklists). Keep the words; you're free to change how they're laid out.

---

## 1. Why the site looks AI-made

When a model gets a vague visual direction ("retro," "fun," "vibrant"), it fills the gap with the average of every website it has seen. The result is technically clean and instantly forgettable: centered hero, three icon cards, a checklist, a testimonial row, another CTA. Same radius on everything, same spacing everywhere, everything fading in on scroll.

On this site there's an extra trap. "Neon on dark navy" is itself one of the most common AI looks: dark background, glowing accent text, glow on every heading. The brand really is neon, so the answer isn't to drop it. The answer is to treat neon the way a sign shop would: as one special object, not a filter over the whole page.

The fix isn't a trendier aesthetic. It's making specific decisions that a model wouldn't make by default, writing them down, and checking every section against them.

---

## 2. What's wrong with the current build

This is a review of the homepage at ultralocal-hub.vibepreview.app, checked at 1440px and 375px. Fix these first, in this order.

**1. The logo is broken everywhere.** The header and footer show a broken-image icon with "Ultra Local" alt text. The images point to files on `vibe.filesafe.space` that don't load. This alone makes the site feel generic, because the logo is the only thing carrying the brand. Bring the SVGs from the repo's `logos/` folder into the project and serve them from the site itself: horizontal neon in the header, stacked neon-glow in the hero, stacked neon or white in the footer. Check that they load at every width.

**2. There's no Ultra Local anywhere in the design.** Take the logo away and this is a dark-mode startup template: navy background, thin gray borders, small rounded cards, one gold button. None of the brand guide's cues show up: no ULTRA stripes, no gold arrow, no tube-color/neon-color pairing, no chalkboard, no pink at all. Sections 3, 4, and 7 below fix this.

**3. A monospace "code" font is all over the page.** The eyebrow labels, the hero board mockup, the card labels, and the footer headings are set in a system monospace font. That's a software-developer look, the opposite of a small-town sign shop, and the brand guide allows only Righteous and DM Sans. Remove every monospace font.

**4. The layouts are the stock AI ones:**
- Pill badge above the hero headline ("● SERVING NORTHEAST INDIANA SMALL BUSINESSES")
- A stat row under the hero buttons ($625 / 100% / 5,000+). "5,000+ monthly foot traffic" also reads as a real traffic claim you can't back up yet. Remove the row.
- A small uppercase label above every section heading (THE LOCAL PROBLEM, HOW IT WORKS, GET INVOLVED, COMMUNITY NOMINATIONS)
- "Old way / new way" as two bordered cards with ✕ and ✓ lists
- Three identical white cards numbered 01, 02, 03
- Checkmark lists in almost every section
- Centered heading plus centered subhead, repeated section after section
- Founder quote in a card with an "NM" initials circle, italic text, and a colored left border
- Thin 1px borders between every section and around every card

**5. It's almost all navy.** Four of the six sections are near-identical dark navy, and the two cream sections are the plainest ones on the page. Nothing about it is vibrant. Night Navy is one material among several, not the default.

**6. The hero board mockup looks like a dashboard widget,** not a chalkboard: a dark UI panel with monospace labels, a "Columbia City, IN" tag, and sponsor tiles named like real businesses (Miller HVAC, Cornerstone, Midwest Dental). Replace it with a real board photo. If you need a stand-in, use a clearly labeled placeholder frame. Any sample sponsor names must be obviously made up.

**7. Copy was added and brandscript sections are missing.** Lines like "A simple model where everyone wins," "365 Days of Visibility," "Zero cost, zero hidden catch," and "Ditch taped printer paper" aren't in the brandscript. The nomination form's button says "Submit Application." The homepage is also missing five brandscript sections: "Does anybody actually look at these?", stakes, the success picture, the Founding offer banner, and the FAQ preview. Restore them, using the brandscript copy, with the layouts in section 7.

**8. Forms.** The nomination form looks custom-built. The site should use the three HighLevel embeds from brandscript section 3.5, with clean placeholders until Nathan supplies the form IDs. Confirm where the current form actually sends its data.

What's working: the copy mostly follows the brandscript, the mobile toggle and sticky CTA bar are right, fonts are loading, there's no horizontal scroll on mobile, and gold buttons with navy text are correct. Keep those.

After fixing, screenshot every section at 375px and 1440px and check it against the list in section 5 before showing Nathan.

---

## 3. The art direction (be this specific)

**Not "retro." American Main Street signage and print from about 1950 to 1965, made by a sign painter and a small-town print shop.**

Ultra Local's founder has a graphic arts degree and co-founded a sign and wide-format graphics company. The site should feel like it was made by that person, not by a web template. Every visual decision should come from physical things you'd find on a small-town main street in that era:

- **Hand-painted shop signs and window lettering**: flat, confident color, strong outlines, drop-lines offset in a second color (not a blurry shadow)
- **Diner and soda-fountain menus**: price columns, dotted leaders between item and price, scalloped or rounded-corner card stock, specials clipped on
- **Changeable-letter marquees and letterboards**: black board, white letters, a little uneven
- **Chalkboard menu boards**: the actual product
- **Matchbooks, ticket stubs, raffle tickets, county fair posters, screen-printed show posters**: two or three flat spot colors, bold type, slight misregistration, halftone dots, paper texture
- **Neon tube signs**: the logo. One lit sign per page, like one sign in a window.

When you're unsure about a decision, ask: **"Would a 1960s sign painter or menu printer have made this?"** If the answer is "no, that's a software-website thing," don't do it.

---

## 4. Decisions to make and write down first

Before redesigning, create a `DESIGN.md` in the repo that records these decisions with a one-line reason for each. Every page must follow it. If you need something that isn't in it, add it to the file first.

1. **Surfaces.** Pick 3 or 4 "materials" and assign each section one: e.g., painted wall (flat Night Navy), menu card stock (Cream with subtle paper grain), chalkboard (the board itself), enamel sign (flat Neon Teal, Pink, or Gold field with Cream or Navy type). No section is "a navy div with glowing text."
2. **Color by section.** Each section uses a maximum of 2 to 3 flat colors from the brand guide, like a screen print. Write down which. Don't put all eight colors in every section.
3. **Type scale.** Righteous and DM Sans only (brand guide rule). Make them work harder through scale: headlines that are really big next to body text that's comfortably normal. Define a scale with at least 4 clearly different steps. Set big numbers and prices in Righteous like price cards in a diner window.
4. **Shapes and corners.** Define a radius scale on purpose. Suggestion: 0 for paper and print items (tickets, menus, posters), a small radius only for buttons and form fields. Allowed signature shapes, chosen from the era: ticket stub with notched corners, scalloped menu edge, arrow-shaped sign, pennant. Pick 2 or 3 and use them consistently.
5. **Shadows.** No soft, blurry drop shadows. If something needs lift, use a hard offset shadow in a solid brand color (like a sign's painted drop-line or a stacked paper card).
6. **Motion.** List every animation on the site and its purpose. If it has no purpose, cut it. See section 6.
7. **Layout map.** Assign each homepage section a different composition (see section 7). No two adjacent sections should share a layout.

---

## 5. Tells to remove

Find and remove every one of these.

**Neon and color**
- Glow on headings, buttons, borders, or cards. **Glow appears in one place per page: the logo in the hero.** Everywhere else the neon colors appear as flat color, the way paint does.
- Gradients of any kind: gradient text, gradient buttons, gradient backgrounds, radial "spotlight" halos, glowing orbs, blurry color blobs.
- Glassmorphism, frosted panels, and backdrop blur.
- Every section being dark. Alternate materials so the page has daylight in it.

**Layout**
- Centered hero with headline, subhead, two buttons, and an image, all stacked and centered.
- Rows of three identical cards with an icon on top, a heading, and a sentence (the problem tiles and success vignettes in the brandscript are the prime suspects; rebuild them as something from section 7).
- Every section having the same width, padding, and structure.
- Cards inside cards.
- Decorative grid-line or dot-pattern backgrounds.
- Tiny numbered section labels ("01 / 02 / 03") used as decoration.
- "Old way vs. new way" comparison cards with ✕ and ✓ lists.
- Thin 1px borders separating every section and outlining every card.

**Type**
- A small uppercase "eyebrow" label above every heading. Keep at most two on the whole homepage, and only where they carry real information (like FOR HOSTS / FOR SPONSORS at the split).
- A badge or pill above the hero headline.
- Headlines that are all the same size across sections (flat hierarchy).
- Any font besides Righteous and DM Sans on the page itself. **Especially monospace or "code" fonts.**
- Stat rows ("$625 / 100% / 5,000+") under the hero.
- Initials avatars (a circle with "NM") in place of a real photo.

**Components**
- The same border radius on everything, pill-shaped buttons everywhere, rounded-2xl cards.
- Hairline border plus soft wide shadow on cards.
- Green checkmark lists for every benefit. One checklist on the whole site, max.
- Icon tiles (an icon inside a rounded colored square) stacked above headings.
- Emoji used as icons, anywhere.
- Default component-library styling that looks like its documentation.

**Imagery**
- Stock photos, AI-generated photos, and 3D renders.
- Rough, generic, or clip-art SVG illustrations. A crude drawing looks worse than no drawing.
- Images buried under dark overlays.

**Motion**
- Fade-up-on-scroll applied to every section.
- Scale-up on hover for every card.
- Bounce or elastic easing.
- Auto-scrolling marquees or tickers.
- Pulsing dots or blinking cursors.

**Copy**
- Any text you added that isn't in the brandscript. Don't invent taglines, section intros, or filler sentences.
- Em dashes, "transform," "elevate," "unlock," "seamless," "effortless," and similar words.

---

## 6. Motion that belongs here

Motion should feel physical, like signs and buttons on a real street. Keep it to these:

- **The hero sign lights up once.** The neon-glow logo flickers on over about a second, like a tube warming up, then stays lit and still. Once per visit. Skip it with reduced motion.
- **Buttons press.** On hover the hard offset shadow gets a little smaller and the button moves toward it, like pressing a physical button. Quick, no bounce.
- **The host/sponsor toggle** on mobile slides like a sign flipping from one side to the other.
- **Links** get an underline drawn with the gold arrow motif.

Nothing else animates unless you can explain what it tells the user.

---

## 7. Composition ideas by homepage section

These keep the brandscript copy but give each section its own shape. Use them as a starting point; the rule is that every section gets a different composition, taken from a real object.

| Section | Composition |
|---|---|
| **Hero** | Asymmetric. A large real photo of an Ultra Local board installed in a host business, cropped with confidence, on one side. Headline set big in Righteous on a painted-wall surface on the other side. Neon-glow logo is the one lit sign. Buttons look like sign plaques with hard drop-lines. |
| **Problem** | A torn-out newspaper page or a "CLOSED" sign motif for "the local paper is gone." The three problems become a single typeset list, like items on a notice board, not three cards. |
| **The idea** | A diagram drawn like an old instruction sheet or sign-shop layout sketch: Host + Sponsors = Community, with the gold arrow connecting them. |
| **Founder quote** | Set like a signed note pinned to a board, or a large pull quote in Righteous with Nathan's real photo. No card around it. |
| **The split** | Two different materials side by side: host column on an enamel-teal sign surface, sponsor column on menu card stock with a pink accent. Each column clearly its own object. |
| **Sponsor price** | A diner price card: "ONE SPOT . . . . . . $625 / YEAR" with a dotted leader, and "about $52 a month" beneath. The price should be the biggest number on the page. |
| **"Does anybody look at these?"** | The chalkboard itself. The objection is written as if it's the board's "Today's Special," answered below. |
| **Stakes** | Two contrasting objects, not two cards: e.g., a crumpled online ad receipt vs. a year-long ticket stub. |
| **Success picture** | A short run of three snapshots with handwritten-style captions *set in DM Sans* (not a script font), or a single wide scene. Not three icon cards. |
| **Founding offer** | A marquee sign with changeable letters: "NOW BOOKING FOUNDING BOARDS." Static bulbs, no chasing animation. |
| **Nominate a spot** | A raffle ticket or suggestion-box card with the button as the "tear here" edge. |
| **FAQ preview** | Plain and clean. Good typography, generous spacing, simple accordions. Not everything has to be themed; the quiet sections make the loud ones work. |

Mix in plain sections deliberately. A page where every section is a costume looks like a theme park. Aim for roughly one "showpiece" section for every one or two plain, well-set sections.

---

## 8. Imagery rules

- **Real photos of real boards come first.** Nathan has some. Use the best one big in the hero, not as a small thumbnail.
- Where you need a board and don't have a photo, use a clearly placeholder frame labeled "Board photo coming soon" rather than a fake illustration. Nathan will fill them in.
- Texture (paper grain, halftone dots, a little chalk dust) is fine if it's subtle, low-contrast, and optimized. It should be something you notice only when you look for it.
- Slight imperfection is good: a ticket rotated 1 to 2 degrees, the second color on a drop-line offset a pixel or two. Keep it rare and deliberate. If everything is tilted, nothing is.

**Photo shot list to send Nathan** (so the site can drop placeholders fast):
1. A board installed in a host business, wide shot showing the room and people
2. A tight shot of the board with a day's specials written on it
3. Close-up of a single sponsor ad on the board
4. Someone reading the board (from behind or side, no faces needed)
5. The starter kit: chalk markers and eraser on a counter
6. Nathan installing a board
7. Nathan portrait for the founder quote and About page
8. Street-level shots of the northeast Indiana towns where boards are going

---

## 9. Review process before you show Nathan

For every section, screenshot at 375px and 1440px and run these tests:

1. **Tell check.** Go down the list in section 5. Zero tells allowed.
2. **Swap test.** Imagine putting a different company's logo on this section. If it would fit a SaaS startup or any generic brand just as well, it's not done.
3. **Sign painter test.** Could this section be described as a real physical object from a 1950s or 60s main street? If not, is it deliberately a plain, well-set section?
4. **Squint test.** Blur your eyes at the full homepage screenshot. You should see a clear rhythm of different shapes, materials, and light and dark, not a stack of identical rectangles.
5. **Glow count.** Exactly one glowing element per page.
6. **Copy check.** Every sentence traces back to the brandscript.

Then send Nathan the before and after screenshots side by side, section by section, with a line on what changed in each.
