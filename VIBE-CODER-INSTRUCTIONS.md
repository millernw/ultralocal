# Build Instructions: goultralocal.com

You're building the website for **Ultra Local**, a northeast Indiana business that places free daily menu boards inside busy local businesses and sells the ad spots around each board to other local businesses. The owner is Nathan Miller. He has already done the strategy work. Your job is to turn it into a website that looks great, works on every device, and sounds like Ultra Local.

The technology is your call. Pick whatever stack and hosting you think fits best, as long as the result meets the requirements below. If anything in the source files suggests a specific framework or host, treat it as a suggestion, not a requirement.

---

## 1. Get the materials

Everything you need is in this repo:

**https://github.com/millernw/ultralocal**

Clone it and read these, in this order, before writing any code:

1. **`ultralocal-brandscript.md`** (repo root). The BrandScript and website brief. This is the source of truth for the message, the page structure, and the copy. Read all of it, including the Open Items at the end.
2. **`ultralocal-brand-guide.pdf`** (repo root; the same file is also in `logos/06-brand-guide/`). Nathan's brand guide: logo versions and when to use each, the color palette and what each color is for, the icon, clear space, minimum sizes, fonts, and don'ts. Open it and look at the pages, don't just skim the text. It's your main design reference (see section 4).
3. **`logos/README.txt`**. Explains every logo file, which one to use where on a website, and the file types.

Then open the logo files themselves and study them. Use them directly from `logos/`. Use the SVGs on the site wherever possible. The favicon set and install snippet are in `logos/04-favicon/`, and the social share image is in `logos/05-social/`. Don't redraw, recolor, stretch, or recreate the logo.

If the brandscript file isn't in the repo or has a different name, stop and tell Nathan. Don't build from memory or guess the content.

**What takes priority when sources disagree:**
1. What Nathan tells you directly
2. For message, structure, and copy: `ultralocal-brandscript.md`
3. For anything visual (logo, color, fonts, look): `ultralocal-brand-guide.pdf`, then `logos/README.txt`. Where the brandscript's design notes conflict with the brand guide, the brand guide wins.
4. Your own judgment

---

## 2. What you're building

The brandscript lays it all out. In short:

- **Seven pages:** Home, Host a Board, Sponsor a Board, Locations, About, FAQ, Contact. (Brandscript section 2.1.)
- **A long, story-driven homepage** that speaks to a general local visitor first, then splits into two columns: one for **hosts** (businesses that get a free board) and one for **sponsors** (businesses that buy ad spots). On phones the split turns into a toggle, so each visitor only sees their own side. (Section 2.2.)
- **Dedicated Host and Sponsor pages** that expand on the homepage columns and end with an application form. (Sections 2.3 and 2.4.)
- **A Locations page driven by a simple data file**, so Nathan can add a new board, update open spots, or list sponsors without touching layout code. (Section 2.5.)
- **Three HighLevel forms**, embedded with the iframe method: General/Nominate a Spot, Host Application, and Sponsor Application. Nathan will provide the form IDs. (Section 3.5.)
- **Board QR code support:** the Sponsor page reads a `board` URL parameter, highlights that board, and passes it through to the form. (Section 3.6.)

Use the written copy in the brandscript as written. You can shorten a line to fit a layout, but don't rewrite the message, change the offer, or add claims.

---

## 3. How to follow the spirit of the brandscript

The brandscript uses the StoryBrand framework. Nathan is a certified StoryBrand practitioner, so he'll notice when a build drifts away from it. Here's what that means for you.

### The customer is the hero, not Ultra Local
Every section should be about the visitor's problem and what their life looks like once it's solved. Ultra Local is the guide who helps. If a headline is about "us," "our mission," or "our innovative platform," it's wrong. Rewrite it around the visitor.

### Three heroes, in sequence
- **The Local** (anyone who cares about their town) hears the big story first: small businesses are getting drowned out by chains and big advertising, and Ultra Local brings it back to the neighborhood.
- Then the page **splits**. **The Host** wants an easy, good-looking way to keep customers up to date. **The Sponsor** wants to be the name locals think of first.
- Never mix host and sponsor messages in the same block. A pub owner shouldn't have to read about ad pricing to find out their board is free.

### There's a villain, and it's not a person
The villain is **Big Advertising and the chains it feeds**: pay-to-play ad platforms, algorithms, the endless scroll, and national franchises squeezing out local businesses. The site should be confident, even a little rebellious, about this. It should never sound bitter, and it should never attack a specific company by name.

### Clarity beats clever
Within five seconds on the homepage, a visitor should be able to answer three questions:
1. What does Ultra Local offer?
2. How does it make my life better?
3. What do I do next?

