

# Privacy Policy — ProfitCalc NG

**Last updated:** [Date, e.g., September 2026]

## 1. Introduction

ProfitCalc NG ("the App") is an offline-first mobile application for Android designed to help Nigerian traders calculate profits, track daily sales, manage inventory, and record customer debts.

This Privacy Policy explains how the App collects, uses, discloses, and safeguards your information when you install and use the App. It does not apply to any third-party services or websites that may be linked to or from the App.

## 2. Information We Do NOT Collect

The App is designed to be **100% offline**. We do not collect any of the following:

- **Personal data:** Name, email, phone number, or any personally identifiable information.
- **Usage data:** We do not track how you use the App, nor do we collect crash reports or analytics that send data off the device.
- **Location data:** The App does not access or collect your GPS location.
- **Financial data externally:** We do not transmit any of your business data, sales, expenses, or debts to any server or cloud service.
- **Account information:** The App does not require or store user accounts, usernames, or passwords (except the optional local PIN for app lock, stored encrypted on the device).

## 3. Information We DO Store Locally

All data in the App is stored **exclusively on your device**. Nothing is uploaded, synced, or transmitted over the internet except:

- **App settings:** Theme preference (light/dark/system), language (English, Pidgin, Hausa, Yoruba, Igbo), large-text mode, onboarding completion flag, and the "Remove Ads" purchase status.
- **Business data (local only):** Sales records, inventory items, expense entries, customer names and phone numbers (for debt tracking), debt records, product catalog, and daily notes. All such data is stored in AES-encrypted Hive boxes on the device.
- **App lock PIN/biometric settings:** If you enable the PIN or biometric lock, a salted PBKDF2 hash (80k iterations, 32-byte random salt) is stored securely in the platform secure store (Android Keystore / iOS Keychain via `flutter_secure_storage`). Failed-attempt lockout (5 attempts / 30s) is also stored locally.
- **IAP receipt (Remove Ads Forever):** A receipt consisting of order ID, purchase token, and a SHA-256 digest binding them to the product ID. Stored in `flutter_secure_storage` (Android Keystore / iOS Keychain). No server verification is performed — verification is client-side only.
- **Backup files:** If you create an encrypted backup (`.pccbak` format), the file is stored locally and can be shared via the system share sheet. Backups are password-protected (minimum 8 characters) and use AES-256 with PBKDF2-HMAC-SHA256 (120k iterations) and Encrypt-then-MAC integrity protection.

## 3. Third-Party Services

The App integrates the following third-party services, all of which operate within the offline constraint:

- **Google AdMob:** Banner and interstitial ads are loaded at build time via configuration. No user data is shared with AdMob. AdMob may serve ads based on general device settings but does not receive ProfitCalc-specific data.
- **Apple/Google In-App Purchase:** For the "Remove Ads Forever" product. The purchase flow is handled by the respective app store; purchase receipts are stored locally only.
- **Flutter Secure Storage:** Used to hold the master encryption key and IAP receipt. Data stays within the platform secure store and never leaves the device.
- **Local Authentication:** Used only for biometric app lock prompts; no biometric data is transmitted or stored by the App.

## 4. Data Security

All locally stored data is protected as follows:

- **Hive boxes** are encrypted with AES-256 using a master key generated once with `Random.secure()` and stored in the platform secure store.
- **PIN hashes** use PBKDF2-HMAC-SHA256 with 80k iterations and a 32-byte random salt; verification is constant-time.
- **Backup files** use authenticated encryption (AES-CBC with HMAC-SHA256) and a user-supplied password (minimum 8 characters).
- **Backup key** is stored in the platform secure store; `resetOnError: false` ensures the key is never silently wiped.

## 4. Children's Privacy

The App is not directed to children under 13 and does not knowingly collect any data from children. If you are a parent or guardian and believe your child has provided us with personal data, please contact us.

## 5. Your Rights

Because the App does not collect or transmit any personal data outside the device, there are no data export, deletion, or portability requirements across a network. However, you may:

- **Reset all data:** Use "Clear All Data" in Settings, which wipes all business data (except the language choice) and resets to a single default shop.
- **Uninstall the App:** Uninstalling deletes all locally stored data from the device.
- **Export data:** Use the backup feature to create a password-encrypted `.pccbak` file, then share it via your device's share mechanism. You control the distribution of this file.

## 6. Changes to This Privacy Policy

We may update our Privacy Policy from time to time. We will notify you of any changes by posting the new Privacy Policy on this page. You are advised to review this Privacy Policy periodically for any changes.

## 7. Contact Us

If you have any questions or suggestions about our Privacy Policy, please contact us at:

**Email:** [almustaphasaidu55@gmail.com]  
**GitHub:** [https://github.com/almustaphasaidu/ProfitCalc-NG](https://github.com/almustaphasaidu/ProfitCalc-NG)

---

*This Privacy Policy was generated for ProfitCalc NG and reflects the App's offline-first architecture as of the version specified.*
