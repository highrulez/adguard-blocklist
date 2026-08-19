# OBFUSGATED Ad Block Test report

- Timestamp (UTC): 2026-08-19T03:05:00Z
- Test URL: https://obfusgated.com/tools/ad-block-test
- DNS path: verified through the configured AdGuard Home resolver (address omitted)

## Before update

| Metric | Result |
|---|---:|
| Total probes | 358 |
| Blocked | 270 |
| Accessible | 88 |
| Protection | 75.4% |

| Category | Blocked | Accessible |
|---|---:|---:|
| Ads | 98 | 11 |
| Analytics | 23 | 9 |
| Tracking & Fingerprinting | 26 | 4 |
| Error Trackers | 3 | 0 |
| Cryptominers & Malware | 13 | 7 |
| Social Trackers | 29 | 11 |
| OEM Vendors | 62 | 4 |
| Consent Management | 0 | 9 |
| Affiliate Networks | 12 | 15 |
| A/B Testing | 0 | 4 |
| Email Tracking | 3 | 3 |
| Video Ads | 1 | 11 |

## Accessible hosts observed

The live browser test was expanded and every category was inspected. No Mixed/uncertain status was exposed.

- Ads: `aan.amazon.com`, `taboola.com`, `api.taboola.com`, `bingads.microsoft.com`, `ads.yahoo.com`, `config.unityads.unity3d.com`, `adserver.unityads.unity3d.com`, `mc.yandex.ru`, `s.youtube.com`, `redirector.googlevideo.com`, `youtubei.googleapis.com`.
- Analytics: `analytics.google.com`, `googletagmanager.com`, `tagmanager.google.com`, `www.googletagmanager.com`, `analytics.adobe.io`, `script.hotjar.com`, `heapanalytics.com`, `api2.amplitude.com`, `scorecardresearch.com`.
- Tracking & Fingerprinting: `permutive.com`, `api2.branch.io`, `singular.net`, `clevertap-prod.com`.
- Cryptominers & Malware: `www.coinimp.com`, `crypto-loot.org`, `popcash.net`, `trafficjunky.net`, `exoclick.com`, `2giga.link`, `greatis.com`.
- Social Trackers: `connect.facebook.net`, `graph.facebook.com`, `graph.instagram.com`, `sc-static.net`, `analytics.pointdrive.linkedin.com`, `static.ads-twitter.com`, `ads.x.com`, `ads-sg.tiktok.com`, `analytics-sg.tiktok.com`, `business-api.tiktok.com`, `vk.com/rtrg`.
- OEM Vendors: `adx.ads.oppomobile.com`, `ck.ads.oppomobile.com`, `us.info.lgsmartad.com`, `app-measurement.com`.
- Consent Management: `cdn.cookielaw.org`, `geolocation.onetrust.com`, `consent.cookiebot.com`, `consentcdn.cookiebot.com`, `cookiebot.com`, `consent.trustarc.com`, `sdk.privacy-center.org`, `cdn.privacy-mgmt.com`, `app.usercentrics.eu`.
- Affiliate Networks: `www.dpbolvw.net`, `shareasale.com`, `shareasale-analytics.com`, `impact.com`, `api.impact.com`, `www.awin1.com`, `zenaps.com`, `partnerstack.com`, `api.partnerstack.com`, `api.refersion.com`, `go.skimresources.com`, `redirector.skimresources.com`, `redirect.viglink.com`, `cdn.viglink.com`, `api.viglink.com`.
- A/B Testing: `cdn.optimizely.com`, `logx.optimizely.com`, `api.optimizely.com`, `cdn.dynamicyield.com`.
- Email Tracking: `trackcmp.net`, `widget.intercom.io`, `js.driftt.com`.
- Video Ads: `imasdk.googleapis.com`, `dai.google.com`, `g.jwpsrv.com`, `mssl.fwmrm.net`, `cd.connatix.com`, `capi.connatix.com`, `vid.connatix.com`, `metrics.brightcove.com`, `s.innovid.com`, `tremorhub.com`, `ads.tremorhub.com`.

## Rules selected

Added only narrow, clearly advertising, tracking, analytics, telemetry, OEM-advertising, and video-ad endpoints. The 17 new rules are listed in the Git diff and categorized in `lists/`.

## Intentionally skipped

