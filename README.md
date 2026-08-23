# Thunderbird for Legacy Windows (Windows 7 / 8 / 8.1)

Mozilla Thunderbird 115 was officially the final branch supporting Windows 7, 8, and 8.1 (released in July 2023, with final security updates ending in December 2024). Unlike Firefox, Thunderbird did not receive extended legacy support.

This project backports modern **Thunderbird 128+ ESR (Nebula UI)** to legacy Windows operating systems, providing modern email protocols, current security standards, and modern rendering engines without requiring Windows 10/11.

---

## 📌 Compatibility Matrix

| OS Version | Architecture | Status | Minimum Version |
| :--- | :--- | :--- | :--- |
| **Windows 8.1** (NT 6.3) | x64 / x86 | ✅ Fully Supported | 128.14.0 |
| **Windows 8** (NT 6.2) | x64 / x86 | ✅ Fully Supported | 128.14.0 |
| **Windows 7 SP1** (NT 6.1) | x64 / x86 | ⏳ In Progress (Wrappers) | Planned |

---

## ⚙️ Changes & Modifications

* **Subsystem Version Patching:** PE headers patched from Windows 10 (`0x000A`) down to NT 6.2 (`0x0006, 0x0002`).
* **API-Set Shims:** Added missing `api-ms-win-shcore-scaling-l1-1-1.dll` DPI awareness stubs for Windows 8 RTM.
* **Auto-Update Lock:** Internal update mechanism disabled via enterprise distribution policies to prevent overwriting patched binaries.
* **Language Support:** Native bilingual releases available in English (`en-US`) and Polish (`pl-PL`).

---

## 🚀 Installation & Usage

1. Download the latest release from the [Releases](https://github.com/Rivelka/Thunderbird-for-Legacy-Windows/releases) tab.
2. Extract the archive using 7-Zip or WinRAR to your preferred location (e.g., `C:\Program Files\Thunderbird`).
3. Run `thunderbird.exe`.

---

## 🗺️ Roadmap

- [x] Initial release for Windows 8 / 8.1 (64-bit).
- [ ] 32-bit (x86) builds for legacy machines and tablets.
- [ ] Custom `pathcch.dll` & `combase.dll` proxy layers for Windows 7 SP1 support.
- [ ] Restoration of native Aero/Classic window title bars (CSD cleanup).

---

## 📜 Disclaimer
This is an independent community project and is not affiliated with or endorsed by the Mozilla Foundation.

## 🛟 Releases

Thunderbird 128.14.0 (64-bit) (Windows 8) - August 23, 2026
