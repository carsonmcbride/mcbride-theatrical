# McBride Theatrical Consulting — site

`index.html` is the whole site. No build step, no dependencies.

**Live at [mcbridetheatrical.com](https://mcbridetheatrical.com)** — hosted free on Cloudflare
Pages, connected to this repo. Any push to `main` redeploys automatically, usually in under a
minute. `www` redirects to the bare domain.

## Photos — the highest-value thing to fix

The work-card images are generic Creative Commons stand-ins from Wikimedia Commons, credited
in the footer. They aren't Michael's work, and they should come out.

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

Put real photos in `images/`, then for each card swap the `src`:

```html
<img src="images/christmas-concert.jpg" alt="...">
```

Landscape 3:2 at roughly 1600px wide is right for the grid cards; the featured card wants
something wider, 16:9 or so. Each `.work-media` has a gradient behind the image, so a card
still looks deliberate if a photo is slow or missing.

When every photo is Michael's own, delete the image-credits sentence in the footer.

## Contact and the form

The contact section lists an email and a location. The phone number and the "book a call"
link were removed rather than shipped as placeholders — add them back when there are real
values.

The form currently opens the visitor's email client and sends to
`michael@mcbridetheatrical.com`. To collect real submissions instead, sign up at
[formspree.io](https://formspree.io) (free tier) and change the form tag to:

```html
<form action="https://formspree.io/f/YOUR_ID" method="POST">
```

…then delete `id="contactForm"` so the mailto script stops intercepting it.

Mail for `@mcbridetheatrical.com` is handled by Cloudflare Email Routing — check the
Cloudflare dashboard if delivery stops.

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
  one item standing between the site and real photography. The affiliation disclaimer in
  the footer is there for the same reason.
- **The commissioning angle is the headline.** "Helped bring the building online"
  is the framing throughout — deliberately modest, since his exact role in 2000 isn't
  documented here. If he led the lighting commissioning rather than assisted, the copy
  should say so plainly; that's the single strongest thing on the page for a new-build
  client, because it's the exact problem they're hiring for. Conversely if "helped get it
  started up" meant something narrower, soften it before a prospect asks.
- **"60,000+ audience across a single Christmas run."** This comes from a reported figure
  for the 2017 concerts. He should confirm it's representative before it stays on the page.
- **International temple projects.** Same as above — the copy stays general. Naming two or
  three temples would strengthen it considerably.
