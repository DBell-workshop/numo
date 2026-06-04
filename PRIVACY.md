# Numo Privacy Policy

> Public copy lives at <https://dbell-workshop.github.io/numo/PRIVACY.html>. This URL is the one filed with App Store Connect.

---

**Effective Date**: 2026-06-03
**App**: Numo: AI Calculator
**Developer**: Beijing Linkos Culture & Technology Co., Ltd. (北京灵可司文化科技有限公司)
**Contact**: support@linkos.cc

## TL;DR

- **Numo Pro** (one-time purchase) collects **zero data**. Math, voice recognition, and receipt OCR all run on your device. No ads, no network, no tracking.
- **Numo Free** runs the same on-device math, voice, and OCR. But it also shows **one launch-screen ad** per cold start, served by Google AdMob. The ad request may collect device identifiers (subject to your iOS App Tracking Transparency choice). Everything else is still on-device.
- You can opt out of personalised ads by denying the ATT prompt on first launch, and you can remove ads entirely by upgrading to Numo Pro.

## What Numo does on your device (and only on your device)

These data live **only on your device** and never leave it:

- **Camera frames** — captured only when you tap the receipt-scan button (`doc.text.viewfinder` icon in the top bar). Frames are fed directly into Apple Vision's on-device OCR. We do not save the photo to your Camera Roll, do not buffer it to disk, and do not transmit it.
- **Microphone audio** — captured only when you tap the mic pill or long-press for dialog mode. Audio is streamed to Apple Speech with `requiresOnDeviceRecognition = true` whenever supported. Not saved, not transmitted.
- **Recognized text** (from OCR) and **transcribed math expressions** (from voice) — held in app memory for the duration of the calculation, then discarded when you start a new one.
- **Calculator state and chat timeline** — your last expression, hero result, and the chat-style history of past calculations. Persisted to your local `UserDefaults` so the app resumes where you left off. Never read by anyone but Numo, on this device.
- **User preferences** — speech mode, haptics, theme, IAP entitlement (Pro / Free), PIPL consent state on China-region devices. Persisted to local `UserDefaults`.

## Data collected by the free version's ad SDK

Numo Free shows **one App Open ad** per cold launch via **Google AdMob** (Google's mobile advertising SDK, version 13.x). To serve and measure that ad, AdMob and its supporting framework (User Messaging Platform, UMP) may collect:

- A resettable advertising identifier (IDFA on iOS) — **only if you accept the iOS App Tracking Transparency prompt**. If you decline, AdMob falls back to non-personalised ads with no IDFA.
- Coarse device and OS information (model, language, region, OS version).
- Approximate location derived from IP address. We do not request GPS.
- Standard ad-serving signals (impression, click, viewability), tied to the identifier above.

We at Linkos **do not receive your identifier, your IP address, or any per-user data**. We only see aggregated revenue and impression counts in AdMob's dashboard.

Google's handling of this data is governed by the [Google Privacy Policy](https://policies.google.com/privacy) and [How Google uses information from sites or apps that use our services](https://policies.google.com/technologies/partner-sites).

### Numo Pro disables all of the above

Purchasing **Numo Pro** (a one-time, non-consumable in-app purchase) removes the ad-serving code path entirely. After upgrading:

- No ad SDK initialisation.
- No ad requests.
- No identifier exchange.
- The ATT prompt is not shown.

If you have already accepted the ATT prompt before upgrading, you can revoke it any time via **iOS Settings → Privacy & Security → Tracking → Numo**.

## Permissions Numo asks for

| Permission | When asked | What it's used for | What happens if you deny |
|---|---|---|---|
| **Camera** | First tap of the receipt-scan button | On-device OCR of paper receipts and price tags via Apple Vision | Receipt scanning is unavailable. Voice and keypad input still work. |
| **Microphone** | First tap of the mic pill | Voice input for math expressions and dialog mode | Voice input is unavailable. Keypad and receipt scan still work. |
| **Speech Recognition** | First mic use | Local on-device transcription (Apple Speech) | Same as above. |
| **App Tracking Transparency (Free only)** | First cold launch with ads enabled | Allows AdMob to use your IDFA for ad personalisation | Ads still show, but as non-personalised; behaviourally a non-event. |

Numo does **not** request access to your contacts, photos library (the camera permission scans only the live viewfinder, never your stored photos), calendar, location services, health data, motion, or HomeKit.

You can revoke any permission at any time via iOS **Settings → Privacy & Security → [Permission name] → Numo**.

## Network usage

- **Numo Pro**: zero network requests. The app functions identically in airplane mode.
- **Numo Free**: one ad request per cold launch, sent to Google AdMob's endpoint. No other Numo feature uses the network. Voice recognition, OCR, math evaluation, and the chat timeline are all 100% local. The app continues to work in airplane mode, only without the launch ad.

## Third-party services

Numo Free embeds the following third-party SDKs:

- **Google Mobile Ads SDK** (`GoogleMobileAds`, v13.4 or later) — serves the cold-launch App Open ad.
- **Google User Messaging Platform** (`UserMessagingPlatform`, v3.x) — manages GDPR consent in EU/UK regions.

No analytics SDK, no crash-reporting SDK from a third party, no telemetry SDK, no social-login SDK. Crash and performance data, when present, are processed locally via Apple's [MetricKit](https://developer.apple.com/documentation/metrickit) framework and held in your device's Application Support directory; they never leave your phone.

**Numo Pro** strips all of the above out of the runtime — even though the code paths exist in the binary, they are gated by a Pro check at startup and never execute.

## Mainland-China users (PIPL compliance)

On first launch in the mainland-China region, Numo presents a **PIPL transparency sheet** explaining the above data flows, with separate consents for:

1. Local-only processing (OCR, voice, math — required for the app to function).
2. Ad SDK data flows (free version only).
3. ATT identifier sharing (optional, per iOS prompt).

Consent state is logged to local `UserDefaults` and can be revoked from **Settings → Privacy → Reset Privacy Choices**, which clears the consent record and re-presents the prompts on next launch.

The data processor for the ad-related flows is **Google LLC, 1600 Amphitheatre Parkway, Mountain View, CA 94043, USA**. We at Linkos do not process or receive your personal data; we only see aggregated AdMob dashboard metrics.

## Children's privacy

Numo is rated 4+ on the App Store. We do not knowingly collect data from children. Numo Free's ad SDK serves only non-personalised, family-safe ads to users under 13 (per AdMob's standard child-directed treatment), and Numo Pro shows no ads at all. The other data flows (OCR, voice, math) are 100% on-device for all ages.

## Changes to this policy

If we change Numo's privacy posture, we will update this document **and** the App Store Privacy Nutrition Label before the new version ships. Substantive changes are reflected in the **Effective Date** above.

## Your rights

Because we (Linkos) hold no personal data about you on our own servers, there is no Linkos data to access, export, correct, or delete. For data Google AdMob may hold about your device's ad interactions, see Google's [data subject request](https://support.google.com/policies/troubleshooter/7575787) flow.

To clear all local Numo state on your device:

1. **iOS Settings → General → iPhone Storage → Numo → Offload App** (preserves data) or **Delete App** (wipes everything).

## Contact

Questions, concerns, accessibility feedback, or "are you sure you don't collect anything in Pro?" emails:

**support@linkos.cc**

---

*This document is the canonical privacy policy for Numo. The App Store Privacy Nutrition Label is filled in to match: Numo Pro = "Data Not Collected"; Numo Free = "Identifiers (Linked for Third-Party Advertising)" and "Diagnostics (Linked for Third-Party Advertising)" via the AdMob SDK, contingent on the user's ATT choice.*
