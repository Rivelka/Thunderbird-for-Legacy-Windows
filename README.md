# Thunderbird for Legacy Windows (Windows Vista / 7 / 8 / 8.1)

Mozilla Thunderbird 115 was officially the final branch supporting Windows 7, 8, and 8.1 (released in July 2023, with security updates ending in December 2024). Unlike Firefox, Thunderbird did not receive extended legacy support from Mozilla.

This project backports modern versions of **Mozilla Thunderbird (116+, 117 Daily, and 128+ ESR Nebula UI)** to legacy Windows operating systems (including planned support for Windows Vista SP2), restoring modern security standards, updated WebExtensions, and mail rendering engines without requiring Windows 10/11.

![](https://github.com/Rivelka/Thunderbird-for-Legacy-Windows/blob/main/Thunderbird%20128.14.0%20-%20Windows%208%20-%20v2%20CENSORED.png)

---

## 📌 Compatibility Matrix

| OS Version | Architecture | Supported Branches | Status |
| :--- | :--- | :--- | :--- |
| **Windows 8.1** (NT 6.3) | x64 / x86 | 128.14.0 ESR, 117.0a1, 116.0b7 | ✅ Fully Supported |
| **Windows 8** (NT 6.2) | x64 / x86 | 128.14.0 ESR, 117.0a1, 116.0b7 | ✅ Fully Supported |
| **Windows 7 SP1** (NT 6.1) | x64 / x86 | 116.0b7, 117.0a1 (128 ESR in dev) | ✅ Supported (v116/117) |
| **Windows Vista SP2** (NT 6.0) | x64 / x86 | 116+, 128 ESR | ⏳ Planned (via Kernel wrappers) |

---

## ⚙️ Changes & Modifications

* **Subsystem Version Patching:** PE headers patched from Windows 10 (`0x000A`) down to NT 6.2 (`6.2`), NT 6.1 (`6.1`), and NT 6.0 (`6.0`).
* **Multi-Architecture Support:** Standalone packages available in both **32-bit (x86)** and **64-bit (x64)** architectures.
* **API-Set Shims:** Integrated missing `api-ms-win-shcore-scaling-l1-1-1.dll` Per-Monitor DPI awareness stubs for Windows 8 RTM and Windows 7.
* **Auto-Update Lock:** Update mechanisms disabled via distribution enterprise policies (`policies.json`) to prevent unintended bin overwrites.
* **Bilingual Support:** Dedicated packages provided in English (`en-US`) and Polish (`pl-PL`).

---

## 🛟 Releases

* **[Thunderbird 116.0b7 & 117.0a1](https://github.com/Rivelka/Thunderbird-for-Legacy-Windows/releases/tag/116.0b7-117.0a1)** — *August 29, 2026*  
  Added support for **Windows 7 SP1** (both 32-bit and 64-bit releases in PL and EN).
* **[Thunderbird 128.14.0 v1](https://github.com/Rivelka/Thunderbird-for-Legacy-Windows/releases/tag/128.14.0-1)** — *August 23, 2026*  
  Initial **128 ESR (Nebula UI)** backport for Windows 8 / 8.1 (64-bit).

---

## 🚀 Installation & Usage

1. Download the archive matching your OS and architecture from the [Releases](https://github.com/Rivelka/Thunderbird-for-Legacy-Windows/releases) section.
2. Extract the archive using 7-Zip or WinRAR to your chosen folder (e.g., `C:\Program Files\Thunderbird`).
3. Run `thunderbird.exe`.

---

## 🗺️ Roadmap

- [x] Initial release of Thunderbird 128 ESR for Windows 8 / 8.1 (64-bit).
- [x] Initial release of Thunderbird 116.0b7 & 117.0a1 for Windows 7 (32-bit and 64-bit).
- [x] Bilingual builds (Polish & English).
- [ ] Backport Thunderbird 128 ESR to Windows 7 SP1 (via `pathcch` & `combase` proxy layers).
- [ ] Experimental backport to **Windows Vista SP2 (NT 6.0)** using Extended Kernel / API shims.
- [ ] Native DWM/Aero titlebar and classic window frame cleanup (`userChrome.css`).

---

## 📜 Disclaimer
This is an independent open-source community modification and is not affiliated with or endorsed by the Mozilla Foundation.
