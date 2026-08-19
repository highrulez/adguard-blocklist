# Super AdBlock Test report

- Timestamp (UTC): 2026-08-19T02:29:20Z
- Test surface: real browser on the current machine/network connection
- Test URL: https://superadblocktest.com/

## Original result

| Metric | Result |
|---|---:|
| Protection Score | 12% |
| Raw Block Rate | 13% (65/482) |
| Blocked probes | 65 |
| Reachable probes | 417 |
| Mixed probes | 0 |

The detailed-results view was opened after completion. The host-level result set contained 482 probes: 160 Ads (21 blocked, 139 reachable), 67 Analytics (11, 56), 32 Tracking & Fingerprinting (5, 27), 15 Error Trackers (1, 14), 69 OEM Vendors (18, 51), 49 Social Trackers (2, 47), 24 Advanced/Risky (4, 20), 15 Consent Management (2, 13), 23 Affiliate Networks (0, 23), 7 A/B Testing (0, 7), 14 Email Tracking & Live Chat (1, 13), and 17 Video Ads (0, 17). No probes were reported as Mixed.

## Changes selected from reachable probes

Added 266 rules not present in the prior repository revision (295 unique rules in the combined list after preserving the 38 existing rules). They are organized as:

- `lists/ads.txt`: 115 advertising, ad-exchange, and video-ad endpoints.
- `lists/trackers.txt`: 94 analytics, attribution, fingerprinting, affiliate, and social-tracking endpoints.
- `lists/telemetry.txt`: 35 analytics/error-reporting/measurement endpoints.
- `lists/oem-telemetry.txt`: 51 OEM advertising and telemetry endpoints.

Each individual hostname tested by the site was read from the detailed-results DOM with its category and `blocked`/`accessible` result before curation. DNS rules deliberately target hostnames only: test labels containing a path (for example, `.../gampad/ads`) were reduced to their hostname only when that hostname was already a clearly ad-serving endpoint.

## Intentionally not blocked

The following reachable groups were left out because DNS-wide blocking is likely to break legitimate functionality or because their intent is not sufficiently narrow:

- S3 hosts (`adtago.s3.amazonaws.com`, `analyticsengine.s3.amazonaws.com`, `advice-ads.s3.amazonaws.com`): shared cloud storage can contain non-ad content.
- Core/social APIs and content hosts (`graph.facebook.com`, `graph.instagram.com`, `i.instagram.com`, `connect.facebook.net`, `sc-static.net`, `widgets.pinterest.com`, `vk.com`): can support sign-in, content, widgets, or platform APIs.
- Consent-management hosts (OneTrust, Cookiebot, TrustArc, Usercentrics, Osano, Google Funding Choices): blocking can prevent consent flows and is not a direct ad/telemetry control.
- A/B and product-delivery hosts (Optimizely, Dynamic Yield, LaunchDarkly): may carry feature flags and required application behavior.
- Live-chat/lifecycle delivery (Intercom, Drift, Braze, OneSignal, Klaviyo, Customer.io): may be customer-support or notification functionality.
- General video/CDN endpoints (`redirector.googlevideo.com`, `s.youtube.com`, `g.jwpsrv.com`, `ssl.p.jwpcdn.com`, `prd.jwpltx.com`): may carry legitimate video playback or player resources.
- Configuration/authentication-sensitive vendor endpoints (`firebase-settings.crashlytics.com`, `grs.hicloud.com`): not newly selected. `grs.hicloud.com` was retained because it was a valid pre-existing rule, per the preservation requirement.

## Comparison run

| Metric | Before | After |
|---|---:|---:|
| Protection Score | 12% | 11% |
| Raw Block Rate | 13% (65/482) | 13% (61/482) |
| Blocked probes | 65 | 61 |
| Reachable probes | 417 | 421 |
| Mixed probes | 0 | 0 |

The second run was real and was not manipulated. The update was only saved in this repository: no local AdGuard Home process or configured refresh endpoint was present, so the new list could not be activated safely. The small score difference is therefore normal network/test variance, not an effect claimed for these unpublished rules.

## Validation

- All 295 combined rules match AdGuard DNS syntax: `||hostname^`.
- No malformed rules or duplicate hostnames were found.
- The combined list exactly matches the de-duplicated union of the four category files.

## Limitations

This browser test checks HTTP reachability and cannot prove that DNS filtering performed a particular block. The site's results may vary by request timing, browser behavior, and network. No internal IP addresses, hostnames, credentials, keys, or deployment-specific configuration were collected or written.
