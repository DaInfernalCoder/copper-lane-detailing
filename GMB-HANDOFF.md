# Copper Lane Mobile Auto Detailing Houston Texas

## Requested outcome

Build and launch a polished, phone-first mobile auto detailing website and Google Business Profile asset pack for Houston, Texas, end to end, following the make-gmb workflow.

## Confirmed facts

- Canonical name: Copper Lane Mobile Auto Detailing Houston Texas
- Business type: mobile auto detailing
- Primary market: Houston, Texas
- Street address: 2409 Maconda Ln, Houston, TX 77027
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
- [x] Define the Copper Lane design direction.
- [x] Source licensed local imagery and record sources.
- [x] Build the static website.
- [x] Run preflight and browser QA at desktop and phone widths, including header contrast.
- [x] Initialize git, commit, create GitHub repository, and push `main`.
- [x] Deploy through Vercel and connect the GitHub repository.
- [x] Attach apex and `www` and delegate DNS to Vercel.
- [ ] Verify authoritative DNS, HTTPS, production content, and call/booking links.
- [x] Write the GMB description and build/validate the final image pack.

## Current state

Site is built, QA'd, committed, and live on Vercel production (`READY`).

- Repository: https://github.com/DaInfernalCoder/copper-lane-detailing (public, `main`)
- Vercel project: `copper-lane-detailing` (prj_GBDOX4Jhc3Rt7VIw84imHg3wYFpZ), GitHub-connected
- Apex and `www` are both assigned to the project (`domain_already_assigned` confirmed)
- Spaceship nameservers set to `ns1.vercel-dns.com` / `ns2.vercel-dns.com` via the Spaceship
  API (`PUT /domains/{domain}/nameservers`); Spaceship's own record confirms `provider: custom`
  with those two hosts. No browser automation was needed.
- Public resolvers and the `.shop` registry had not yet published the new nameservers as of
  2026-07-16. This is propagation, not a failed change (Spaceship documents up to 48 hours).
- GMB pack validated and installed at
  `/Users/sumit/Documents/gmb/Copper Lane Mobile Auto Detailing Houston Texas`
  (1 logo 1200x1200, 4 covers 1920x1080 16:9, 4 business photos, DESCRIPTION.txt 641/750 chars
  with the service keyword in all 5 sentences, SOURCES.txt).

### Design record

Warm copper (`#b5642f`) to verdigris (`#2f7a68`) palette on cream (`#f7f1e8`) and warm ink
(`#17120e`), Fraunces display over Public Sans body, DM Mono for markers. Signature element is
the dashed copper "lane stripe" rule between sections, echoed in the logo mark. Deliberately
unlike Glass Harbor's teal/cyan/coral grotesque treatment.

### Bugs found and fixed during QA (do not regress)

1. The generic `section { padding-block }` rule applied to `.hero`, exposing a black band of
   the ink background between the header and the hero image. `.hero` now sets `padding-block: 0`.
2. The hero's "Book online" button used `.btn-outline` (ink text, dark border) on the dark hero,
   rendering it invisible at every viewport. It now uses `.btn-outline-cream`. Every cal.com link
   was then re-checked programmatically against its real computed background.
3. The footer logo was near-black on the dark footer: `logo.svg` used `fill="currentColor"`, but
   an SVG loaded through `<img>` cannot inherit page `color`, so `color: var(--cream)` did nothing.
   Fixed with a separate `assets/logo-cream.svg`; both logo SVGs now bake their colors in.

## Blocker

None. Only DNS propagation is outstanding, which is a wait and not an action.

## Exact next action

Poll authoritative DNS until `ns1.vercel-dns.com` / `ns2.vercel-dns.com` are public for
`copperlanedetailing.shop`. Then run:

```bash
python3 ~/.claude/skills/make-gmb/scripts/check_live.py copperlanedetailing.shop "Copper Lane"
python3 ~/.claude/skills/make-gmb/scripts/check_live.py www.copperlanedetailing.shop "Copper Lane"
```

Confirm HTTPS, the brand text, `tel:+13466439249`, and the cal.com booking links through the real
custom domain.

## Related

Glass Harbor's handoff still has one open task: authoritative DNS/HTTPS verification was never confirmed after nameserver delegation. Worth closing out separately.
