# Photomancy Privacy Policy

**Effective Date:** January 24, 2026
**Last Updated:** February 5, 2026

---

## 1. Introduction

Welcome to Photomancy ("App," "we," "our," or "us"). This Privacy Policy describes how we collect, use, and protect your information when you use our App.

Photomancy is a mystical photo oracle app that transforms your photos into personalized oracle card readings using artificial intelligence.

By using Photomancy, you agree to the practices described in this Privacy Policy. Please also review our [Terms of Use](https://artyomvasilyev.github.io/photomancy/terms).

---

## 2. Data We Collect

### Data You Provide
We access data only when you use the App's features:

| Data Type | What We Access | Purpose |
|-----------|----------------|---------|
| **Photos** | Individual photos randomly selected from your library | To generate oracle card readings |
| **Photo Metadata** | Date, time, location (if available), favorite/edited status | To personalize your reading |
| **Device Identifier** | A random unique ID stored securely on your device (iOS Keychain) | To enforce daily card limits and prevent abuse |
| **Language Preference** | Your device's language setting | To generate readings in your language |
| **Subscription Status** | Your current subscription tier | To determine daily card limits |

### Device Identifier Compliance

Our device identifier is **not device fingerprinting**. We comply with Apple's guidelines by:
- Generating a random UUID (not derived from device characteristics)
- Storing it securely in the iOS Keychain
- Using it solely for rate limiting and abuse prevention
- Never using it for advertising or cross-app tracking

This approach is consistent with Apple's App Store Review Guidelines and does not violate Section 5.1.2 (Device Fingerprinting).

### Data We Do NOT Collect
- We do **not** access your entire photo library
- We do **not** collect your name, email, or contact information
- We do **not** use analytics or tracking SDKs
- We do **not** collect device identifiers for advertising
- We do **not** use cookies or web tracking
- We do **not** derive identifiers from device characteristics (no fingerprinting)

---

## 3. Third-Party Services

### Important Disclosure (Apple Guideline 5.1.2i)

**Photomancy uses third-party services to provide its core functionality. By using this App, you consent to the following data sharing:**

| Service | Provider | Data Shared | Purpose |
|---------|----------|-------------|---------|
| **Firebase Authentication** | Google LLC | Anonymous user ID only | Authenticate API requests and enforce rate limits |
| **Firebase Cloud Functions** | Google LLC | Your selected photo + metadata (in transit only) | Securely process photos through our backend |
| **GPT-4o Vision** | OpenAI, Inc. | Your selected photo + metadata | Analyze photo and generate oracle interpretation |
| **DALL-E 3** | OpenAI, Inc. | Text prompt (no photo) | Generate mystical artwork for your card |
| **Spotify** | Spotify AB | None from us | Song recommendations can open in Spotify (user choice) |
| **Apple Music** | Apple Inc. | None from us | Song recommendations can open in Apple Music (user choice) |

**What this means:**
- When you generate a card, your selected photo is sent to our secure Firebase backend, which then forwards it to OpenAI's services
- Your photo passes through Google's Firebase infrastructure (encrypted in transit) but is **not stored** on our servers
- OpenAI processes your photo to create your personalized reading
- According to OpenAI's API Terms, data sent via their API is **not used to train their models**
- Firebase stores only an anonymous user ID and a daily usage counter (see section 4)

**Third-party privacy policies:**
- Firebase/Google: [https://firebase.google.com/support/privacy](https://firebase.google.com/support/privacy)
- OpenAI: [https://openai.com/privacy](https://openai.com/privacy)
- Spotify: [https://www.spotify.com/privacy](https://www.spotify.com/privacy)
- Apple Music: [https://www.apple.com/legal/privacy](https://www.apple.com/legal/privacy)

**You can choose not to use this feature** — the App requires photo processing to function. If you do not consent, please do not use the App.

---

## 4. Data Storage & Retention

| Data | Storage Location | Retention |
|------|------------------|-----------|
| **Generated oracle cards** | Your device only (local) | Until you delete the App |
| **App preferences** | Your device only (local) | Until you delete the App |
| **Anonymous user ID** | Firebase Authentication | Until you delete the App or uninstall |
| **Daily usage counter** | Firebase Firestore | Forever (contains only: anonymous ID, date, count) |
| **Device identifier** | Firebase Firestore | Forever (used to enforce rate limits across reinstalls) |
| **Photos (in transit)** | Firebase/OpenAI servers | Not stored — processed and immediately discarded |
| **Generated images** | OpenAI CDN | Up to 1 hour (temporary URLs), then deleted |

**What we store in Firebase Firestore:**
```
users/{anonymous_user_id}/cards/{DD-MM-YYYY}
  - count: 2 (how many cards generated today)
  - lastGeneratedAt: timestamp

devices/{device_identifier}
  - lastGeneratedAt: timestamp (for rate limiting)
```

**What we DO NOT store:**
- Your original photos (never saved to our servers)
- Your generated oracle card images (only temporary URLs returned)
- Any personally identifiable information
- Your photo library contents

**Important:** Once you delete the App, you will lose access to all your saved oracle cards. We cannot recover them because they are only stored on your device, not our servers.

---

## 5. International Data Transfers

When you use Photomancy, your photo data is transferred to servers located in the United States. If you are located in the European Union, United Kingdom, or other regions with data protection laws, please be aware that:

- Your data will be processed in the United States (Firebase servers and OpenAI servers)
- Google (Firebase) and OpenAI maintain appropriate safeguards for international transfers
- Your data is encrypted in transit using TLS/HTTPS
- By using this App, you consent to this transfer

---

## 6. Your Rights

### All Users
- **Access**: View your generated cards within the App
- **Deletion**: Delete the App to remove all local data
- **Revoke Photo Access**: Disable photo permissions in device Settings at any time
- **Opt Out**: Stop using the App to prevent any data processing

### European Union Residents (GDPR)

Under the General Data Protection Regulation, you have the following rights:

**Rights we can fulfill:**
- **Right to Access**: Your generated cards are stored locally on your device and visible in the App
- **Right to Erasure (Local Data)**: Delete the App to remove all locally stored data immediately
- **Right to Withdraw Consent**: Stop using the App at any time; uninstall to revoke photo access

**Rights with limitations:**
- **Data sent to OpenAI**: Once a photo is sent to OpenAI for processing, we cannot retrieve or delete it from their servers. According to OpenAI's data retention policy, API data is retained for up to 30 days for abuse monitoring, then automatically deleted. We do not have access to OpenAI's systems to request deletion on your behalf.

**Legal Basis for Processing:** Consent — by choosing to generate an oracle card, you consent to your photo being processed by OpenAI.

**Data Controller:** For local data, you control your own data on your device. For data processed by OpenAI, OpenAI acts as a data processor under their own policies.

### California Residents (CCPA/CPRA)

Under the California Consumer Privacy Act:

- **Right to Know**: See Section 2 of this policy for what we collect
- **Right to Delete**: Delete the App to remove all local data. Data sent to OpenAI is automatically deleted after 30 days per their policy.
- **Right to Opt-Out**: We do **not sell** your personal information
- **Non-Discrimination**: We will not discriminate against you for exercising your rights

**Note:** We do not maintain a database of user information. We cannot look up or delete specific user data because we don't store it.

---

## 7. Children's Privacy

Photomancy is intended for users **13 years of age or older**. We do not knowingly collect data from children under 13. If you believe a child under 13 has used our App, please contact us.

---

## 8. Security

We implement reasonable security measures:
- Photos are transmitted over encrypted HTTPS connections
- Local data is stored in iOS's sandboxed app container
- Device identifier is stored in iOS Keychain (Apple's secure credential storage)
- We do not store photos or personal data on external servers

---

## 9. Changes to This Policy

We may update this Privacy Policy periodically. We will indicate the "Last Updated" date at the top. Continued use of the App after changes constitutes acceptance of the updated policy.

---

## 10. Contact Us

For questions, concerns, or to exercise your privacy rights:

**Email:** artyom.vasilyev@outlook.com

---

## 11. Apple App Privacy Details

For transparency, here is how we categorize our data practices per Apple's requirements:

| Category | Collected? | Linked to Identity? | Used for Tracking? |
|----------|------------|---------------------|-------------------|
| Photos | Yes | No | No |
| Location (from photos) | Yes (if available) | No | No |
| Usage Data | No | — | — |
| Identifiers | Yes (random device ID for rate limiting) | No | No |
| Diagnostics | No | — | — |

---

*This policy complies with Apple App Store requirements, GDPR, and CCPA.*
