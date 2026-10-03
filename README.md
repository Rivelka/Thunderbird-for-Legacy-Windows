# Thunderbird for Legacy Windows (Windows Vista / 7 / 8 / 8.1)

Mozilla Thunderbird officially dropped support for Windows Vista after version 52.9.0 ESR, and for Windows 7 / 8 / 8.1 after version 115.18.0 ESR. Unlike Firefox, Thunderbird did not receive official extended ESR support for legacy platforms.

This project backports modern and intermediate milestone versions of **Mozilla Thunderbird (78 ESR, 88 Beta, 89 Nightly Proton UI, 90 Beta, 91 Nightly, 116 Beta, 117 Nightly, 128+ ESR, 132 Release, and 133+ Daily Nebula UI)** to legacy Windows operating systems (NT 6.0 through NT 6.3) without requiring an Extended Kernel.

![Thunderbird 128.14.0 on Windows 7](Thunderbird%20128.14.0%20-%20Windows%207%20-%20v2%20-%20CENSORED.png)

---

## 📌 Compatibility Matrix

| OS Version | Architecture | Supported / Tested Branches | Status |
| :--- | :--- | :--- | :--- |
| **Windows 8.1** (NT 6.3) | x64 / x86 | 133.0a1, 132.0.1, 128.14.0 ESR, 117.0a1, 116.0b7, 91.0a1, 90.0b3, 89.0a1, 88.0b3, 78.14.0 | ✅ Fully Supported |
| **Windows 8** (NT 6.2) | x64 / x86 | 133.0a1, 132.0.1, 128.14.0 ESR, 117.0a1, 116.0b7, 91.0a1, 90.0b3, 89.0a1, 88.0b3, 78.14.0 | ✅ Fully Supported |
| **Windows 7 SP1** (NT 6.1) | x64 / x86 | **128.14.0 ESR (x64 / x86)**, 117.0a1, 116.0b7, 78.14.0<br>*(132 & 133 in active development)* | ✅ Supported (v78 / v116 / v117 / **v128 ESR**) |
| **Windows Vista SP2** (NT 6.0) | x64 / x86 | **78.14.0**, **88.0b3**, **89.0a1 (2021-03-29)**<br>*(90.0b3, 91.0a1 & 89.0a1 2021-04-07: executable with font glitch)* | ✅ Supported (Working Fonts)<br>⚠️ Experimental (Broken Font) |

---

## ⚙️ Changes & Modifications

* **Subsystem Version Patching:** PE headers patched from modern Windows versions down to NT 6.0 (Vista), NT 6.1 (Win 7), and NT 6.2 (Win 8).
* **Multi-Architecture Standalone Builds:** Packages provided in both **32-bit (x86)** and **64-bit (x64)** architectures.
* **Source-Level Backports & Engine Patches:** Custom-compiled trees (`comm-esr128`) removing hardcoded modern Windows dependencies and adapting Gecko runtime directly for Windows 7.
* **API Redirection & Shims (No Extended Kernel):**
  * Redirected thread affinity calls (`GetThreadGroupAffinity` / `SetThreadGroupAffinity`).
  * Stubbed missing Windows Error Reporting calls (`WerRegisterRuntimeExceptionModule`, `WerUnregisterRuntimeExceptionModule` $\to$ `WerRegisterFile` / `WerUnregisterFile`).
  * Redirected missing kernel, shell, user, and DWM calls (`TryAcquireSRWLockExclusive`, `K32*` functions, `SetGestureConfig`, `DwmInvalidateIconicBitmaps`, etc.).
* **Proton & Nebula UI Implementations:** Modern interface backports (up to Thunderbird Daily 133 Nebula UI) running smoothly on legacy Windows desktop compositors.
* **Auto-Update Lock:** Enterprise distribution policies (`distribution/policies.json`) bundled by default to prevent binaries from being overwritten by Mozilla update servers.
* **Language Availability:** Packages available in Polish (`pl-PL`) and English (`en-US`) depending on branch release.

---

## 🛟 Releases

