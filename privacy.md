---
layout: page
title: Privacy Policy
permalink: /privacy.html
---

# Privacy Policy — Nature+ EBookReader

> **⚠ DRAFT — NOT YET REVIEWED BY LEGAL COUNSEL.**
> This draft was generated to reflect the app's actual data-handling
> behaviour as observed in the codebase. Before publishing this document
> on a public URL or referencing it from the app, you must:
> 1. Have it reviewed by a privacy lawyer for your target jurisdictions
>    (especially if launching in the EU/UK, California, or to children).
> 2. Confirm every factual claim still matches the shipped app —
>    re-check on every release.
> 3. Replace every `[BRACKETED PLACEHOLDER]` below with real values.

**Effective Date:** 2026-05-04
**Last Updated:** 2026-05-04

---

## 1. Who we are

Nature+ EBookReader (the "App") is published by **[DEVELOPER LEGAL NAME]**
("we", "us", "our"). For privacy questions, contact us at
**[PRIVACY CONTACT EMAIL]**.

The App is distributed through the Google Play Store. Your installation
of the App is governed by Google Play's terms in addition to ours.

## 2. Summary — what we do and don't collect

**We do not operate a server.** We do not collect, store, or transmit
your reading data to any system we control.

* Books, annotations, notes, highlights, reading progress, study
  sessions, and your preferences are stored **locally on your device**.
* Optional cloud sync sends your data to **your own** cloud account
  (Google Drive, Dropbox, OneDrive, or WebDAV) — we never see it.
* Android's system-level Auto Backup may copy a subset of app data to
  your **own** Google Drive backup; you control this via your Google
  Account settings.
* The App displays advertising via Google AdMob (free tier only).
  AdMob may collect device-level identifiers and ad-targeting data —
  see Section 6.

## 3. Data the App handles

### 3.1 Locally stored data (never transmitted by us)

The following stays on your device unless you opt into cloud sync:

* Books you import (file paths and content excerpted for indexing).
* Reading progress: current page, total time read, last-opened time,
  per-book reading sessions.
* Annotations: highlights, underlines, sticky notes, image clips,
  pencil drawings, quote blocks.
* Flashcards and the Spaced-Repetition (SM-2) state used by Daily
  Recap.
* Reading preferences: theme, font, line spacing, auto-margin, page
  flip animation, TTS speed and voice, custom photo wallpaper.
* Pomodoro session history.
* Kids Mode state and the local PIN (the PIN is stored in
  EncryptedSharedPreferences and never transmitted).

This data is removed when you uninstall the App.

### 3.2 Data sent to your own cloud accounts (opt-in, Pro feature)

If you enable cloud sync and authenticate with one of the supported
providers, the App uses **OAuth** to upload selected data to
**your** cloud storage:

| Provider | What is uploaded |
|---|---|
| Google Drive | App-folder data: annotations, reading state, preferences, optionally book files. |
| Dropbox | Same scope. |
| OneDrive | Same scope. |
| WebDAV | Same scope, against the server URL you supply. |

We do not have access to your cloud account. To revoke access, sign
out from inside the App or revoke the App from your provider's
security/connected-apps settings.

### 3.3 Android Auto Backup

When Backup is enabled in your Google Account, Android may copy the
following to your own Google Drive backup quota (encrypted with a key
known only to your device family):

* Room database files (library, annotations, reading progress,
  flashcards).
