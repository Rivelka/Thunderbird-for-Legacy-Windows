# Thunderbird for Legacy Windows (Windows Vista / 7 / 8 / 8.1)

Mozilla Thunderbird officially dropped support for Windows Vista after version 52.9.0 ESR, and for Windows 7 / 8 / 8.1 after version 115.18.0 ESR. Unlike Firefox, Thunderbird did not receive official extended ESR support for legacy platforms.

This project backports modern and intermediate milestone versions of **Mozilla Thunderbird (78 ESR, 88 Beta, 89 Nightly, 116 Beta, 117 Nightly, and 128+ ESR Nebula UI)** to legacy Windows operating systems (NT 6.0 through NT 6.3), restoring modern security standards, updated encryption protocols, and mail rendering engines without requiring Windows 10/11.

![](https://github.com/Rivelka/Thunderbird-for-Legacy-Windows/blob/main/Thunderbird%20128.14.0%20-%20Windows%208%20-%20v2%20CENSORED.png)

---

## 📌 Compatibility Matrix

| OS Version | Architecture | Supported Branches | Status |
| :--- | :--- | :--- | :--- |
| **Windows 8.1** (NT 6.3) | x64 / x86 | 128.14.0 ESR, 117.0a1, 116.0b7, 78.14.0 | ✅ Fully Supported |
| **Windows 8** (NT 6.2) | x64 / x86 | 128.14.0 ESR, 117.0a1, 116.0b7, 78.14.0 | ✅ Fully Supported |
| **Windows 7 SP1** (NT 6.1) | x64 / x86 | 117.0a1, 116.0b7, 78.14.0 (128 ESR in dev) | ✅ Supported (v78 / v116 / v117) |
| **Windows Vista SP2** (NT 6.0) | x64 / x86 | 78.14.0, 88.0b3 (x86), 88.0b3 x64 & 89.0a1 (dev) | ✅ Supported (v78 full, v88.0b3 x86) / ⏳ In Progress |

---

## ⚙️ Changes & Modifications

* **Subsystem Version Patching:** PE headers patched to allow execution on NT 6.0 (Vista), NT 6.1 (Win 7), and NT 6.2 (Win 8).
* **Multi-Architecture Builds:** Releases packaged for **32-bit (x86)** and **64-bit (x64)** systems.
* **API Wrappers & Shims:** Integrated `api-ms-win-shcore-scaling-l1-1-1.dll` DPI stubs for Windows 8/7, along with kernel API redirection for Windows Vista.
* **Auto-Update Lock:** Enterprise distribution policy (`distribution/policies.json`) bundled by default to prevent Mozilla servers from overwriting modified binaries.
* **Bilingual Releases:** All releases provided in both Polish (`pl-PL`) and English (`en-US`).

---

## 🛟 Releases

* **[Thunderbird 78.14.0, 88.0b3 & 89.0a1](https://github.com/Rivelka/Thunderbird-for-Legacy-Windows/releases/tag/78.14.0-88.0b3-89.0a1)** — *August 30, 2026*  
  Added **Thunderbird 88.0b3 (32-bit, Polish & English)** alongside full 78.14.0 builds (32-bit and 64-bit, PL & EN) for **Windows Vista SP2**. (64-bit packages for 88.0b3 and milestone 89.0a1 Proton builds are in active development).
* **[Thunderbird 116.0b7 & 117.0a1](https://github.com/Rivelka/Thunderbird-for-Legacy-Windows/releases/tag/116.0b7-117.0a1)** — *August 29, 2026*  
  Added support for **Windows 7 SP1** (both 32-bit and 64-bit releases in PL and EN).
* **[Thunderbird 128.14.0 v1](https://github.com/Rivelka/Thunderbird-for-Legacy-Windows/releases/tag/128.14.0-1)** — *August 23, 2026*  
  Initial **128 ESR (Nebula UI)** release for Windows 8 / 8.1 (64-bit).

---

## 🚀 Installation & Usage

1. Download the matching archive from the [Releases](https://github.com/Rivelka/Thunderbird-for-Legacy-Windows/releases) tab.
2. Extract the archive using 7-Zip or WinRAR to your application directory (e.g., `C:\Program Files\Thunderbird`).
3. Launch `thunderbird.exe`.

---

## 🗺️ Roadmap

- [x] Initial release of Thunderbird 128 ESR for Windows 8 / 8.1 (64-bit).
- [x] Release of Thunderbird 116.0b7 & 117.0a1 for Windows 7 (32-bit and 64-bit).
- [x] Full release of Thunderbird 78.14.0 for Windows Vista SP2 (32-bit & 64-bit, PL & EN).
- [x] Release of Thunderbird 88.0b3 for Windows Vista SP2 (32-bit, PL & EN).
- [ ] 64-bit (x64) packages for Thunderbird 88.0b3 on Windows Vista SP2.
- [ ] Backport Thunderbird 89.0a1 (Proton UI) to Windows Vista SP2 (32-bit & 64-bit).
- [ ] Backport Thunderbird 128 ESR to Windows 7 SP1 (via `pathcch` & `combase` proxy layers).
- [ ] Native DWM/Aero frame and classic UI cleanup (`userChrome.css`).

---

## 📜 Disclaimer
This is an independent open-source community modification and is not affiliated with or endorsed by the Mozilla Foundation.
