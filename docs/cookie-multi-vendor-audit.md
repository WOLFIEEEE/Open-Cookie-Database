# Cookie additions audit — 20 September 2026

Branch: `cookie-multi-vendor-additions`. Reviewed starting commit: `7b4d86c0d572fdf83ea10534d664053eef149d5d`. Base: `749c37c` (`origin/master`).

All **236 original additions** were reviewed against vendor cookie tables, product documentation and, where the documentation was incomplete or inconsistent, public vendor source code. The review covered names and capitalization, provider attribution, domain scope, purpose, category, retention, privacy links and prefix matching.

| Outcome | Original rows |
| --- | ---: |
| Corrected | 165 |
| Verified without a change | 59 |
| Removed or consolidated into an existing rule | 12 |
| Total reviewed | 236 |

The result is **224 additions** and **2,490 total database rows**. All **2,266 base rows are byte-for-byte unchanged**. A corrected row can have more than one changed field; the number of corrected rows is not a count of independent errors.

The [row-by-row audit](cookie-multi-vendor-audit.csv) contains one record for every original addition, identified by its original UUID, with its outcome, final provider/name, changed fields, reasoning and source URLs. UUIDs were preserved for retained records. The [source link index](cookie-multi-vendor-sources.md) makes every reference individually clickable and records its access-check result.

## Duplicate and wildcard decisions

The final data has no duplicate UUIDs. No addition duplicates another record's `(Platform, Cookie / Data Key name)` or `(Cookie / Data Key name, Domain)` combination, and no addition creates overlapping prefix rules for the same provider. Comparisons respect case-sensitive cookie names; domain comparisons also normalize leading dots, domain lists and legacy third-party annotations.

| Original entry | Action and coverage retained |
| --- | --- |
| BigCommerce `authjs.session-token` | Keep the Auth.js implementation entry once. Catalyst uses that library cookie. |
| FreeWheel `uid-bp-41393` | Already covered by the base FreeWheel `uid-bp-` prefix for the same domain family. |
| PrestaShop `PHPSESSID` | Already covered by the base PHP.net session-cookie entry. |
| Okta `JSESSIONID` | Already covered by the base J2EE session-cookie prefix; the added entry did not document a different purpose. |
| Mouseflow `mf_user` | Merge into `mf_`; preserve both the session identifier and the 90-day returning-visitor flag. |
| PerimeterX `_pxde`, `_pxff_`, `_pxhd`, `_pxmvid`, `_pxttld`, `_pxvid` | Merge six overlapping rows into `_px`, including the separate published lifetimes. `pxcts` remains separate because its name does not share that prefix. |
| Moodle `MoodleSessionTest` | Merge the documented legacy cookie-support check into the `MoodleSession` family; retain its session lifetime. |

Seven cookie names also occur under other providers: `fid`, `cid`, `lang`, `tu`, `remember_me`, `t` and `JSESSIONID`. These are not duplicate records: their providers, domain scopes or documented purposes differ. In particular, LinkedIn documents `JSESSIONID` for CSRF protection on `.www.linkedin.com`, whereas the generic J2EE entry describes session management. The existing Adhese `cap` and Marfeel `_s` wildcard rules are restricted to unrelated vendor domains. Consumers must use domain and provider context, and prefer specific matches over generic framework fallbacks; name-only matching can conflate unrelated services.

## Substantive accuracy corrections