* DataStore preferences.
* Book cover thumbnails.
* The Pro Preview activation record (a small encrypted blob bound to
  your device's hardware fingerprint).

**Excluded from backup:** OAuth credentials, EncryptedSharedPreferences
contents (including the Kids Mode PIN), and any Dropbox / WebDAV
configuration. These reset when the App is restored to a new device.

You can disable Auto Backup per-app in **Settings → Google → Backup →
App data** on your device.

### 3.4 Time synchronisation (Pro Preview only)

To prevent users from extending the 3-hour Pro Preview trial by
changing their device clock, the App fetches the current time from
**`time.google.com`** (Google's public NTP server) when a Preview is
activated and again every minute while it runs. The fetch sends only
your device's IP address; no App-specific identifier is included.

## 4. Permissions

| Permission | Why we request it |
|---|---|
| Storage (read external storage / scoped storage) | To scan folders you choose for `.epub`, `.pdf`, and other supported book files. We never read files outside the folders you grant. |
| Internet | To display ads, run Pro Billing, perform optional cloud sync, and fetch SNTP time for Pro Preview validation. |
| Notifications | Daily Recap reminders, Pomodoro timer alerts, reading reminders, and TTS playback controls. |
| Foreground Service (special use: Pomodoro) | Keeps the focus timer accurate when the App is in the background. |

You can revoke any permission via your device's system Settings.

## 5. Pro purchase

Pro is a one-time, in-app purchase processed by **Google Play
Billing**. We receive a purchase token from Google Play, which we use
solely to confirm your entitlement on this device. We do not see your
payment details (Google Play handles the transaction). The token is
stored in Google Play's billing library cache on your device and
mirrored to a small DataStore cache so the entitlement evaluates
immediately on cold start.

## 6. Third-party SDKs

### 6.1 Google AdMob (free tier only)

The free tier of the App displays banner, interstitial, and rewarded
ads via Google AdMob. AdMob may collect:

* Your device's advertising identifier.
* Approximate location (derived from IP), device model, OS version,
  app session data.
* Ad-interaction data (impressions, clicks).

Google's privacy practices are described at
<https://policies.google.com/technologies/ads>. You can reset or opt
out of personalised advertising via your device's Settings → Privacy →
Ads.

For users in regions covered by the GDPR, the UK GDPR, or CCPA, the
App presents Google's User Messaging Platform (UMP) consent dialog on
first launch in the affected region. Your consent or non-consent
choice is stored by the UMP SDK and applies to subsequent ad requests.

**Pro users see no ads.** AdMob is not initialised at all when Pro is
detected at app start.

### 6.2 Google Play Billing

See Section 5.

### 6.3 ML Kit (on-device)

The App uses Google ML Kit for the following on-device features. These
SDKs run inference locally on your device and do not transmit text
content to Google:

* **On-Device Translation** — translate selected passages or full
  pages into 59 supported languages. Language packs are downloaded on
  first use.
* **Entity Extraction** — used to generate fact-shaped flashcards from
  passages you select.

ML Kit may report aggregated, anonymised model-performance metrics to
Google. See <https://developers.google.com/ml-kit/terms> for details.

### 6.4 Children's apps and COPPA

Kids Mode marks ad requests as **child-directed** so AdMob does not
serve personalised ads in a Kids session, in compliance with COPPA
and Google Play's Designed-for-Families policy. Reading sessions
captured under Kids Mode stay on the device and are not transmitted.

In addition, **all advertising surfaces are suppressed entirely while
Kids Mode is active** — neither rewarded nor interstitial ads load or
display, regardless of the COPPA flags. The COPPA configuration
operates as defence-in-depth so that any AdMob caching from before
the toggle cannot serve a personalised or non-G-rated ad in a Kids
session.

If you believe a child under 13 is using the App without parental
consent, please contact us at **[PRIVACY CONTACT EMAIL]** so we can
provide guidance on data deletion.

### 6.5 Children's data — DPDP Act, 2023 (India) §9

The Digital Personal Data Protection Act, 2023 §9 prohibits the
processing of children's personal data without verifiable parental
consent and bans behavioural monitoring and targeted advertising
directed at children (defined as persons under 18 years of age in
India — a stricter standard than COPPA's under-13).

Nature+ EBookReader's compliance posture under §9 is structural:

* **No behavioural or targeted advertising in Kids Mode.** All
  advertising surfaces are suppressed during a Kids Mode session;
  neither AdMob nor any other third-party SDK requests personalised
  ad inventory.
* **No behavioural tracking.** The App ships with no analytics
  framework, no telemetry SDK, no developer-controlled server. We
  process no personal data from any user — child or adult — on
  systems we control.
* **PIN-protected parental control.** Kids Mode entry and exit
  require a parental PIN stored in EncryptedSharedPreferences on the
  device. The PIN is never transmitted and is excluded from
  Auto Backup.
* **Local-only reading sessions in Kids Mode.** Reading time, books
  opened, and any annotations made during a Kids session are stored
  locally on the device for the user's own viewing within the App
  (e.g., the parent reviewing a child's reading history). This is
  app-state data, not analytics — it is not transmitted to any
  developer-controlled server or third-party telemetry SDK, because
  none exist. The data is uploaded to an external service only if a
  paying parent has separately opted into Pro cloud sync against
  their own cloud account.

Indian parents or guardians may raise concerns about the handling
of a child's personal data through the Grievance Officer designated
in §11. We respond within the period prescribed by the Digital
Personal Data Protection Rules.

## 7. Data retention and deletion

* **Local data** — retained on your device until you delete a book,
  clear app data, or uninstall the App.
* **Cloud-synced data** — stored on your cloud provider's servers
  according to **their** retention policies. We have no copy. Sign out
  of the provider in the App (or revoke access from the provider's
  console) to stop further sync. Deletion of already-uploaded files is
  performed via your cloud provider.
* **Auto Backup data** — managed by your Google Account. Delete via
  **drive.google.com → Backups → [Device] → [App] → Delete**.
* **Pro purchase record** — managed by Google Play. Refund or revoke
  via the Play Store.

## 8. International data transfers

Because cloud sync runs against globally-distributed providers (Google
Drive, Dropbox, OneDrive), data uploaded under your account may be
processed in countries other than your country of residence. We have
no role in or control over those transfers.

## 9. Your rights

Depending on your jurisdiction, you may have the right to:

* Access the personal data we hold about you (we hold none on our
  servers; all retrieval is from your device or your own cloud).
* Request deletion (uninstall the App and revoke cloud-provider
  access).
* Opt out of personalised advertising (UMP consent dialog or device
  Settings → Privacy → Ads).
* Export annotations and notes (Settings → Export Annotations).
* Lodge a complaint with a data-protection authority.

To exercise any right, contact us at **[PRIVACY CONTACT EMAIL]**.

## 10. Changes to this policy

We may update this policy from time to time. The "Last Updated" date
above reflects the current version. Material changes will be flagged
in-app on next launch where practical.

## 11. Grievance Officer (India — DPDP Act, 2023)

In compliance with the Digital Personal Data Protection Act, 2023,
Indian-resident users may raise grievances regarding the processing
of their personal data through the Grievance Officer designated
below. We respond within the period prescribed by the Digital
Personal Data Protection Rules.

The Grievance Officer role is held by the developer personally —
emails are read and answered directly, not routed through a corporate
support system. Most queries about Nature+ EBookReader can be
answered briefly because the App processes no personal data on
servers we control; please describe your concern in plain language
and we will reply with the relevant facts about what (if anything)
the App holds about you.

**Grievance Officer:** [DEVELOPER LEGAL NAME]
**Email:** [PRIVACY CONTACT EMAIL]
**Postal Address:** [DEVELOPER POSTAL ADDRESS], Hyderabad, Telangana, India

## 12. Contact

**[DEVELOPER LEGAL NAME]**
**[DEVELOPER POSTAL ADDRESS]**, Hyderabad, Telangana, India
**Privacy queries:** [PRIVACY CONTACT EMAIL]

---

*This document is the binding privacy policy for the Nature+
EBookReader Android application as published on Google Play.*
