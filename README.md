# Savills (savills)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Savills plc is a London-headquartered global real estate advisor, established in 1855, listed on the London Stock Exchange, with more than 42,000 people in over 70 countries. It sits on the advisory side of the property value chain rather than the data-platform side: commercial and prime residential agency, transaction advisory and capital markets, valuation and professional services, building and project consultancy, property and facilities management, rural and agricultural advisory, occupier services, the Savills Research publication programme, and a separate fund manager in Savills Investment Management. Its home market is the United Kingdom, where there is no MLS and no cooperative listing standard — residential stock reaches consumers through the Rightmove and Zoopla duopoly by way of agency CRM software (Reapit, Alto, Street, Apex27) rather than a shared cooperative pool. Savills is a supplier into that pipe, not an operator of it. Its API posture is the honest null case for this sector. Savills publishes no developer portal, no API documentation, no SDK, no Postman collection and no machine-readable contract of any kind.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/savills/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/savills/refs/heads/main/apis.yml)

## Tags

- Real Estate
- United Kingdom
- Commercial Real Estate
- Property Listings
- Valuation
- Property Management
- Brokerage
- Rentals
- PropTech
- Investment Management

## Timestamps

- **Created:** 2026-07-26
- **Modified:** 2026-07-26

## APIs

None. Savills publishes no documented public API.

Every conventional developer entry point was probed on 2026-07-26 and every one failed:

- `developer.savills.com`, `developers.savills.com`, `docs.savills.com` and `apis.savills.com` do not resolve in DNS.
- `api.savills.com` resolves and answers in JSON, but returns `{"statusCode": 404, "message": "Resource not found"}` on every path tried — an API gateway with no public routes.
- `/developers`, `/api`, `/docs`, `/openapi.json`, `/swagger.json`, `/api-docs` and `/.well-known/openid-configuration` all return 404 on `savills.com`, `savills.co.uk` and `savills.us`.
- The 82 KB sitemap at `https://www.savills.com/sitemap.xml` (HTTP 200) contains zero `developer`, `/api`, `swagger` or `openapi` paths.

Savills does run internal APIs. The property search front end loads [`https://search.savills.com/js/endpoints.js`](https://search.savills.com/js/endpoints.js) (HTTP 200), which names four of them by hostname — `livev6-searchapi.savills.com`, `livev6-authentication.savills.com`, `livev6-profile.savills.com` and `assets.savills.com`. All of the service hosts return 404 anonymously, none serves an OpenAPI, Swagger or OData `$metadata` document, and none is documented anywhere public. The estate is private by construction, not gated behind a licence.

## RESO Posture

**Not certified. No RESO reference found anywhere in the Savills estate.**

The official RESO certified-organization list at [https://www.reso.org/certificates/](https://www.reso.org/certificates/) (HTTP 200) was searched for Savills, Savills Inc and Savills plc — no match, and no UK entries at all. `https://certification.reso.org/` returned HTTP 400 to an anonymous client. No OData `$metadata` document exists (probed on `api.savills.com` and `livev6-searchapi.savills.com`, both 404), and no Universal Property Identifier appears anywhere.

This is structural rather than a lapse. RESO is a North American NAR/MLS mechanism, the UK has no MLS to certify against, and Savills' US arm (formerly Savills Studley) is a commercial real estate services firm rather than a residential MLS participant.

## Access Gate

**`none-published`.** There is no developer signup, no application form, no partner programme page, no data licence, no sandbox, no API terms of use and no key issuance process published anywhere on `savills.com`, `savills.co.uk`, `savills.us` or `savillsim.com`. The only published route to any Savills data conversation is the general corporate contact form at [https://www.savills.com/contact-us/](https://www.savills.com/contact-us/). Classifying this as `partner-only` would imply a partner programme exists; none is published.

## Open Data

**No.** Savills publishes no open, unlicensed, publicly callable dataset. Savills Research ships as PDF reports and web narrative at [https://www.savills.com/insight-and-opinion/](https://www.savills.com/insight-and-opinion/) — no data download, no CSV, no feed, no API.

The genuinely open UK property layer sits in the public sector and is not operated by Savills: HM Land Registry Price Paid Data under the Open Government Licence, and Ordnance Survey's addressing and mapping open products. This is the structural inverse of the United States — the UK has no industry standard and no MLS, but it does have real open government property APIs, and none of them come from the brokerages or the portals.

## Auth Model

**None published.** No authentication scheme is documented because no API is documented. OIDC discovery was probed anonymously on three hosts and returned 404 on all of them, including `https://livev6-authentication.savills.com/.well-known/openid-configuration` — the authentication service the consumer property search actually calls. No API key scheme, no OAuth2 flow, no SAML member-portal entry point, and no `security.txt`.

## Webhooks, Events, SDKs, Postman

Absence across the board, and that is the finding:

- **Webhooks:** none documented.
- **Events:** no event bus, no streaming, no AsyncAPI, no WebSocket surface.
- **SDKs:** none. `https://github.com/savills` returns 404 — there is no Savills GitHub organization.
- **Postman:** no official collection or workspace.
- **Changelog / status page / rate limits / sandbox:** none.
- **`llms.txt` / `ai-plugin.json`:** neither exists. Savills' `robots.txt` does actively disallow CCBot and SemrushBot, which is the only machine-access posture the company publishes.

## Common Properties

- [Website](https://www.savills.com/)
- [Savills United Kingdom](https://www.savills.co.uk/)
- [Savills United States](https://www.savills.us/)
- [Savills Property Search](https://search.savills.com/list)
- [Investor Relations](https://ir.savills.com/)
- [Insight & Opinion](https://www.savills.com/insight-and-opinion/)
- [Contact](https://www.savills.com/contact-us/)
- [LinkedIn](https://www.linkedin.com/company/savills)
- [Savills Investment Management](https://savillsim.com/)

## Review

The full probe trail — 68 recorded URLs with HTTP status, the RESO evidence, the access gate, the open-data finding and the auth model — is in [review.yml](review.yml).

## Maintainers

- Kin Lane &lt;kin@apievangelist.com&gt;
