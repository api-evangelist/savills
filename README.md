# Savills (savills)

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
