# PS4 & PS5 PKG Sender 📦🚀

https://www.mediafire.com/file/cpbb0rcbj70pms3/ps4-ps5-pkg-sender-0.9.1beta.apk/file

A modern, feature-rich Android application designed to seamlessly transfer and install `.pkg` files on PlayStation 4 and PlayStation 5 consoles over your local Wi-Fi network.

Developed with **Jetpack Compose (Material Design 3)**, the app features full support for **GoldHEN FTP Direct Streaming**, **Remote Package Installer (RPI)**, an integrated **Homebrew Store**, an internal **Archive Extractor**, **Automated PKG Categorization**, **Horizontal Marquee Filename Scrolling**, and **6 localized languages with preference persistence**.

---

## 🌟 Key Features

### 🔄 1. Dual Transfer Modes
* **Mode 1: GoldHEN (FTP Upload)**
  * Direct FTP upload to the console's internal storage (`hdd:/data/pkg/`).
  * Custom FTP port configuration (e.g., port `2121`).
  * **Direct Streaming:** Stream Homebrew apps directly from online URLs to the console via FTP without downloading them to your phone first.
  * Live progress, real-time transfer speed (MB/s), and calculated **Remaining Time (ETA)**.

* **Mode 2: Package Sender (Remote Package Installer / RPI)**
  * Embedded high-performance HTTP server (**NanoHTTPD**) with Byte-Range streaming support.
  * Sends installation trigger payloads directly to the console's RPI service (default port `12800`).
  * Comprehensive error code explanations for PS4 error codes (`0x80990015`, `0x8099000C`, `0x8099008B`, etc.).
  * Optimized background HTTP streaming with no false completion popups.

---

### 🏷️ 2. Smart PKG Categorization (Base Game, Update, DLC)
* Automatically detects and labels `.pkg` files in the File Explorer:
  * 🎮 **Base Game** (Blue tag)
  * 🔄 **Update / Patch** (Orange tag)
  * 🎁 **DLC / Addon** (Green tag)
* Instant visual recognition of package types before uploading.

---

### 📜 3. Marquee Filename Scrolling & Speed / ETA Display
* **Horizontal Marquee Text:** Long filenames automatically scroll horizontally across the screen so you can easily read full file names without truncation.
* Displays exact transfer progress (`0%` - `100%`), live transfer speed (`MB/s`), and calculated **Remaining Time (ETA)** in `00m 00s` format.
* Real-time ETA and speed updates in both the app UI and Android status bar notifications.

---

### 📂 4. Built-in File Explorer & Archive Extractor
* Native internal file browser for phone storage, Downloads, and Documents.
* **Supported Archive Formats:** Extract `.zip`, `.rar`, `.7z`, `.tar`, `.gz`, `.tgz`, and `.tar.gz` archives directly on your phone.
* **Batch Extraction:** Extract multiple archives or multi-part archive files in a single pass.
* Automatic detection and selection of extracted `.pkg` files.
* In-app file management: Create folders, search, filter, and delete files.

---

### 🏪 5. Integrated Homebrew Store (PKG Zone)
* Browse hundreds of PS4 Homebrew apps directly inside the app powered by the PKG Zone API.
* Search and filter by category, developer name, and application title.
* **Option A:** Download PKGs directly to your phone storage.
* **Option B:** Direct-stream link to your console via GoldHEN FTP without saving locally.

---

### ⚙️ 6. Foreground Service & Panel Notifications
* **Android Foreground Service:** Uses **WakeLock** and **WifiLock** to keep multi-gigabyte transfers running reliably even when the screen is locked or the app is minimized.
* **Localized Panel Notifications:** Live status bar notifications showing mode (`GoldHEN FTP` / `Package Sender`), filename, transfer percentage, speed, and remaining time.

---

