# Revision 2: Conversion, Trust, and the Last AI Tells

This is a review of ultralocal-hub.vibepreview.app (homepage and /sponsor, checked at 1440px and 375px). The last round was a big step forward: the logo loads, real board photos are in, the monospace font is gone from the homepage, the missing brandscript sections are back, and there's more cream in the page rhythm. Keep all of that.

This round has three goals, in this order:
1. **Stop losing visitors and leads** (things that break conversion outright)
2. **Make visitors feel safe** (a small-town business owner should feel like they're dealing with a real local person)
3. **Remove the remaining AI tells**

Keep following `ultralocal-brandscript.md`, `VIBE-CODER-INSTRUCTIONS.md`, `DESIGN-DIRECTION.md`, and your `DESIGN.md`. Where this file conflicts with them, this file wins. Items marked **[Nathan]** need an answer from Nathan; leave a visible placeholder until he gives it.

---

## Part 1: Conversion blockers (fix first)

### 1.1 The page is blank for about 5 seconds
In testing, the homepage showed an empty navy screen for roughly 5 seconds before anything appeared, on both desktop and mobile (first contentful paint about 5.4s). Most visitors from a QR code or a text message will leave before it loads. Some of this may be the preview host, but check for:
- Anything that hides the page until fonts load (use `font-display: swap`, and never gate rendering on `document.fonts.ready`)
- The neon "warm-up" animation or any intro effect holding back the rest of the page. The headline, subhead, buttons, and photo must be visible immediately. Only the logo flickers, and the page must not wait for it.
- A full-page loader, or an opacity-0 starting state on the page wrapper

**Target:** hero text and buttons visible in under 1.5 seconds on a mid-range phone. Measure before and after, and report both numbers.

### 1.2 Make sure every form actually delivers leads
The site uses custom-built forms, not the HighLevel embeds in brandscript section 3.5. There are no iframes on the homepage or the Sponsor page. If these forms don't send to HighLevel, every lead is being lost.
- Either replace them with the three HighLevel form embeds, or wire the custom forms into HighLevel (webhook or API) so each submission creates a contact tagged `host`, `sponsor`, or `nomination`. Your choice, but they must end up in HighLevel.
- Submit a test entry through each form and confirm with Nathan that it arrived. Then show a clear thank-you state that says what happens next (see 2.3).
- Fix the button labels. They all say "Submit Application," including on the nomination form. Use:
  - Host form: **Request My Free Board**
  - Sponsor form: **Claim My Spot**
  - Nomination form: **Nominate This Spot**

### 1.3 The subpages didn't get the redesign
/sponsor still has the monospace pill badge above the headline ("★ FOR LOCAL SERVICE BUSINESSES & PROFESSIONALS") and the old dark-template look. Apply `DESIGN.md` to every page: /host, /sponsor, /about, /faq, /contact, and /locations. Check each one against the tell list in `DESIGN-DIRECTION.md`.

### 1.4 The Sponsor page is too thin to close the sale
This is the page that makes money, and right now it's hero, board list, form. A sponsor about to spend $625 needs a few more answers before the form. Add, in this order, using brandscript copy (section 2.4):
1. Hero (keep)
2. The "Does anybody actually look at these?" answer
3. How it works (pick your board, approve your ad, a year of being seen) **plus the renewal explanation**
4. What's included in the $625 (the rate card belongs here, not on the homepage; see 3.2)
5. Available boards (keep)
6. Sponsor FAQ (short, 4 to 6 questions)
7. The form

Apply the same logic to /host: hero, what you get, how it works, Yes and No lists, board size and mounting, Host FAQ, form.

### 1.5 Bring back the Locations page
The nav no longer links to /locations, but board data already exists (E Brewing, South Whitley). Restore the page and the nav link. A real place with a real name is the strongest proof the site has right now.

---

## Part 2: Make people comfortable

For a local business owner, comfort comes from knowing there's a real person nearby who will pick up the phone. Right now the site has almost none of those signals.

### 2.1 Show a real person
- Replace the founder card's pink dot with a real photo of Nathan. **[Nathan: headshot]**
- Put a phone number in the header (tap-to-call on mobile) and in the footer. For this audience, a visible local phone number is worth more than any design flourish. **[Nathan: phone number]**
- Add "Call or text Nathan" near each form as an alternative to filling it out.

### 2.2 Name the real board
The hero photo caption reads "Ultra Local menu board in northeast Indiana." If E Brewing has agreed to be named, change it to "Now live at E Brewing, South Whitley" and link it to /locations. Do the same anywhere a board photo appears. **[Nathan: confirm E Brewing can be named, and which photos are from there]**

### 2.3 Say what happens after they submit
Anxiety at the form is the #1 reason people don't submit. Under each form button, add one line, and repeat it on the thank-you state:
- Sponsor: "Nathan will call you within [1 business day] to confirm your board and your ad. Nothing is billed until you approve your ad." **[Nathan: confirm response time and when billing happens]**
- Host: "Nathan will reach out within [1 business day] to set up a quick visit and measure your space." **[Nathan: confirm]**
- Nomination: "Thanks. We'll reach out to them and let you know if a board goes up."

Replace "Your information stays local with Ultra Local & Systematic Marketing. Zero spam." with: "We'll only use this to follow up about your board. No mailing lists."

### 2.4 Label the hero buttons by who's clicking
The two hero buttons compete, and a first-time visitor may not know which one is theirs. Add a small line above or under each:
- Above **Get a Free Board**: "Own a busy spot?"
- Above **Claim Your Spot**: "Want your business on a board?"

### 2.5 Photos must be real, and not repeated
- The "For the sponsor" photo in "Picture this a year from now" is a product render on a white background. It reads as a stock mockup. Replace it with a real photo, or a real close-up of a sponsor ad on a board.
- The same restaurant photo appears in the hero and again in "For the host." Use each photo once.
- **[Nathan: confirm every board photo on the site is a real installed board.]** If any are AI-generated or digitally composited, remove them. On this site, a fake-looking photo costs more trust than having no photo.
- The hero sits on a darkened, blurred photo background. That's a common template move (an image buried under an overlay). Use a flat Night Navy "painted wall" surface instead and let the real board photo on the right do the work.

### 2.6 Keep the guarantee honest
/sponsor says "Guaranteed 12 months of display." Until the board-removal policy is settled (what happens if a host closes or pulls the board mid-year), soften it to "A full 12 months on the wall," or add the policy to the Sponsor FAQ. **[Nathan: board-removal policy]**

---

## Part 3: Remaining AI tells

### 3.1 One box style everywhere
Almost every section is now the same object: a rectangle with a thick border and a hard offset shadow in gold, teal, or navy. The offset shadow was supposed to be a special detail. Used on nine boxes in a row, it's become the new template. Limit it to **two or three elements on the whole homepage** (for example: the hero photo frame, the sponsor price card, and the marquee). Everything else should sit directly on the section surface with no box, or use a different object from `DESIGN-DIRECTION.md` section 7.

### 3.2 Cut repetition and tighten the homepage
The homepage is about 9,000px tall on desktop and 11,400px on mobile, and several sections repeat each other:
- **Stakes** ("Keep doing it their way" vs. "Do it the Ultra Local way") restates the problem section, and it's the ✕/✓ comparison-card pattern flagged as a tell. Remove it, or fold its headline ("Every dollar spent with a corporation is a dollar that leaves town.") into the problem section as a closing line.
- The **rate card** repeats the price box already in the sponsor column. Move the rate card to /sponsor and keep just the price box on the homepage.

Suggested homepage order after cuts:
1. Hero
2. Problem (ending with "Every dollar spent with a corporation...")
3. The idea (Host + Sponsors = Community)
4. Founder quote with a real photo
5. The split (host / sponsor)
6. "Does anybody actually look at these?"
7. Picture this a year from now
8. Founding boards marquee
9. FAQ preview
10. Nominate a spot

### 3.3 Specific tells still on the page
- **Checkmark lists:** the host column uses checkbox-style ticks, the objection section has a row of "✓ HIGH FOOT TRAFFIC VENUES / ✓ DELIBERATE DAILY READS / ✓ UNSKIPPABLE REAL-WORLD PRESENCE," and the stakes section uses ✓ and ✕. Keep one list on the whole page (the host "what you get"), styled like items written on a chalkboard or a menu, not checkboxes. Remove the rest.
- **Three identical cards** in "Picture this a year from now." Make it one wide photo with the three short captions beside or under it, or three photos of different sizes in a loose, hand-placed arrangement. Not three matching boxes.
- **"01. 02. 03." numbering** in the problem list. The three problems aren't a sequence. Drop the numbers.
- **Everything is centered.** Nearly every section has a centered heading, a centered paragraph, and a centered box. Left-align most sections, and let a few break the grid (for example, the objection headline big and left, the answer offset to the right).
- **"Does anybody actually look at these?"** is still a bordered box. Per `DESIGN-DIRECTION.md`, make it the chalkboard: the question written as the board's "Today's Special," with the answer below.
- **The Founding marquee** is a box with a row of dots on top. Either make it a real marquee sign (bulbs all the way around, changeable-letter style text) or make it a simple bold gold band across the page. The in-between version reads as a template.
- **Mobile hero:** the logo appears twice at the top (the header logo plus the big neon logo), which pushes the board photo below the fold. On mobile, drop the hero neon logo and show the photo directly under the buttons.

### 3.4 Copy that isn't from the brandscript
These lines were added. Remove them or send them to Nathan to approve:
- "THREE THINGS BROKEN ABOUT MODERN LOCAL ADS" and "Main Street Notice"
- "Stop paying and you vanish instantly." / "or step foot in your shop" / "viral videos, and automated algorithms"
- The labels in the idea diagram ("Chalkboard, supplies, zero cost ever," "4x6 spots seen every single day," "Neighbors hire neighbors")
- "Straightforward answers for hosts and sponsors."
- "Free ad design assistance if needed" and "Optional direct QR code to your phone/web" (the brandscript wording is "Send us your 4x6 artwork or we'll design it for you. Add a QR code if you'd like.")
- "Nathan will reach out to confirm ad artwork and board placement!" (no exclamation points; replace with the line from 2.3)

---

## Part 4: Check before you send it back

Report each of these to Nathan with a yes or no:

- [ ] Hero text and buttons appear in under 1.5 seconds on a phone (report the before and after numbers)
- [ ] A test submission from each of the three forms arrived in HighLevel with the right tag
- [ ] Every page follows `DESIGN.md`, with no monospace font and no pill badges anywhere
- [ ] /sponsor and /host have the full sections from 1.4; /locations is back in the nav
- [ ] Phone number in the header and footer; real photo of Nathan (or visible placeholders)
- [ ] "What happens next" line under every form and on every thank-you state
- [ ] No photo is used twice; no renders or mockups; hero background overlay removed
- [ ] Hard offset shadows on no more than three elements on the homepage
- [ ] Stakes section and homepage rate card removed; homepage follows the order in 3.2
- [ ] Only one list on the homepage; no ✓/✕ rows; no "01/02/03"
- [ ] Most sections left-aligned
- [ ] Every sentence traces to the brandscript or has Nathan's approval
- [ ] Before-and-after screenshots of every changed section at 375px and 1440px
