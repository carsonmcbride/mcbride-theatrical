# McBride Theatrical Consulting — site

`index.html` is the whole site. No build step, no dependencies. Double-click to open it,
or drag it onto any host (Netlify, Cloudflare Pages, GitHub Pages) to publish.

## Before it goes live

Search `index.html` for **REPLACE** — there are 5 markers left.

| What | Where | Notes |
|---|---|---|
| Email address | Contact section + the `mailto:` in the script | Appears twice |
| Phone number | Contact section | |
| Booking link | `id="bookLink"` | Point at Calendly/Cal.com, or delete the list item |
| ~~Portrait of Michael~~ | ✅ done | `images/michael-mcbride.jpg` |
| Testimonial | Quote section | Replace the placeholder text and attribution |
| Form destination | `<form id="contactForm">` | See below |

### Wiring the contact form

Right now the form opens the visitor's email client. To collect real submissions,
sign up at [formspree.io](https://formspree.io) (free tier) and change the form tag to:

```html
<form action="https://formspree.io/f/YOUR_ID" method="POST">
```

…then delete `id="contactForm"` so the mailto script stops intercepting it.

## Photos — the highest-value thing to fix

**Every image is a temporary placeholder** from Wikimedia Commons, each marked with a
small "Placeholder" ribbon on the page. They need to come out before launch.

Priority order, since the top of the page does the most work:

1. **Christmas with the Tabernacle Choir** — the featured full-width card. This is the
   single most valuable image on the site. A wide shot of the full stage in a big look
   — choir, orchestra, bells, brass all lit — is the shot that sells the practice.
2. **The European tour** — a hall photo from 2016 with his rig visible.
3. Everything else.

The portrait is done. The current headshot is good and appropriate for a consultant — but if
he has a candid at the console or on the deck, that's worth swapping in later. Working
photos say "designer"; headshots say "executive." Replace `images/michael-mcbride.jpg`
and the page picks it up with no code change.

### Replacing them

Put real photos in an `images/` folder next to `index.html`, then for each card:

```html
<img src="images/christmas-concert.jpg" alt="...">   <!-- swap the src -->
```

…and delete that card's `<span class="ph-flag">Placeholder</span>` line.

Landscape 3:2 at roughly 1600px wide is right for the grid cards; the featured card wants
something wider, 16:9 or so. When every photo is swapped, delete the image-credits
paragraph in the footer.

### Why not just use Church photos

Photographs of the Conference Center, Christmas concerts, temple open houses, and pageants
are, with few exceptions, owned by the Church (Intellectual Reserve, Inc.) and aren't
licensed for use on a commercial consulting site. The current stand-ins are Creative
Commons images, which is why the footer carries an attribution block — but they're
generic, not Michael's. Which brings up the real question below.

## The guest artist roster

The "On That Stage" section lists 44 guest artists across 25 Christmas concerts,
2000 through 2025 (2020 was cancelled for COVID). Sourced from Church News.

Two things to keep intact when editing it:

- **It's framed as production credits, not endorsements.** The heading says who has been
  on that stage during his tenure — not that they hired him or vouch for him. The
  disclaimer below the list says so explicitly. Listing artists you've lit is completely
  standard on a designer's credits; implying a relationship you don't have is not.
  Keep the framing, keep the disclaimer.
- **Trim it to what's his.** The list currently covers the full run of Christmas concerts
  at the Conference Center. If any of those years predate his involvement or were designed
  by someone else, cut them. A shorter accurate list is worth more than a long one he has
  to walk back on a call.

## Worth confirming with Michael

- **Rights to his own work.** Photos taken in the course of his employment may belong to
  his employer, and the Christmas concert in particular is tightly controlled. Worth
  finding out what he can show publicly and what needs written permission — this is the
  one item that could hold up launch. The affiliation disclaimer in the footer is there
  for the same reason.
- **The commissioning angle is the headline now.** "Helped bring the building online"
  is the framing throughout — deliberately modest, since I don't know his exact role in
  2000. If he led the lighting commissioning rather than assisted, the copy should say so
  plainly; that's the single strongest thing on the page for a new-build client, because
  it's the exact problem they're hiring for. Conversely if "helped get it started up"
  meant something narrower, soften it before a prospect asks.
- **"60,000+ audience across a single Christmas run."** This comes from a reported figure
  for the 2017 concerts. He should confirm it's representative before it stays on the page.
- **International temple projects.** Same as above — the copy stays general. Naming two or
  three temples would strengthen it considerably.
- **Domain.** `mcbridetheatrical.com` is used as the example email domain throughout.