### 🌐 7. Multi-Language Support & Persistence
* 🇩🇪 **German (Deutsch)**
* 🇬🇧 **English**
* 🇪🇸 **Spanish (Español)**
* 🇵🇹 **Portuguese (Português)**
* 🇷🇺 **Russian (Русский)**
* 🇸🇦 **Arabic (العربية)**
* **Language Preference Persistence:** Saves your selected language and automatically restores it when restarting the app.
* **Live Log Translation:** Dynamically translates console log entries and error messages into your selected language when switching flags.

---

## 🛠️ System Requirements & Setup

### 📱 Android Smartphone
* **Android Version:** Android 7.0 (API Level 24) or higher.
* **Permissions:** Storage Access (for file browsing & archive extraction) and Notification permission.

### 🎮 Console (PS4 / PS5)
* Smartphone and console must be connected to the **same Wi-Fi network**.
* **For GoldHEN (FTP Mode):**
  * GoldHEN must be running on the console.
  * Enable the FTP Server in GoldHEN settings (default port `2121` or custom).
* **For Package Sender (RPI Mode):**
  * The **Remote Package Installer** app must be running on the PS4.
  * Default port is `12800`.

---

## 📖 Step-by-Step Usage Guide

### Mode 1: GoldHEN (FTP Upload)
1. Connect your phone and console to the same Wi-Fi network.
2. Select **GoldHEN** mode at the top of the app.
3. Enter your console's IP address and FTP port (e.g., `2121`).
4. Tap **File Explorer / Extractor** and select a `.pkg` file (or extract a ZIP/RAR/7Z archive).
5. Tap **Send**. The file will be uploaded directly to `hdd:/data/pkg/` on the console.
6. On your PS4/PS5, install the uploaded PKG using the GoldHEN Package Installer menu.

---

### Mode 2: Package Sender (HTTP Streaming / RPI)
1. Launch the **Remote Package Installer** app on your PS4.
2. Select **Package Sender** mode in the app.
3. Select a `.pkg` file and tap **Start Server**.
4. Enter your PS4's IP address (RPI port is typically `12800`).
5. Tap **Start Installation on PS4/PS5**.
6. The installation trigger will be sent, and live progress/ETA will be displayed in the app and status bar notification.

---

## 🚨 PS4/PS5 Error Codes & Solutions

| Error Code | Meaning | Solution |
| :--- | :--- | :--- |
| **`0x80990015`** | PKG / Task already exists | On PS4, go to **Notifications** -> **Downloads**, press `Options` on the old entry and delete it, then try again. |
| **`0x80990004`** | Invalid PKG format | The PKG file is corrupted or has an invalid key/content ID. Ensure it is a valid Fake PKG (fPKG). |
| **`0x8099000C`** | Storage Full | Not enough free space on PS4. Free up storage in **Settings** -> **Storage**. |
| **`0x80990088`** | Already in Task List | The download task is already active on the PS4. Check progress under **Notifications** -> **Downloads**. |
| **`0x8099008B`** | Network connection failed | The PS4 cannot reach the phone's IP address. Ensure both are on the same Wi-Fi and verify the phone's IP. |
| **`0x80990014`** | Stream aborted | Failed to read PKG header. Check Wi-Fi connection stability and ensure the file was not moved/deleted. |
| **`0x80990095`** | Firmware too old | PKG requires a newer system firmware. Use a backported PKG or update system software. |

---

## 🏗️ Tech Stack & Dependencies

* **Language:** Kotlin
* **UI Framework:** Jetpack Compose (Material Design 3)
* **HTTP Server:** [NanoHTTPD](https://github.com/NanoHttpd/nanohttpd) (2.3.1)
* **Networking:** [OkHttp](https://square.github.io/okhttp/) (4.12.0)
* **Image Loading:** [Coil Compose](https://coil-kt.github.io/coil/) (2.7.0)
* **Archive Extraction:**
  * [Apache Commons Compress](https://commons.apache.org/proper/commons-compress/) (1.28.0)
  * [Junrar](https://github.com/junrar/junrar) (8.1.1)
