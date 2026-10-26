<div align="center">

# 📡 NearLink
### The Dynamic NFC Digital Wallet for Android

Turn your Android phone into an instant tap-to-share digital business card and link broadcaster.

[![Platform](https://img.shields.io/badge/Platform-Android-3DDC84?logo=android&logoColor=white)](#requirements--compatibility)
[![Language](https://img.shields.io/badge/Language-Kotlin-7F52FF?logo=kotlin&logoColor=white)](https://kotlinlang.org)
[![Privacy](https://img.shields.io/badge/Privacy-100%25_Local_%26_Offline-green)](#privacy--security)
[![Privacy Policy](https://img.shields.io/badge/Privacy%20Policy-View-blue)](PRIVACY.md)

[**Download on Google Play**](https://play.google.com) *(Coming Soon)* • [**Privacy Policy**](PRIVACY.md) • [**Report Bug**](https://github.com/Drake2Dev/NearLink/issues)

</div>

---

## 📱 Screenshots

<div align="center">

| Empty State | Saved Cards | Active NFC Broadcast | Settings & Backup |
|:---:|:---:|:---:|:---:|
| <img src="screenshots/empty_state.png" width="210" alt="Empty State" /> | <img src="screenshots/cards_list.png" width="210" alt="Cards List" /> | <img src="screenshots/broadcasting.png" width="210" alt="Active NFC Broadcast" /> | <img src="screenshots/settings_sheet.png" width="210" alt="Settings & Backup" /> | <img src="screenshots/dark_theme.png" width="210" alt="Dark Theme" /> | <img src="screenshots/photo1.jpg" width="210" alt="Photo 1" /> | <img src="screenshots/photo2.jpg" width="210" alt="Photo 2" /> |

</div>

---

## 📖 Overview

**NearLink** transforms your Android smartphone into an on-demand, customizable NFC tag using **Host Card Emulation (HCE)**. Whether you are networking at a conference, pitching a portfolio to a client, or exchanging social handles, NearLink lets you beam any URL directly to another NFC-compatible smartphone with a single tap. 

Ditch stacks of paper business cards, separate hardware tag programmers, or static physical tags. NearLink brings dynamic, switchable NFC link broadcasting right into your pocket.

---

## ✨ Features

- 🗂️ **Digital Card Wallet:** Organize personal links, social profiles, business cards, portfolios, or quick payment URLs into a clean, distraction-free interface.
- ⚡ **One-Tap NFC Emulation:** Tap any card to activate NDEF broadcasting. The card illuminates with a green glow and status indicator to confirm you are live. Tap it again to immediately turn off broadcasting.
- 🛠️ **Long-Press Card Actions:** Long-press any card to bring up dedicated **Edit** and **Delete** actions. Tap anywhere outside the card to exit action mode safely.
- 💾 **JSON Backup & Restore:** Export your entire card collection to a clean `.json` file and save it wherever you want via Android's native file picker. Easily import it onto another device with automatic duplicate detection.
- 🛡️ **Optional Confirmation Safety:** Enable confirmation prompts in Settings to prevent accidental card deletions or edits.
- 🌓 **Dynamic Theme Support:** Built-in Light and Dark mode toggles optimized for battery conservation and low-light environments.
- 🔒 **100% Private & Offline:** Zero analytics, zero ad trackers, zero telemetry, and no account required. All data remains stored exclusively on your device's local memory.

---

## 🚀 How to Use NearLink

### 1. Creating a Link Card
1. Open NearLink and tap **`+ Create New Link`** at the bottom of the screen.
2. Enter a descriptive **Card Name** (e.g., *Personal Website*, *LinkedIn*, *GitHub*).
3. Enter the target **URL** (e.g., `github.com/Drake2Dev`). *(If no protocol is provided, NearLink will automatically prepend `https://`)*.
4. Tap **Save**.

### 2. Broadcasting via NFC
1. Make sure **NFC** is turned **ON** in your Android device's system settings.
2. In NearLink, **tap the card** you want to transmit.
3. The card will turn green and display:  
   `● Broadcasting – hold your phone near a reader`
4. Hold the back of your phone near the NFC sweet spot of the recipient's smartphone or NFC reader.
5. Tap the card again at any time to **Stop Broadcasting**.

### 3. Editing or Deleting Cards
1. **Long-press** the card you wish to modify.
2. The card elevates and reveals **Edit** and **Delete** buttons:
   - **Edit:** Opens the dialog to update the name or URL.
   - **Delete:** Removes the card from your list (with a confirmation modal if enabled in settings).
3. To dismiss the edit/delete overlay without making changes, simply tap anywhere outside the card or press the back button.

---

## 🔄 Import & Export (Backup & Migration)

NearLink uses the Android Storage Access Framework (SAF) to let you backup and restore your links without granting broad storage permissions.

### Exporting Your Cards
1. Tap the **Settings (gear)** icon in the top right corner.
2. Select **Export cards to file**.
3. Choose your desired save location (Internal Storage, SD Card, Google Drive, etc.) using the Android file picker.
4. NearLink generates a timestamped backup named:  
   `NearLink-backup-YYYY-MM-DD.json`

### Importing Cards
1. Tap the **Settings (gear)** icon.
2. Select **Import cards from file**.
3. Select any valid NearLink backup `.json` file.
4. NearLink parses the file and merges your cards. Duplicates already present in your wallet are automatically skipped.

---

## 📋 Requirements & Compatibility

| Requirement | Specification |
|:---|:---|
| **Operating System** | Android 8.0 (Oreo / API Level 26) or higher |
| **Hardware** | Built-in NFC chip with **Host Card Emulation (HCE)** support |
| **Target Audience Device** | Any NFC-enabled smartphone (iOS or Android) capable of reading standard NDEF URI tags |
| **Permissions** | `android.permission.NFC` *(No internet or broad file-storage permissions required)* |

> **Note on Receiving Devices:**  
> - **iPhones:** iPhone XS and newer read background NDEF URLs automatically without opening an app.  
> - **Android:** Most modern Android devices read NDEF URLs automatically when unlocked.

---

## ❓ Troubleshooting & FAQ

#### Why doesn't the other phone open my link?
1. **Check NFC Sweet Spots:** NFC antenna locations vary between devices. On iPhones, the NFC sensor is at the very top edge. On Android phones, it is typically in the center or near the camera bump.
2. **Device Must Be Unlocked:** For security, most phones do not read NFC tags while the lock screen is asleep. Ensure the receiving phone is awake and unlocked.
3. **Turn Off Contactless Payment Interference:** If the receiving phone opens Google Wallet or Apple Pay instead of your link, hold the devices at a slight angle or ensure you are transmitting an NDEF URI format.

#### Does NearLink broadcast when the app is closed?
NearLink only broadcasts while the app is active and a card is explicitly selected. As soon as you deselect the card or terminate the app, HCE broadcasting stops to save battery and prevent unintentional transfers.

#### Can I format links as phone numbers or emails?
Yes. NearLink supports standard URI schemes including:
- Web links: `https://example.com`
- Direct email: `mailto:hello@example.com`
- Direct phone call: `tel:+1234567890`

---

## 🛠️ Built With

- **[Kotlin](https://kotlinlang.org/)** – Modern, concise programming language for Android.
- **[Android Jetpack](https://developer.android.com/jetpack)** – RecyclerView, Material Components, Edge-to-Edge window insets.
- **[Host Card Emulation (HCE)](https://developer.android.com/guide/topics/connectivity/nfc/hce)** – Standards-compliant emulation of NDEF Type 4 tags over ISO-DEP.
- **[Gson](https://github.com/google/gson)** – Fast, local JSON serialization for wallet storage and backups.

---

## 🔒 Privacy & Terms

NearLink does not collect, transmit, track, or share any personal data[cite: 2]. All links, preferences, and backups remain 100% offline and stored strictly on your local device[cite: 2].

For complete details on data handling and device permissions, please refer to our [Privacy Policy](PRIVACY.md).

All rights reserved by [Drake2Dev](https://github.com/Drake2Dev).

---

<div align="center">
  <sub>Developed with ❤️ by <a href="https://github.com/Drake2Dev">Drake2Dev</a></sub>
</div>
