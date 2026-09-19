---
name: travelpin-investor-update
description: >-
  Write Travelpin angel/investor product updates in a factual, glanceable style.
  Use when the user asks for an investor update, angel update, September/monthly
  update for investors, or status update for an early investor.
---

# Travelpin investor update

## Voice

Write as **Satish in the first person (“I”)**. Do not use corporate “we” unless referring to Travelpin the product/company in a clearly impersonal way (e.g. “Travelpin explains rights”).

Do **not** emphasise solo headcount (“one engineer”, “without a larger eng team”) — the investor already knows.

## Reference example

Canonical glanceable page path when publishing (unlisted; do not link from site nav/sitemap unless asked):

`travelpin-website/update/YYYY-MM/` → `https://travelpinapp.com/update/YYYY-MM/`

**Do not leave sensitive updates as plaintext on the public website repo.** Prefer AES/code-gated pages (`update/YYYY-MM/` with a shared numeric access code), or a private copy under `TPOpenApi/docs/`. Only publish ungated when the user explicitly wants a public URL.

**Never push the website to production unless the user explicitly asks to deploy / push / publish.** Local preview only by default.

Long draft may live under `TPOpenApi/docs/` — polish the **website HTML** for sending.

## Workflow

1. Gather from git (last ~2–4 weeks across `tpiosdev` + `TPOpenApi`) + what the user says shipped / gated.
2. Draft **glanceable HTML** (or tighten an existing page): summary cards → metrics → feature sections → architecture → next → asks.
3. Prefer facts over story. Cut drama in a pass before showing the user.
4. Leave metrics as `[ fill in ]` unless the user supplies production numbers — never invent MAU/trips.
5. If publishing to the website: **unlisted only** (`noindex, nofollow`), **no** homepage/nav/footer/sitemap links, unless the user explicitly asks to link it.

## Tone (hard rules)

| Do | Don't |
|----|--------|
| Factual headlines: “Product progress: X, Y, Z” | Clever drama: “Two shipped. One held back — on purpose.” |
| State what the product does | “Calm card”, “least served”, “co-pilot”, pull-quote rhetoric |
| “Not released” / “UI gated” with a reason | “Held back on purpose” as a punchline |
| Advisory language for rights: “may apply” | Absolute “you are owed” in investor claims about the product |
| Professional curation: “research”, “classify”, “publish” | Screenshots, OCR, “Panjim vs Panaji”, internal naming nits |
| Economics of a choice (why Google Flights deep link vs paid API) | Feature poetry |

Investors buy judgment and leverage, not vibes. Withholding a broken planner is a **decision** — state the field failure and the path to release, not a morality play.

## Structure (default)

1. **Header** — Travelpin · Update · Month Year · byline. No “Investor” on the page.
2. **Subscription model** — Free as short text under the eyebrow; three cards: Yearly · Monthly · Weekly (prices). Model before product narrative.
3. **Metrics** — MAU, trips, repeat, infra/trip — fill-ins until verified.
4. **This period** — 1–2 sentence lede + summary cards (Released / Not released).
5. **Per shipped feature** — what it does · scope · delivery · stack · material risks · economics if relevant.
6. **Partnerships under evaluation** — partner model, fit, status (no BD ask-lines in the status cell).
7. **Manual day planning** — separate shipped section. Traveller-owned itinerary (add / reorder / plan by day). Do **not** fold this into Plan My Day.
8. **Plan My Day** — AI-assisted only; gated. Field failures + decision + path to ship. Cross-reference that manual planning is the live path, without merging the two sections.
9. **Architecture** — stack and shipping targets; cost controls; offline critical paths. No “one engineer” boast.
10. **Next 30 days** — bullets with outcomes (product + marketing / GTM as relevant).
11. **Asks** — intros, testers, legal, pricing input — specific and actionable.

Use key-value rows and short bullets. Avoid walls of prose. No artificial `max-width: NNch` that wraps text early inside a wider sheet.

## Feature writing checklist

For each feature include only if true and useful:

- **What shipped** (user-visible behaviour)
- **How it works** (1–2 lines, not a design essay)
- **Unit economics / cost control** (caches, deep links vs metered APIs)
- **Issues hit and fixed** (investor-relevant reliability, not trivia)
- **Stack** (short)
- **Open decisions** (gated features, partnership eval)

## Curation / content ops

Frame as research and owned shortlists:

- Research → Classify (see / outdoors / eat / coffee) → Structure (hubs + area chips) → Publish (hybrid merge, ratings)

Never list individual POI names as “examples” in investor copy — hubs + process are enough; place laundry lists look like filler.

## AirHelp (and similar partners)

When discussing claims partners:

- What they do (eligibility, file/chase, escalate)
- Business model (no-win no-fee %; skip tax/VAT minutiae unless the investor asks)
- Fit for Travelpin (e.g. EU/UK outbound yes; India domestic DGCA often no)
- Status: **evaluating** unless a deal exists
- Guardrail: rights stay advisory; disclose if referred; airline direct claim remains available

## Anti-patterns (reject on sight)

- App Store traveller-voice marketing in an investor memo
- Internal bug nicknames as section titles
- Overclaiming “built and verified end to end” without certainty
- Inflating differentiation with “nobody else can…” unless narrowly true
- Filling metrics from guesswork
- Vanity eng metrics (e.g. “676 lines of tests”) — investors care that it failed in the field and why, not LOC of XCTest
- “One engineer” / team-size flex — they already know
- Corporate “we” when the author is a solo founder — use “I”
- Linking an unlisted investor URL from the public site

## Output

- Default: update or create the glanceable HTML on `travelpin-website`
- Share URL pattern: `https://travelpinapp.com/<unlisted-slug>.html`
- Do not push or create PRs unless the user asks