If the hero section can't pass that test, simplify it.

### Calls to action are everywhere and they never change
- Host: **Get a Free Board**
- Sponsor: **Claim Your Spot**
- General visitor: **Nominate a Spot**

Use these exact words every time. Repeat the main CTAs throughout the homepage and in the header. On mobile, keep the relevant CTA reachable at all times (see the sticky bar in section 3.7 of the brandscript).

### The price is a selling point, not something to hide
**$625 a year for one spot, about $52 a month.** Put it front and center in the sponsor column and on the Sponsor page. "One price, one year, no bidding, no clicks, no algorithm" is part of the pitch.

### Answer the big objection head-on
Every sponsor will wonder, "Does anybody actually look at these?" The brandscript includes a section that answers this. Give it real visual weight. Don't bury it in the FAQ.

### Honesty is part of the brand
Ultra Local is placing its first boards now. There are no testimonials, stats, or client logos yet.
- **Never invent** testimonials, reviews, numbers, sponsor names, or host names and present them as real.
- Build the proof sections (logos, stats, quotes) as components that **stay hidden until Nathan adds real content**.
- Board mockups can show sample ads, but the business names on them must be obviously made up.
- The "Founding Host / Founding Sponsor" framing is how the site handles being new. Use it as written.

### Voice
Friendly, plain-spoken, a little nostalgic, a little rebellious. Picture a diner owner who has opinions about chain restaurants. Short sentences. No hype. Avoid marketing jargon (leverage, elevate, unlock, solutions, impressions, omnichannel). Don't use em dashes in any copy you write.

---

## 4. Look and feel

Nathan has given no design direction beyond the logo, the brand guide, and this: **the site should be fun, exciting, unique, and vibrant.** That leaves the design to you, so build the whole visual system from what's in the logo and the brand guide. Don't reach for a generic template or a trendy SaaS look. If someone saw a screenshot of any section with the logo cropped out, they should still know it's Ultra Local.

### Design cues to take from the logo and brand guide

- **The mood is "Main Street after dark."** The logo is a 1950s and 60s neon sign, and the brand guide cover shows it glowing on Night Navy. Picture neon in a diner window, marquee lights, chalkboard menus, and cream-colored paper menus. Aim for warm, fun, and a little bold, never kitschy or costume-like.
- **Two lighting modes, straight from the guide.** The guide pairs every color: neon colors (Neon Teal, Neon Pink, Marquee Gold) for light backgrounds, and tube colors (Tube Teal, Tube Pink, Tube Gold) for dark ones. Build the site the same way. Dark Night Navy sections use tube colors and the neon or neon-glow logo. Light Cream sections use the neon colors and the color logo. Alternate the two down the page so long pages feel like walking from a neon-lit street into a bright diner and back.
- **The striped ULTRA lettering.** The parallel inline stripes in "ULTRA" are the most distinctive shape in the brand. Borrow them for dividers, section edges, card borders, background bands, button outlines, or big display numbers. Borrow the idea of the stripes, not the letters.
- **The gold arrow.** It points forward and says "go local." Use it as a recurring device: next to CTAs, as an underline under key words, as a scroll cue, or pointing from the split heading to each column.
- **The script "L" icon** works well as a small stamp, a bullet, a loading mark, or a sticker-style badge (for example, a "Founding Sponsor" seal).
- **Letterspaced small caps in gold**, like "BRAND GUIDE · LOGO, COLOR AND USAGE" on the guide's cover, are a good style for eyebrows, labels, and section tags.
- **Color roles from the guide:** Night Navy for dark backgrounds, Cream as the warm light background, Gold for accents. On the site, host content gets teal accents, sponsor content gets pink accents, and gold is for primary buttons, the price, and the arrow.
- **The product is a chalkboard menu board framed by ad tiles.** Use it as a recurring visual: in the hero, in the split section, and on the Locations cards.
- **Marquee bulbs** suit the Founding offer banner.

### Make it fun and vibrant without breaking the brand

- Go bold with scale: big headings, big color blocks, generous space.
- Neon glow belongs on the logo and large headlines on dark backgrounds only. Never on body text, never on light backgrounds.
- Motion should feel like a sign coming to life: a one-time neon "flicker on" for the hero logo, buttons that light up on hover, gentle reveals. Respect reduced-motion settings. No scroll-jacking or constant animation.
- Illustrations and icons should use simple rounded lines in the brand colors, the way neon tubes bend.
- Nathan has some real board photos and will add more. Until then, use an illustrated board mockup. **No generic stock photos**, especially of big-city storefronts or corporate offices. They contradict the whole brand.

### Brand guide rules you must follow

