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

## After AdGuard Home refresh

- Timestamp (UTC): 2026-08-19T03:25:00Z
- Total tested: 357
- Blocked: 302
- Accessible: 55
- Protection: 84.6%
- Direct DNS validation: passed. `crypto-loot.org`, `ads.yahoo.com`, and `www.anrdoezrs.net` returned the configured AdGuard blocking addresses when queried directly.

| Metric | Before current update | After refresh |
|---|---:|---:|
| Protection | 83.5% | 84.6% |
| Blocked | 298 | 302 |
| Accessible | 59 | 55 |

### Newly blocked in the browser test

`2giga.link`, `ads.yahoo.com`, `go.skimresources.com`, `redirector.skimresources.com`, and `redirect.viglink.com` changed from Accessible to Blocked.

### Still accessible

- Ads: `cdn.taboola.com`, `s.youtube.com`, `redirector.googlevideo.com`, `youtubei.googleapis.com`.
- Analytics: `googletagmanager.com`, `tagmanager.google.com`, `www.googletagmanager.com`, `api-js.mixpanel.com`, `scorecardresearch.com`.
- Tracking & Fingerprinting: `thetradedesk.com`, `app.appsflyer.com`, `app.adjust.com`.
- Cryptominers & Malware: `crypto-loot.org`, `greatis.com`.
- Social Trackers: `connect.facebook.net`, `graph.facebook.com`, `graph.instagram.com`, `i.instagram.com`, `ads.x.com`, `ads-sg.tiktok.com`, `business-api.tiktok.com`, `vk.com/rtrg`.
- OEM Vendors: `firebase-settings.crashlytics.com`.
- Consent Management: `cdn.cookielaw.org`, `geolocation.onetrust.com`, `consent.cookiebot.com`, `consentcdn.cookiebot.com`, `cookiebot.com`, `consent.trustarc.com`, `sdk.privacy-center.org`, `cdn.privacy-mgmt.com`, `app.usercentrics.eu`.
- Affiliate Networks: `www.anrdoezrs.net`, `www.dpbolvw.net`, `www.tkqlhce.com`, `shareasale.com`, `shareasale-analytics.com`, `impact.com`, `api.impact.com`, `www.awin1.com`, `zenaps.com`, `cdn.viglink.com`.
- A/B Testing: `cdn.optimizely.com`, `logx.optimizely.com`, `api.optimizely.com`, `cdn.dynamicyield.com`.
- Email Tracking: `widget.intercom.io`.
- Video Ads: `imasdk.googleapis.com`, `dai.google.com`, `g.jwpsrv.com`, `ssl.p.jwpcdn.com`, `mssl.fwmrm.net`, `cd.connatix.com`, `capi.connatix.com`, `vid.connatix.com`.

### Browser/DNS mismatch

Direct AdGuard DNS lookups prove that three newly added rules are active. The OBFUSGATED browser probe nevertheless reported some rules as Accessible, including `crypto-loot.org` and several rules already present before this retest. This indicates the site's resource-fetch methodology, browser caching, CNAME/resource behavior, or non-DNS failure classification is not equivalent to a direct DNS-block test. No duplicate rules were added to chase these probes.

## Video Advertising Tests

### YouTube

- Domains evaluated: `pagead2.googlesyndication.com`, `googleads.g.doubleclick.net`, `ad.doubleclick.net`, `stats.g.doubleclick.net`, `static.doubleclick.net`, `securepubads.g.doubleclick.net`, `pubads.g.doubleclick.net`, `tpc.googlesyndication.com`, `googleadservices.com`, and `ads.youtube.com`.
- Existing coverage: all except `stats.g.doubleclick.net` were already covered by the Highrulez list (including `www.googleadservices.com` via its parent rule). Direct DNS checks confirmed blocking for `pagead2.googlesyndication.com`, `googleads.g.doubleclick.net`, and `ads.youtube.com`.
- Domain added: `stats.g.doubleclick.net` in `lists/video-ads.txt`. It is a hostname-specific DoubleClick measurement endpoint.
- Domains skipped: `youtube.com`, `googlevideo.com`, `ytimg.com`, `ggpht.com`, `googleusercontent.com`, `s.youtube.com`, `redirector.googlevideo.com`, `youtubei.googleapis.com`, and Google Tag Manager hosts. These support playback, account/API features, thumbnails, or application delivery.
- Playback result: three normal public videos loaded to ready state 4 and played past three seconds after explicit Play. Navigation, thumbnails/search results, and signed-out account UI remained available; no DNS-related playback failure was observed.
- Ads: no pre-roll, display, or measurement ad was visibly rendered during the short startup samples. Mid-roll and post-roll could not be conclusively assessed without long-duration viewing, so advertisements are reported as **not demonstrated**, not fully blocked.
- DNS limitation: YouTube frequently serves advertising and media through shared Google/YouTube infrastructure. DNS filtering can block dedicated Google ad and DoubleClick hosts but cannot reliably remove all YouTube ads without risking playback or core features.

### Dailymotion

- Domains evaluated: live Dailymotion player pages and their browser-visible player state; no dedicated Dailymotion advertising/tracking hostname was exposed through the available diagnostics.
- Domains added: none.
- Domains skipped: Dailymotion primary site, player/CDN, API, thumbnail, and account infrastructure. No broad Dailymotion rule was created.
- Playback result: three normal public video pages showed an active `Video playing` player. Navigation remained available and no DNS-related playback failure was observed.
- Ads: no obvious pre-roll/display ad was shown in the short samples; mid-roll and post-roll were not conclusively assessed. Result: **unchanged/not demonstrated**.
