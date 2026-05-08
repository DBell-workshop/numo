# Numo Privacy Policy

> Public copy lives at <https://dbell-workshop.github.io/numo/PRIVACY> (mirrored from the private `mitools` repo). The URL on GitHub Pages is the one filed with App Store Connect.

---

**Effective Date**: 2026-05-08
**App**: Numo (the MiTools Calculator)
**Developer**: Beijing Linkos Culture & Technology Co., Ltd.
**Contact**: support@linkos.cc

## TL;DR

Numo collects **nothing**. No analytics, no tracking, no telemetry, no
account, no cloud sync. Everything — math, voice recognition, voice
playback — runs on your device only. We never see what you calculate,
what you say, or what you hear.

## Data we collect

**None.**

We do not collect, store, transmit, or sell any personal data. We do
not use any third-party SDK, analytics tool, or advertising network.
Numo does not require an account and does not have a sign-in flow.

## Data the device handles locally

These pieces of data exist **only on your device** and never leave it:

- **Microphone audio** — captured only when you tap the mic button.
  Audio is streamed directly to Apple's on-device speech recognizer
  (`SFSpeechRecognizer.requiresOnDeviceRecognition = true`). It is
  not buffered, saved to disk, or sent over the network.
- **Recognized text** — the transcribed math expression. Held in app
  memory only for the duration of the calculation, then discarded.
- **Calculator state** — the current display, expression, and pending
  operation. Held in app memory; not persisted to disk.
- **User preferences** — three toggles (TTS readout on/off, haptics
  on/off, theme) saved to your local `UserDefaults`. Never read by
  anyone but Numo itself, on this device.

## Permissions Numo asks for

- **Microphone** — to listen to your math expressions when you tap mic.
- **Speech Recognition** — to convert what you say into numbers, locally.

That's it. Numo does not request network access, contacts, photos,
calendars, location, or anything else.

You can revoke either permission at any time via iOS **Settings → Privacy
& Security**. Numo continues to work without them; only the voice-input
feature becomes unavailable.

## Network usage

Numo makes **zero network requests**. We do not contact any server,
including our own. The app functions identically in airplane mode.

This includes the optional **AI Boost** feature: when enabled, Numo
uses Apple's on-device Foundation Models framework (Apple Intelligence)
which runs locally on your device's Neural Engine. There is no model
download, no API call, and no server roundtrip.

## Children's privacy

Numo is rated 4+ on the App Store. We do not knowingly collect any
information from children, because we do not collect any information
from anyone.

## Changes to this policy

If we ever change Numo's privacy posture (we don't plan to), we will
update this document and the App Store Connect Privacy Nutrition Label
before the new version ships. Substantive changes will be reflected in
the **Effective Date** above.

## Your rights

Because we hold no data about you, there is no data to access, export,
correct, or delete. You can clear all your in-app preferences by:

1. iOS Settings → General → iPhone Storage → Numo → Offload App
   (preserves data) or Delete App (wipes preferences).

## Contact

Questions, concerns, or "are you sure you don't collect anything?"
emails:

**support@linkos.cc**

---

*This document is the canonical privacy policy for Numo. The App
Store Privacy Nutrition Label is filled in to match: "Data Not
Collected" across all categories.*
