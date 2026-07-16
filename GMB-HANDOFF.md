# Copper Lane Mobile Auto Detailing Houston Texas

## Requested outcome

Build and launch a polished, phone-first mobile auto detailing website and Google Business Profile asset pack for Houston, Texas, end to end, following the make-gmb workflow.

## Confirmed facts

- Canonical name: Copper Lane Mobile Auto Detailing Houston Texas
- Business type: mobile auto detailing
- Primary market: Houston, Texas
- Phone: +1 346-643-9249 (Houston 346 area code)
- Primary conversion: phone calls; booking link is the required secondary path
- Booking link: https://cal.com/sumitdatta/auto-detail-service
- Domain: `copperlanedetailing.shop`
- Domain status: registered 2026-07-16, expires 2027-07-16, `lifecycleStatus: registered`
- Registration settings: one year, high privacy with consent, `autoRenew: false` (verified on the live record)
- Spaceship credentials: macOS Keychain only; never copied into this file or the repository

## Decisions and constraints

- Name screened for local and same-category conflicts before purchase; no Houston or national detailer using "Copper Lane".
- Visual identity must stay distinct from the three existing Houston-area detailing builds (Fresh Ride, Glass Harbor, Prairie Gloss). Copper Lane uses a warm copper-to-verdigris palette and a serif display face; Glass Harbor uses teal/cyan/coral with a grotesque.
- Dependency-free HTML, CSS, and JS. No lead form and no SMTP: the business is phone-first, so public email routes stay off the site.
- Every call CTA is paired with the cal.com booking link (header, hero, mid-page, final CTA, footer, mobile sticky bar). Calling stays primary emphasis; booking is secondary. Plain links only, no cal.com embed script.
- Copy says "call or book online" — never "call first" or "phone-first" while a booking link is offered.
- Do not invent an address, prices, reviews, certifications, guarantees, hours, service radius, staff, or completed-work claims.
- Licensed stock photography for launch imagery only; record every source; never imply stock photos show Copper Lane's own work.
- Header gets its own opaque/scrim background so contrast never depends on hero image content.
- Deploy via a dedicated public GitHub repository connected to Vercel; attach apex and `www`; delegate Spaceship DNS to Vercel nameservers.

## Acceptance criteria

- `copperlanedetailing.shop` registered with high privacy and auto-renew off.
- Permanent repository at `/Users/sumit/Documents/websites & apps/copper-lane-detailing`.
- Responsive, accessible, honest site using +1 346-643-9249 everywhere, with both booking paths on every CTA cluster.
- Preflight and desktop/mobile browser checks pass: no broken assets, console errors, overflow, or unreadable header.
- Clean `main` pushed to a dedicated GitHub repository and connected to Vercel.
- Apex and `www` serve the intended site over HTTPS through the real custom domain.
- GMB pack at `/Users/sumit/Documents/gmb/Copper Lane Mobile Auto Detailing Houston Texas` meets file-count and dimension requirements.

## Task list

- [x] Screen the Copper Lane name for local and same-category conflicts.
- [x] Confirm `copperlanedetailing.shop` available and non-premium.
- [x] Obtain explicit purchase approval from Sumit.
- [x] Register the domain with high privacy and auto-renew off.
- [x] Verify asynchronous registration success and `autoRenew: false`.
- [x] Confirm the business phone number.
- [ ] Define the Copper Lane design direction.
- [ ] Source licensed local imagery and record sources.
- [ ] Build the static website.
- [ ] Run preflight and browser QA at desktop and phone widths, including header contrast.
- [ ] Initialize git, commit, create GitHub repository, and push `main`.
- [ ] Deploy through Vercel and connect the GitHub repository.
- [ ] Attach apex and `www` and delegate DNS to Vercel.
- [ ] Verify authoritative DNS, HTTPS, production content, and call/booking links.
- [ ] Write the GMB description and build/validate the final image pack.

## Current state

Domain registered and verified. Project folder created. Design direction and build not started.

## Blocker

None.

## Exact next action

Define the Copper Lane design direction (palette, type pairing, layout thesis, signature patina element), then source licensed imagery into `assets/`.

## Related

Glass Harbor's handoff still has one open task: authoritative DNS/HTTPS verification was never confirmed after nameserver delegation. Worth closing out separately.
