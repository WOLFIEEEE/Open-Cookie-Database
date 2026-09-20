# Cookie audit source links — 20 September 2026

This is the individually clickable link index for the [cookie additions audit](cookie-multi-vendor-audit.md) and its [row-by-row evidence ledger](cookie-multi-vendor-audit.csv). It includes all **82 distinct URLs** used by the audit or the retained additions: **52 evidence sources** and **35 privacy/reference URLs**, with five shared between those groups.

Checks below describe direct requests from the review environment on 20 September 2026. **77 URLs returned readable content; five access checks remain unresolved.** None returned a 404 or 410. A successful fetch establishes availability here, not access from every browser or the correctness of every claim on a page. Privacy/reference links provide vendor context; they do not by themselves substantiate cookie names or lifetimes.

All **16 GitHub source links** now use readable `github.com` file pages pinned to full commit hashes. Each page returned HTTP 200, and its embedded code was compared with the corresponding fetched source file. Eight formerly used moving branch names (`main`, `v4` or a Moodle stable branch). The original raw URLs also returned code here; the access failure reported by the user was not reproduced. The new links provide another access route and preserve the exact reviewed revision.

## Access checks still unresolved

| Link | Direct result | Evidence limit |
| --- | --- | --- |
| [33Across privacy policy](https://33across.com/privacy-policy/) | HTTP 403; JavaScript/cookie challenge | The policy body was not fetched. |
| [Adobe privacy policy](https://www.adobe.com/privacy/policy.html) | Request timed out | The web research service returned policy text, but direct access remains unconfirmed. |
| [Akamai privacy and policies](https://www.akamai.com/legal/privacy-and-policies) | HTTP 403; access denied | The web research service resolves this legacy address to the broader legal index; this is not a direct policy verification. |
| [Wordfence cookies notice](https://www.wordfence.com/cookies-notice/) | HTTP 202 with an empty body | Indexed vendor text supports the cookie entries; a direct readable response was not obtained. |
| [Wordfence privacy policy](https://www.wordfence.com/privacy-policy/) | HTTP 202 with an empty body | The web research service returned policy text, but a direct readable response was not obtained. |

These are explicitly unresolved access checks, not confirmed deletions or passing checks. Successful retrieval through the web research service does not override the direct-request result.

## Complete link index

“Evidence” means the URL appears in the row-by-row audit. “Privacy/reference” means it appears in the database’s privacy/rights field; NextAuth.js and Auth.js currently point to framework documentation. HTTP 200 entries had their returned title/content checked for obvious error pages. Redirects to country-specific policy pages are reported instead of replacing the country-neutral URL.

| # | Source | Used for | Providers | Direct result | Redirect / check note |
| ---: | --- | --- | --- | --- | --- |
| 1 | [33Across privacy policy](https://33across.com/privacy-policy/) | Privacy/reference | 33Across | 403 — unresolved | Resolves to https://www.33across.com/privacy-policy/ Access blocked; policy body not fetched. |
| 2 | [Auth.js \| Types](https://authjs.dev/reference/core/types) | Privacy/reference | Auth.js | 200 — readable | No redirect. |
| 3 | [AWS Privacy Notice](https://aws.amazon.com/privacy/) | Privacy/reference | Amazon CloudFront | 200 — readable | No redirect. |
| 4 | [Business Data Responsibility](https://business.safety.google/privacy/) | Privacy/reference | Google | 200 — readable | No redirect. |
| 5 | [Terminology - SDK Development \| Clerk Docs](https://clerk.com/docs/guides/development/sdk-development/terminology) | Evidence | Clerk | 200 — readable | No redirect. |
| 6 | [How Clerk works \| Clerk Docs](https://clerk.com/docs/guides/how-clerk-works/overview) | Evidence | Clerk | 200 — readable | No redirect. |
| 7 | [Clerk, Inc. Privacy Policy](https://clerk.com/privacy) | Privacy/reference | Clerk | 200 — readable | Resolves to https://clerk.com/legal/privacy |
| 8 | [Cookie :: PrestaShop Developer Documentation](https://devdocs.prestashop-project.org/9/development/components/cookie/) | Evidence | PrestaShop | 200 — readable | No redirect. |
| 9 | [Understand how sessions work after the upgrade \| Okta Developer](https://developer.okta.com/docs/guides/oie-upgrade-sessions-api/main/) | Evidence | Okta | 200 — readable | No redirect. |
| 10 | [Share a sign-in session with native mobile apps \| Okta Developer](https://developer.okta.com/docs/guides/shared-sso-android-ios/ios/main/) | Evidence | Okta | 200 — readable | No redirect. |
| 11 | [Set signed cookies using a custom policy - Amazon CloudFront](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/private-content-setting-signed-cookie-custom-policy.html) | Evidence | Amazon CloudFront | 200 — readable | No redirect. |
| 12 | [Cookies \| BigCommerce Docs](https://docs.bigcommerce.com/developer/docs/storefront/catalyst/features/cookies) | Evidence | BigCommerce | 200 — readable | No redirect. |
| 13 | [Advanced Configuration](https://docs.datadoghq.com/real_user_monitoring/application_monitoring/browser/advanced_configuration/) | Evidence | Datadog | 200 — readable | No redirect. |
| 14 | [Troubleshooting Browser SDK Issues](https://docs.datadoghq.com/real_user_monitoring/application_monitoring/browser/troubleshooting/) | Evidence | Datadog | 200 — readable | No redirect. |
| 15 | [Advanced Concepts \| LSCache Developers Guide \| LiteSpeed Documentation](https://docs.litespeedtech.com/lscache/devguide/advanced/) | Evidence | LiteSpeed | 200 — readable | No redirect. |
| 16 | [doPlugins \| Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/functions/doplugins) | Evidence | Adobe Analytics | 200 — readable | No redirect. |
| 17 | [getPercentPageViewed \| Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/plugins/getpercentpageviewed) | Evidence | Adobe Analytics | 200 — readable | No redirect. |
| 18 | [getPreviousValue \| Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/plugins/getpreviousvalue) | Evidence | Adobe Analytics | 200 — readable | No redirect. |
| 19 | [Cookie law compliance \| Adobe Commerce](https://experienceleague.adobe.com/en/docs/commerce-admin/start/compliance/privacy/compliance-cookie-law) | Evidence | Adobe Experience Platform, Magento | 200 — readable | No redirect. |
| 20 | [DataDog/browser-sdk — packages/browser-core/src/browser/cookie.ts](https://github.com/DataDog/browser-sdk/blob/a46e96e49348afe54f3f770e12aa645c438706d8/packages/browser-core/src/browser/cookie.ts) | Evidence | Datadog | 200 — readable | GitHub page returned 200; embedded file content matches the fetched source. Pinned to a full commit SHA. |
| 21 | [DataDog/browser-sdk — packages/browser-core/src/browser/cookieAccess.ts](https://github.com/DataDog/browser-sdk/blob/a46e96e49348afe54f3f770e12aa645c438706d8/packages/browser-core/src/browser/cookieAccess.ts) | Evidence | Datadog | 200 — readable | GitHub page returned 200; embedded file content matches the fetched source. Pinned to a full commit SHA. |
| 22 | [DataDog/browser-sdk — packages/browser-core/src/domain/session/sessionConstants.ts](https://github.com/DataDog/browser-sdk/blob/a46e96e49348afe54f3f770e12aa645c438706d8/packages/browser-core/src/domain/session/sessionConstants.ts) | Evidence | Datadog | 200 — readable | GitHub page returned 200; embedded file content matches the fetched source. Pinned to a full commit SHA. |
| 23 | [DataDog/browser-sdk — packages/browser-core/src/domain/session/storeStrategies/sessionInCookie.ts](https://github.com/DataDog/browser-sdk/blob/a46e96e49348afe54f3f770e12aa645c438706d8/packages/browser-core/src/domain/session/storeStrategies/sessionInCookie.ts) | Evidence | Datadog | 200 — readable | GitHub page returned 200; embedded file content matches the fetched source. Pinned to a full commit SHA. |
| 24 | [PrestaShop/PrestaShop — classes/Cookie.php](https://github.com/PrestaShop/PrestaShop/blob/e5515d88ead3761a342c72bffb91446ba213ba13/classes/Cookie.php) | Evidence | PrestaShop | 200 — readable | GitHub page returned 200; embedded file content matches the fetched source. Pinned to a full commit SHA. |
| 25 | [clerk/javascript — packages/clerk-js/src/core/auth/cookies/clientUat.ts](https://github.com/clerk/javascript/blob/4ff463adf9f287918d902daefa7828790a066d04/packages/clerk-js/src/core/auth/cookies/clientUat.ts) | Evidence | Clerk | 200 — readable | GitHub page returned 200; embedded file content matches the fetched source. Pinned to a full commit SHA. |
| 26 | [clerk/javascript — packages/clerk-js/src/core/auth/cookies/devBrowser.ts](https://github.com/clerk/javascript/blob/4ff463adf9f287918d902daefa7828790a066d04/packages/clerk-js/src/core/auth/cookies/devBrowser.ts) | Evidence | Clerk | 200 — readable | GitHub page returned 200; embedded file content matches the fetched source. Pinned to a full commit SHA. |
| 27 | [clerk/javascript — packages/clerk-js/src/core/auth/cookies/session.ts](https://github.com/clerk/javascript/blob/4ff463adf9f287918d902daefa7828790a066d04/packages/clerk-js/src/core/auth/cookies/session.ts) | Evidence | Clerk | 200 — readable | GitHub page returned 200; embedded file content matches the fetched source. Pinned to a full commit SHA. |
| 28 | [moodle/moodle — lib/setup.php](https://github.com/moodle/moodle/blob/572729aaa5b23c087f712e4fe4c43fa5d7cc1853/lib/setup.php) | Evidence | Moodle | 200 — readable | GitHub page returned 200; embedded file content matches the fetched source. Pinned to a full commit SHA. |
| 29 | [moodle/moodle — lib/classes/session/manager.php](https://github.com/moodle/moodle/blob/89ae02d0007418c50f0911148137f4cb3bd67f4a/lib/classes/session/manager.php) | Evidence | Moodle | 200 — readable | GitHub page returned 200; embedded file content matches the fetched source. Pinned to a full commit SHA. |
| 30 | [moodle/moodle — lib/sessionlib.php](https://github.com/moodle/moodle/blob/89ae02d0007418c50f0911148137f4cb3bd67f4a/lib/sessionlib.php) | Evidence | Moodle | 200 — readable | GitHub page returned 200; embedded file content matches the fetched source. Pinned to a full commit SHA. |
| 31 | [nextauthjs/next-auth — packages/core/src/lib/actions/callback/oauth/checks.ts](https://github.com/nextauthjs/next-auth/blob/a1a16a5a7780488c7449feece410033f445d0b31/packages/core/src/lib/actions/callback/oauth/checks.ts) | Evidence | Auth.js | 200 — readable | GitHub page returned 200; embedded file content matches the fetched source. Pinned to a full commit SHA. |
| 32 | [nextauthjs/next-auth — packages/core/src/lib/init.ts](https://github.com/nextauthjs/next-auth/blob/a1a16a5a7780488c7449feece410033f445d0b31/packages/core/src/lib/init.ts) | Evidence | Auth.js | 200 — readable | GitHub page returned 200; embedded file content matches the fetched source. Pinned to a full commit SHA. |
| 33 | [nextauthjs/next-auth — packages/core/src/lib/utils/cookie.ts](https://github.com/nextauthjs/next-auth/blob/a1a16a5a7780488c7449feece410033f445d0b31/packages/core/src/lib/utils/cookie.ts) | Evidence | Auth.js | 200 — readable | GitHub page returned 200; embedded file content matches the fetched source. Pinned to a full commit SHA. |
| 34 | [nextauthjs/next-auth — packages/next-auth/src/core/lib/cookie.ts](https://github.com/nextauthjs/next-auth/blob/d857eec560fb99c8b18d3b22a2693b849a62d1c3/packages/next-auth/src/core/lib/cookie.ts) | Evidence | NextAuth.js | 200 — readable | GitHub page returned 200; embedded file content matches the fetched source. Pinned to a full commit SHA. |
| 35 | [nextauthjs/next-auth — packages/next-auth/src/core/lib/oauth/checks.ts](https://github.com/nextauthjs/next-auth/blob/d857eec560fb99c8b18d3b22a2693b849a62d1c3/packages/next-auth/src/core/lib/oauth/checks.ts) | Evidence | NextAuth.js | 200 — readable | GitHub page returned 200; embedded file content matches the fetched source. Pinned to a full commit SHA. |
| 36 | [What is your cookie policy? \| Help Center - Mouseflow](https://help.mouseflow.com/en/articles/4282966-what-is-your-cookie-policy) | Evidence | Mouseflow | 200 — readable | No redirect. |
| 37 | [Cookies and Smartlook](https://help.smartlook.com/docs/cookies-smartlook) | Evidence | Smartlook | 200 — readable | No redirect. |
| 38 | [Privacy Statement](https://help.smartlook.com/docs/privacy-statement-full) | Evidence; Privacy/reference | Smartlook | 200 — readable | No redirect. |
| 39 | [Cookies set in your visitor's browser by HubSpot](https://knowledge.hubspot.com/privacy-and-consent/what-cookies-does-hubspot-set-in-a-visitor-s-browser) | Evidence | HubSpot | 200 — readable | No redirect. |
| 40 | [Web browser cookies used in Microsoft Entra authentication - Microsoft Entra ID \| Microsoft Learn](https://learn.microsoft.com/en-us/entra/identity/authentication/concept-authentication-web-browser-cookies) | Evidence | Microsoft | 200 — readable | No redirect. |
| 41 | [HubSpot Privacy Policy](https://legal.hubspot.com/privacy-policy) | Privacy/reference | HubSpot | 200 — readable | No redirect. |
| 42 | [What cookies are created by the Matomo JavaScript Tracking client? FAQ - Analytics Platform - Matomo](https://matomo.org/faq/general/faq_146/) | Evidence | Matomo | 200 — readable | No redirect. |
| 43 | [Privacy Policy - Analytics Platform - Matomo](https://matomo.org/privacy-policy/) | Privacy/reference | Matomo | 200 — readable | No redirect. |
| 44 | [Privacy Notice - Moodle](https://moodle.com/privacy-notice/) | Privacy/reference | Moodle | 200 — readable | No redirect. |
| 45 | [Mouseflow Privacy Policy \| Data Protection & Rights](https://mouseflow.com/legal/privacy-policy/) | Privacy/reference | Mouseflow | 200 — readable | No redirect. |
| 46 | [Options \| NextAuth.js](https://next-auth.js.org/configuration/options) | Evidence; Privacy/reference | NextAuth.js | 200 — readable | No redirect. |
| 47 | [Wordfence plugin source — wordfenceClass.php](https://plugins.svn.wordpress.org/wordfence/trunk/lib/wordfenceClass.php) | Evidence | Wordfence | 200 — readable | No redirect. |
| 48 | [How Google uses cookies – Privacy & Terms – Google](https://policies.google.com/technologies/cookies?hl=en-US) | Evidence | Google | 200 — readable | No redirect. |
| 49 | [JavaScript web persistence and cookies - Docs - PostHog](https://posthog.com/docs/libraries/js/persistence) | Evidence | PostHog | 200 — readable | No redirect. |
| 50 | [Privacy policy, PostHog style](https://posthog.com/privacy) | Privacy/reference | PostHog | 200 — readable | No redirect. |
| 51 | [Microsoft Privacy Statement – Microsoft privacy](https://privacy.microsoft.com/privacystatement) | Privacy/reference | Microsoft, Microsoft Forms | 200 — readable | Resolves to https://www.microsoft.com/en-ca/privacy/privacystatement |
| 52 | [Service Privacy Notice - Sift](https://sift.com/legal-and-compliance/service-privacy-notice) | Privacy/reference | Sift | 200 — readable | Resolves to https://sift.com/legal-and-compliance/service-privacy-notice/ |
| 53 | [Privacy Policy](https://stripe.com/privacy) | Privacy/reference | Stripe | 200 — readable | Resolves to https://stripe.com/in/privacy |
| 54 | [Analytics Cookies - Gainsight Inc.](https://support.gainsight.com/PX/Install_PX/Install_PX_Web/Analytics_Cookies) | Evidence | Gainsight PX | 200 — readable | No redirect. |
| 55 | [Cookies and local storage – Pendo Help Center](https://support.pendo.io/hc/en-us/articles/360041032971-Cookies-and-local-storage) | Evidence | Pendo | 200 — readable | Use the current article URL returned by the original redirect. |
| 56 | [The cookies Squarespace uses – Squarespace Help Center](https://support.squarespace.com/hc/en-us/articles/360001264507-The-cookies-Squarespace-uses) | Evidence | Acuity Scheduling, Squarespace | 200 — readable | No redirect. |
| 57 | [Zendesk In-Product Cookie Policy – Zendesk help](https://support.zendesk.com/hc/en-us/articles/4408824378650-Zendesk-In-Product-Cookie-Policy) | Evidence | Stripe, Zendesk | 200 — readable | Use the current article URL returned by the original redirect. |
| 58 | [Adobe privacy policy](https://www.adobe.com/privacy/policy.html) | Privacy/reference | Adobe Analytics, Adobe Experience Platform, Magento | Timeout — unresolved | Direct fetch timed out; not counted as readable. |
| 59 | [Akamai privacy and policies](https://www.akamai.com/legal/privacy-and-policies) | Privacy/reference | Akamai | 403 — unresolved | Access blocked; policy body not fetched. |
| 60 | [Privacy Policy \| Commerce](https://www.commerce.com/privacy/) | Evidence; Privacy/reference | BigCommerce | 200 — readable | No redirect. |
| 61 | [Privacy Policy \| Datadog](https://www.datadoghq.com/legal/privacy/) | Privacy/reference | Datadog | 200 — readable | No redirect. |
| 62 | [Privacy Policy \| FreeWheel](https://www.freewheel.com/privacy-policy) | Privacy/reference | FreeWheel | 200 — readable | No redirect. |
| 63 | [Privacy Policy \| Customer Success Software \| Gainsight](https://www.gainsight.com/policy/privacy/) | Evidence; Privacy/reference | Gainsight, Gainsight PX | 200 — readable | No redirect. |
| 64 | [HUMAN Privacy Policy - HUMAN Security](https://www.humansecurity.com/privacy-policy) | Privacy/reference | PerimeterX | 200 — readable | Resolves to https://www.humansecurity.com/privacy-policy/ |
| 65 | [Cookie Table](https://www.linkedin.com/legal/l/cookie-table) | Evidence | 33Across, Adobe Analytics, Akamai, CVTrust, FreeWheel, Gainsight, Google, LinkedIn, Microsoft, Microsoft Forms, Oracle, PerimeterX, Salesforce, Sift, Skilljar | 200 — readable | No redirect. |
| 66 | [LinkedIn Privacy Policy](https://www.linkedin.com/legal/privacy-policy) | Privacy/reference | LinkedIn | 200 — readable | No redirect. |
| 67 | [Privacy Policy - LiteSpeed Technologies](https://www.litespeedtech.com/company/privacy-policy) | Evidence; Privacy/reference | LiteSpeed | 200 — readable | No redirect. |
| 68 | [Microsoft Privacy Statement – Microsoft privacy](https://www.microsoft.com/en-gb/privacy/privacystatement) | Evidence | Microsoft, Microsoft Forms | 200 — readable | No redirect. |
| 69 | [Cookies Policy \| Okta](https://www.okta.com/legal/cookies-policy/) | Evidence | Okta | 200 — readable | No redirect. |
| 70 | [Privacy Policy \| Okta](https://www.okta.com/privacy-policy/) | Privacy/reference | Okta | 200 — readable | Resolves to https://www.okta.com/legal/privacy-policy/ |
| 71 | [Privacy @ Oracle \| Oracle](https://www.oracle.com/legal/privacy/) | Privacy/reference | Oracle | 200 — readable | No redirect. |
| 72 | [Privacy Policy](https://www.pendo.io/privacy-policy/) | Privacy/reference | Pendo | 200 — readable | Resolves to https://www.pendo.io/legal/privacy-policy/ |
| 73 | [Politique de protection des donnÃ©es \| PrestaShop](https://www.prestashop.com/en/privacy-policy) | Privacy/reference | PrestaShop | 200 — readable | Resolves to https://prestashop.com/privacy-policy/ |
| 74 | [Salesforce Privacy Information \| Salesforce](https://www.salesforce.com/company/privacy/) | Privacy/reference | Salesforce | 200 — readable | Resolves to https://www.salesforce.com/company/legal/privacy/ |
| 75 | [Shopify Cookie Policy - Shopify](https://www.shopify.com/legal/cookies) | Evidence | Shopify | 200 — readable | No redirect. |
| 76 | [Shopify Privacy Policy - Shopify](https://www.shopify.com/legal/privacy) | Privacy/reference | Shopify | 200 — readable | No redirect. |
| 77 | [Privacy](https://www.skilljar.com/privacy) | Privacy/reference | Skilljar | 200 — readable | No redirect. |
| 78 | [Smart Certificate \| Terms and conditions](https://www.smartcertificate.com/en/terms-and-conditions/) | Privacy/reference | CVTrust | 200 — readable | No redirect. |
| 79 | [Privacy Policy — Squarespace](https://www.squarespace.com/privacy) | Privacy/reference | Acuity Scheduling, Squarespace | 200 — readable | No redirect. |
| 80 | [Wordfence cookies notice](https://www.wordfence.com/cookies-notice/) | Evidence | Wordfence | 202 — unresolved | Empty body; not counted as readable. |
| 81 | [Wordfence privacy policy](https://www.wordfence.com/privacy-policy/) | Privacy/reference | Wordfence | 202 — unresolved | Empty body; not counted as readable. |
| 82 | [Privacy Policy \| Zendesk India](https://www.zendesk.com/company/agreements-and-terms/privacy-notice/) | Privacy/reference | Zendesk | 200 — readable | Resolves to https://www.zendesk.com/in/company/agreements-and-terms/privacy-notice/#georedirect |