- **Provider attribution:** 20 entries previously labeled LinkedIn belong to Gainsight, Skilljar, Microsoft, Oracle, Sift or CVTrust. The five `sj_` entries describe Skilljar training, not SlideShare. The separate `_RequestVerificationToken` entry is now scoped to Microsoft Forms. Both Microsoft and LinkedIn publish that single-underscore name; it is intentionally distinct from the existing ASP.NET `__RequestVerificationToken` entry. [LinkedIn cookie table](https://www.linkedin.com/legal/l/cookie-table), [Microsoft privacy statement](https://www.microsoft.com/en-gb/privacy/privacystatement).
- **Cookie names:** correct AWS names to `CloudFront-Key-Pair-Id`, `CloudFront-Policy` and `CloudFront-Signature`; correct Wordfence to `wf_loginalerted_`; correct the current Moodle username prefix to `MOODLEID1_`; use Datadog's generated `dd_cookie_test_` and `dd_site_test_` prefixes. [AWS signed-cookie documentation](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/private-content-setting-signed-cookie-custom-policy.html), [Wordfence cookie notice](https://www.wordfence.com/cookies-notice/).
- **Authentication lifetimes:** NextAuth.js/Auth.js session tokens default to 30 days and can use database sessions as well as JWTs; nonce cookies expire after 15 minutes. Add prefix matching for session-token chunks. ClerkJS gives its session cookie a one-year browser expiration although the enclosed JWT is short-lived. `__client_uat` means Updated At; the application session cookie is written by JavaScript, while the separate Frontend API client cookie is HttpOnly. Source files are linked per row in the audit.
- **Other lifetimes:** Gainsight PX uses 30 minutes of inactivity for `apt.sid` and one year for `apt.uid`; Adobe's `getPreviousValue` expires after 30 minutes of inactivity; Wordfence publishes one-year login-alert/bypass cookies and a 12-hour WAF authentication cookie; PrestaShop defaults to 20 days. [Gainsight analytics cookies](https://support.gainsight.com/PX/Install_PX/Install_PX_Web/Analytics_Cookies), [Adobe getPreviousValue](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/plugins/getpreviousvalue).
- **Storage mechanisms and scope:** identify local/session storage in Squarespace, Acuity, HubSpot and Zendesk entries. Preserve Zendesk's browser-dependent durations and dual storage for article votes. The Smartlook `SL_C_` prefix covers both 13-month identifiers and immediately deleted domain-test cookies. Add the documented domains to entries sourced from particular deployments.
- **Descriptions and categories:** remove inferred mechanisms unsupported by the sources, including individual Salesforce chat-cookie roles and Stripe checkout-state claims. Product-recommendation data is categorized as Personalization; location-based content personalization, security and preference entries are categorized by their documented purpose.
- **Privacy links:** use LiteSpeed's actual policy instead of cache documentation, replace Smartlook's home-page redirect with its published privacy statement, use the current Commerce.com notice for BigCommerce, and normalize Gainsight PX to the verified policy URL. Provider changes also update the corresponding policy links. [LiteSpeed privacy policy](https://www.litespeedtech.com/company/privacy-policy), [Smartlook privacy statement](https://help.smartlook.com/docs/privacy-statement-full), [Commerce.com privacy policy](https://www.commerce.com/privacy/).

## Evidence limits recorded in the data

**27 retained entries now explicitly say `Not specified` for retention.** Their names and purposes are documented, but the cited source does not establish a lifetime. Other configurable, version-dependent or browser-dependent values are labeled accordingly. In particular:

- Squarespace still lists the historical fixed date January 1, 2025 for `_acloggedin` and `_client_acloggedin`. That does not establish their present-day lifetime.
- Adobe Commerce names many cookies without giving their individual retention periods. A purpose description alone does not establish session-only or persistent retention.
- HubSpot experiment-cache contents expire at experiment-specific times, often 48 hours; the value is not an unconditional 48-hour lifetime.
- Datadog's prose documentation describes a 15-minute inactivity limit and four-hour maximum **RUM session**. Current source code separately gives the browser cookie one year with anonymous-user tracking or four hours without it. The data distinguishes those two concepts. Pre-v7 `_dd_s` retention is labeled version/configuration-dependent.
- Lifetimes taken only from LinkedIn's integration table are scoped to the published deployment when they cannot safely be generalized to every installation.

Privacy URLs were requested and redirects inspected. Some vendor servers returned access blocks, an empty challenge response, a timeout or a DNS failure to automated requests. An HTTP 200 response alone was not treated as proof of a valid policy: it exposed Smartlook's home-page redirect. Indexed official pages were used to confirm relevant blocked links where available. This audit does not claim every policy endpoint was independently fetched successfully or that a configured deployment must use the documented default.

## Source link verification

A second pass on 20 September 2026 checked **all 82 distinct URLs** used as evidence or as privacy/reference links for the additions. **77 returned readable content; five direct access checks remain unresolved**: 33Across and Akamai returned HTTP 403, Adobe timed out, and the Wordfence cookie notice and privacy policy returned HTTP 202 with empty bodies. No checked URL returned HTTP 404 or 410. Indexed content available through the web research service is distinguished from a successful direct fetch in the [complete link index](cookie-multi-vendor-sources.md).

All **16 raw GitHub URLs** were replaced with readable GitHub file pages pinned to complete commit hashes. Every replacement returned HTTP 200, and the code embedded in the GitHub page matched the corresponding fetched file. Eight of those references previously used moving branch names. The original raw URLs returned code in this environment, so the reported access failure was not reproduced; the replacement URLs provide a different access route and preserve the reviewed revision. Pendo and Zendesk article references were also updated to their successfully fetched canonical URLs.

For Auth.js, the pinned [cookie definitions](https://github.com/nextauthjs/next-auth/blob/a1a16a5a7780488c7449feece410033f445d0b31/packages/core/src/lib/utils/cookie.ts), [session initialization](https://github.com/nextauthjs/next-auth/blob/a1a16a5a7780488c7449feece410033f445d0b31/packages/core/src/lib/init.ts) and [OAuth cookie checks](https://github.com/nextauthjs/next-auth/blob/a1a16a5a7780488c7449feece410033f445d0b31/packages/core/src/lib/actions/callback/oauth/checks.ts) continue to support the recorded names, configurable 30-day session default and 15-minute nonce lifetime. This link-repair pass did not change any cookie records or the count of 224 additions. Fetch success establishes accessibility from the review environment, not universal accessibility or a guarantee of cookie behavior in every deployment.

## Validation

- CSV structure: ten columns, populated required addition fields, valid UUIDs, valid category names, `0`/`1` wildcard flags and HTTPS URL syntax.
- Duplicate checks: all database UUIDs; addition-versus-base and addition-versus-addition exact keys; normalized domains; provider-aware wildcard coverage; review of cross-provider name collisions.
- Scope: compare every base record and the full base byte prefix; all 2,266 original rows remain unchanged.
- Exports: run both existing JSON converters into temporary files and compare all exported fields of all 2,490 records against the CSV. The repository's generated JSON files remain under their existing master-branch automation workflow.
- Repository validator: **still reports the same nine pre-existing invalid `Necessary` categories as `origin/master`**. They belong to QookieQloud (five), Ruby on Rails, NextAuth.js, Supabase and Clerk. All 224 additions use accepted categories. The validator emits an error annotation but exits zero, so its textual output was checked rather than relying on the process exit status.
- `git diff --check`: passes.

## Coverage by original provider

Reattributed entries are counted under their original provider here, so these numbers reconcile exactly with the 236 inputs.

| Original provider | Reviewed | Corrected | Unchanged | Removed/consolidated |
| --- | ---: | ---: | ---: | ---: |
| 33Across | 1 | 1 | 0 | 0 |
| ASP.net | 1 | 1 | 0 | 0 |
| Acuity Scheduling | 7 | 4 | 3 | 0 |
| Adobe Analytics | 5 | 5 | 0 | 0 |
| Adobe Experience Platform | 2 | 2 | 0 | 0 |
| Akamai | 1 | 1 | 0 | 0 |
| Amazon CloudFront | 3 | 3 | 0 | 0 |
| Auth.js | 8 | 3 | 5 | 0 |
| BigCommerce | 6 | 5 | 0 | 1 |
| Clerk | 4 | 4 | 0 | 0 |
| Datadog | 4 | 4 | 0 | 0 |
| FreeWheel | 2 | 1 | 0 | 1 |
| Gainsight PX | 2 | 2 | 0 | 0 |
| Google | 2 | 1 | 1 | 0 |
| HubSpot | 5 | 4 | 1 | 0 |
| LinkedIn | 46 | 46 | 0 | 0 |
| LiteSpeed | 1 | 1 | 0 | 0 |
| Magento | 20 | 20 | 0 | 0 |
| Matomo | 2 | 0 | 2 | 0 |
| Microsoft | 4 | 4 | 0 | 0 |
| Microsoft Forms | 1 | 1 | 0 | 0 |
| Moodle | 3 | 2 | 0 | 1 |
| Mouseflow | 2 | 1 | 0 | 1 |
| NextAuth.js | 4 | 2 | 2 | 0 |
| Okta | 3 | 2 | 0 | 1 |
| Pendo | 11 | 5 | 6 | 0 |
| PerimeterX | 8 | 2 | 0 | 6 |
| PostHog | 1 | 0 | 1 | 0 |
| PrestaShop | 2 | 1 | 0 | 1 |
| Salesforce | 4 | 4 | 0 | 0 |
| Shopify | 19 | 4 | 15 | 0 |
| Skilljar | 1 | 1 | 0 | 0 |
| Smartlook | 3 | 3 | 0 | 0 |
| Squarespace | 25 | 6 | 19 | 0 |
| Stripe | 3 | 2 | 1 | 0 |
| Wordfence | 3 | 3 | 0 | 0 |
| Zendesk | 17 | 14 | 3 | 0 |