* **[Thunderbird 128.14.0 (Windows 7 SP1 - 64-bit)](https://github.com/Rivelka/Thunderbird-for-Legacy-Windows/releases/tag/128.14.0-v3)** — *October 2, 2026*   (Minor update on October 3, 2026 - 64-bit only - Disabled updates)
  Added native standalone **64-bit (x64)** release of **Thunderbird 128.14.0 ESR (Nebula UI)** for **Windows 7 SP1** built from source:
  * Compiled directly from modified `comm-esr128` sources with no Extended Kernel required.
  * Full 64-bit memory addressing, native Aero Glass frame integration, and complete IMAP/POP3/HTML mail rendering.
  * Available in **Polish (`pl-PL`)** and **English (`en-US`)**.
* **[Thunderbird 128.14.0 (Windows 7 SP1 - 32-bit)](https://github.com/Rivelka/Thunderbird-for-Legacy-Windows/releases/tag/128.14.0-v2)** — *October 1, 2026*  
  Added standalone **32-bit (x86)** release of **Thunderbird 128.14.0 ESR (Nebula UI)** natively backported to **Windows 7 SP1** via source code modifications:
  * Built directly from modified `comm-esr128` sources without requiring an Extended Kernel.
  * Native Aero Glass frame and full IMAP/POP3/HTML mail rendering support.
  * Available in **Polish (`pl-PL`)** and **English (`en-US`)**.
* **[Thunderbird Daily 133.0a1 (Windows 8 / 8.1)](https://github.com/Rivelka/Thunderbird-for-Legacy-Windows/releases/tag/132.0.1-1)** — *September 28, 2026*  
  Added standalone release of **Thunderbird Daily 133.0a1 (2024-10-02 Build)** featuring **Nebula UI** for **Windows 8** and **Windows 8.1**:
  * Full support for both **32-bit (x86)** and **64-bit (x64)** architectures.
  * Available in **English (`en-US`)**.
* **[Thunderbird 132.0.1 (Windows 8 / 8.1)](https://github.com/Rivelka/Thunderbird-for-Legacy-Windows/releases/tag/132.0.1-1)** — *September 28, 2026*  
  Added official standalone release of **Thunderbird 132.0.1 (Nebula UI)** for **Windows 8** and **Windows 8.1**:
  * Full support for both **32-bit (x86)** and **64-bit (x64)** architectures.
  * Available in **Polish (`pl-PL`)** and **English (`en-US`)**.
* **[Thunderbird 128.14.0 v1 (32-bit)](https://github.com/Rivelka/Thunderbird-for-Legacy-Windows/releases/tag/128.14.0-v1)** — *September 25, 2026*  
  Added official **32-bit (x86)** standalone release of **Thunderbird 128.14.0 ESR (Nebula UI)** for **Windows 8** and **Windows 8.1** (PL & EN).
* **[Thunderbird 78.14.0, 88.0b3, 89.0a1, 90.0b3 & 91.0a1 (Windows Vista)](https://github.com/Rivelka/Thunderbird-for-Legacy-Windows/releases/tag/78.14.0-88.0b3-89.0a1)** — *Updated August 31, 2026*  
  * **Thunderbird 88.0b3:** Fully working text and UI font rendering (32-bit & 64-bit, PL & EN).
  * **Thunderbird 89.0a1 (2021-03-29 Build):** Fully working text and Proton UI font rendering (32-bit & 64-bit, EN).
  * **Thunderbird 78.14.0 ESR:** Stable release (32-bit & 64-bit, PL & EN).
  * **Experimental Builds (Font Rendering Glitch / Broken Font):**
    * *Thunderbird 89.0a1 (2021-04-07 Build)* — 32-bit (EN).
    * *Thunderbird 90.0b3* — 64-bit (PL & EN).
    * *Thunderbird 91.0a1 (2021-06-14 Build)* — 64-bit (EN).
* **[Thunderbird 116.0b7 & 117.0a1](https://github.com/Rivelka/Thunderbird-for-Legacy-Windows/releases/tag/116.0b7-117.0a1)** — *August 29, 2026*  
  Added support for **Windows 7 SP1** (both 32-bit and 64-bit releases in PL and EN).
* **[Thunderbird 128.14.0 v1 (64-bit)](https://github.com/Rivelka/Thunderbird-for-Legacy-Windows/releases/tag/128.14.0-1)** — *August 23, 2026*  
  Initial **128 ESR (Nebula UI)** release for Windows 8 / 8.1 (64-bit).

---

## 🚀 Installation & Usage

1. Download the archive matching your OS, architecture, and language from the [Releases](https://github.com/Rivelka/Thunderbird-for-Legacy-Windows/releases) tab.
2. Extract the archive using 7-Zip or WinRAR to your application directory (e.g., `C:\Program Files\Thunderbird`).
3. Run `thunderbird.exe`.

---

## 🗺️ Roadmap

- [x] Initial release of Thunderbird 128 ESR for Windows 8 / 8.1 (64-bit).
- [x] Release of Thunderbird 128 ESR for Windows 8 / 8.1 (32-bit).
- [x] Backport Thunderbird 128.14.0 ESR (32-bit) to Windows 7 SP1 via source-level modifications (`comm-esr128`, PL & EN).
- [x] Backport Thunderbird 128.14.0 ESR (64-bit) to Windows 7 SP1 via source-level modifications (`comm-esr128`, PL & EN).
- [x] Release of Thunderbird 132.0.1 for Windows 8 / 8.1 (32-bit and 64-bit, PL & EN).
- [x] Release of Thunderbird Daily 133.0a1 (2024-10-02) for Windows 8 / 8.1 (32-bit and 64-bit, EN).
- [x] Release of Thunderbird 116.0b7 & 117.0a1 for Windows 7 (32-bit and 64-bit).
- [x] Full release of Thunderbird 78.14.0 for Windows Vista SP2 (32-bit & 64-bit, PL & EN).
- [x] Full release of Thunderbird 88.0b3 for Windows Vista SP2 (32-bit & 64-bit, PL & EN).
- [x] Functional Proton UI release: Thunderbird 89.0a1 (2021-03-29) for Windows Vista SP2 (32-bit & 64-bit).
- [x] Bootstrapped execution of Thunderbird 90.0b3 and 91.0a1 on Windows Vista SP2.
- [ ] Backport Thunderbird 132 & 133 (32-bit / 64-bit) to Windows 7 SP1.
- [ ] Fix DirectWrite / Direct2D font rendering engine for post-April 2021 builds (89.0a1 2021-04-07+, 90.0b3, 91.0a1) on Windows Vista.
- [ ] Test and evaluate Thunderbird 128 ESR / 132 / 133 viability on Windows Vista SP2 and Windows XP/2003.
- [ ] Native DWM/Aero frame and classic UI cleanup (`userChrome.css`).

---

## 📜 Disclaimer
This is an independent open-source community modification and is not affiliated with or endorsed by the Mozilla Foundation.