- Use only the eight colors in the guide. No new hues. Tints and transparencies of palette colors are fine.
- **Fonts:** Righteous for headings, DM Sans for body text. **Monoton and Yellowtail appear only inside the logo. Never set text in them.** The brandscript mentions Yellowtail as an accent font; ignore that and follow the brand guide.
- Use the right logo version for the background: color on light, neon on dark, neon glow on screens (it's fine on the website), white over photos.
- Keep ULTRA, Local, and the arrow together. Don't stretch, squash, rotate, recolor, or add drop shadows or other effects to the logo. Don't retype it.
- **Clear space:** leave empty space around the logo of at least twice the arrowhead's height on every side.
- **Minimum size:** stacked 200px wide, horizontal 280px wide. Smaller than that, use the icon.
- Don't put the logo on busy or low-contrast backgrounds.
- The icon is for small spaces only (favicon, tiny mobile header). It doesn't replace the full logo anywhere the full logo fits.

### Readability

The contrast rules in brandscript section 3.2 were checked against this palette, so follow them exactly. Body text is always cream on navy or navy on cream. Teal, pink, and gold are not readable as text on cream. Primary buttons are gold with navy text.

---

## 5. Requirements

- **Mobile first.** Most visitors arrive from a text message or a QR code on a board. Design for a phone first, then scale up. No horizontal scrolling at any width.
- **Fast.** Optimize images, lazy-load anything below the fold, and keep scripts light.
- **Accessible.** WCAG AA contrast, real buttons and links, visible focus states, alt text on every image, titled form iframes.
- **SEO basics.** Page titles and meta descriptions (suggestions are in section 3.7 of the brandscript), Open Graph tags using the share image from `logos/05-social/`, and LocalBusiness structured data.
- **Easy for Nathan to edit.** Keep page copy and board data in clearly labeled, easy-to-find places, separate from layout code. Nathan should be able to change a headline, add a board, or paste in a form ID without hunting through components.
- **Placeholders are visible, never invented.** Anything marked `[TBD]` in the brandscript (phone, email, form IDs, board dimensions, and so on) should render as an obvious placeholder, or hide gracefully, until Nathan fills it in. If a form ID is missing, show a clean "Form coming soon" box instead of a broken embed.
- **Analytics-ready.** Make it easy to add a tracking ID later, and tag every CTA and form so clicks and submissions can be tracked by type.

---

## 6. How to work with Nathan

1. **Start with a short plan.** Before building, send Nathan the page list, the homepage section order, your approach to the mobile split, a short description of the visual system you've drawn from the logo and brand guide (how you'll use the stripes, the arrow, the two lighting modes, the board motif), and any questions. Keep it short.
2. **Build the homepage first**, all the way through, including the two-column split and the mobile toggle. Share it for feedback before building the other pages. Every other page borrows from it.
3. **Then build** Host, Sponsor, Locations, About, FAQ, and Contact.
4. **Ask when the message is at stake.** If something would change the offer, the price, the promise, or the voice, ask. Make ordinary design and technical calls yourself.
5. **Don't resolve the Open Items yourself.** The brandscript lists open questions (board-removal policy, spots per board, category exclusivity, ad size, board dimensions). Leave those as placeholders unless Nathan answers them.

---

## 7. Before you hand it off

Check each of these yourself, and tell Nathan the result:

- [ ] Homepage passes the five-second test: what it offers, why it matters, what to do next
- [ ] Every section speaks to the visitor as the hero; Ultra Local shows up only as the guide
- [ ] Host and sponsor messages never mix; the mobile toggle works
- [ ] CTA wording is identical everywhere: Get a Free Board / Claim Your Spot / Nominate a Spot
- [ ] $625/year (about $52/month) is prominent in the sponsor column and on the Sponsor page
- [ ] The "Does anybody actually look at these?" section is present and visible
- [ ] No invented testimonials, stats, or business names; empty proof sections are hidden
- [ ] Logos come from the repo files, unaltered, with the right version for each background, proper clear space, and at least the minimum sizes
- [ ] Only the eight brand guide colors are used; Monoton and Yellowtail appear nowhere outside the logo
- [ ] The design clearly borrows from the logo (stripes, arrow, neon/tube pairing, board motif) and would still read as Ultra Local with the logo cropped out
- [ ] It feels fun, exciting, unique, and vibrant, not like a template
- [ ] Contrast rules followed; site works cleanly on a phone
- [ ] All three form slots are in place (live or placeholder), and the `board` parameter works on the Sponsor page
- [ ] Nathan can edit copy and board data without touching layout code
- [ ] No em dashes or marketing jargon in any copy you wrote

When you finish, give Nathan a short summary: what you built, how to add a board, where to paste each form ID, how to edit copy, and a list of every remaining placeholder.