- Google, Meta, Instagram, YouTube, Unity, and social-network API/content hosts: can be necessary for sign-in, playback, core APIs, or embedded content.
- Consent-management and A/B-testing vendors: can be needed for legal consent and application feature delivery.
- Intercom, Drift, and other lifecycle/customer-support endpoints: can support legitimate chat or notifications.
- Generic affiliate/vendor roots and ambiguous hosts: avoided where a hostname-specific ad/tracking purpose was not clear.

## After update

Pending: the new committed list must be pushed, fetched by AdGuard Home, and verified through DNS before the comparison test is meaningful.

## Fresh retest before current update

- Timestamp (UTC): 2026-08-19T03:15:00Z
- Total tested: 357
- Blocked: 298
- Accessible: 59
- Protection: 83.5%
- Unusual statuses: none; the site exposed only Blocked and Accessible.

Accessible hosts by category:

- Ads: `cdn.taboola.com`, `ads.yahoo.com`, `s.youtube.com`, `redirector.googlevideo.com`, `youtubei.googleapis.com`.
- Analytics: `googletagmanager.com`, `tagmanager.google.com`, `www.googletagmanager.com`, `api-js.mixpanel.com`, `scorecardresearch.com`.
- Tracking & Fingerprinting: `thetradedesk.com`, `app.appsflyer.com`, `app.adjust.com`.
- Cryptominers & Malware: `crypto-loot.org`, `2giga.link`, `greatis.com`.
- Social Trackers: `connect.facebook.net`, `graph.facebook.com`, `graph.instagram.com`, `i.instagram.com`, `ads.x.com`, `ads-sg.tiktok.com`, `business-api.tiktok.com`, `vk.com/rtrg`.
- OEM Vendors: `firebase-settings.crashlytics.com`.
- Consent Management: `cdn.cookielaw.org`, `geolocation.onetrust.com`, `consent.cookiebot.com`, `consentcdn.cookiebot.com`, `consent.trustarc.com`, `sdk.privacy-center.org`, `cdn.privacy-mgmt.com`, `app.usercentrics.eu`.
- Affiliate Networks: `www.anrdoezrs.net`, `www.dpbolvw.net`, `shareasale.com`, `shareasale-analytics.com`, `impact.com`, `api.impact.com`, `www.awin1.com`, `zenaps.com`, `go.skimresources.com`, `redirector.skimresources.com`, `redirect.viglink.com`, `cdn.viglink.com`, `api.viglink.com`.
- A/B Testing: `cdn.optimizely.com`, `logx.optimizely.com`, `api.optimizely.com`, `cdn.dynamicyield.com`.
- Email Tracking: `widget.intercom.io`.
- Video Ads: `imasdk.googleapis.com`, `dai.google.com`, `g.jwpsrv.com`, `ssl.p.jwpcdn.com`, `mssl.fwmrm.net`, `cd.connatix.com`, `capi.connatix.com`, `vid.connatix.com`.

### Rules added from this retest

`2giga.link`, `crypto-loot.org`, `ads.yahoo.com`, `ads.x.com`, `api-js.mixpanel.com`, `scorecardresearch.com`, `shareasale-analytics.com`, `www.anrdoezrs.net`, `www.awin1.com`, `www.dpbolvw.net`, `zenaps.com`, `go.skimresources.com`, `redirector.skimresources.com`, `redirect.viglink.com`, `cdn.viglink.com`, and `api.viglink.com`.

### Covered but still accessible

`cdn.taboola.com`, `app.appsflyer.com`, `app.adjust.com`, `ads-sg.tiktok.com`, and `business-api.tiktok.com` already match existing Highrulez rules. Their accessible result is therefore not a reason to add duplicate rules; likely causes include the test request method, browser-level behavior, cache, or the DNS rule not applying to the test's exact resource path.

### Intentionally skipped in this retest

- Google, Meta, Instagram, YouTube, and Firebase API/content hosts: authentication, playback, application delivery, or configuration risk.
- Tag Manager, A/B testing, consent, Intercom, and video player/CDN hosts: may be required for site behavior, consent, support, or playback.
- `thetradedesk.com`, `greatis.com`, `shareasale.com`, `impact.com`, and `api.impact.com`: root/API domains are not narrowly enough advertising/tracking-specific for a DNS-wide block.
