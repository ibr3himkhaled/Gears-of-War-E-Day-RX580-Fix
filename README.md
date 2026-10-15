<div align="center">

# Gears of War: E-Day
## AMD Radeon RX 580 Compatibility Fix

**A community-developed DirectX 12 compatibility project for AMD Polaris GPUs.**

![GPU](https://img.shields.io/badge/GPU-AMD_RX_580-ED1C24?style=for-the-badge&logo=amd&logoColor=white)
![API](https://img.shields.io/badge/API-DirectX_12_%2F_Vulkan-0078D6?style=for-the-badge)
![Platform](https://img.shields.io/badge/Platform-Windows-0078D4?style=for-the-badge&logo=windows&logoColor=white)
![Distribution](https://img.shields.io/badge/Distribution-Windows_Installer-6F42C1?style=for-the-badge)
![Target](https://img.shields.io/badge/Target-AMD_Polaris-ED1C24?style=for-the-badge)

**Developed and tested primarily on the AMD Radeon RX 580 8GB.**

[Download Latest Release](../../releases/latest) · [Report an Issue](../../issues)

---

## ❤️ Support My Work

Hi, I'm **Ibrahim Khaled**, an independent developer working on compatibility fixes that help older AMD graphics cards run modern games.

Developing these projects involves graphics API investigation, shader analysis, debugging, compatibility research, and repeated testing.

If this project has been useful to you, please consider supporting the development of future fixes.

### ☕ Support Development

[![GitHub Sponsors](https://img.shields.io/badge/GitHub-Sponsor-EA4AAA?style=for-the-badge&logo=githubsponsors&logoColor=white)](https://github.com/sponsors/ibr3himkhaled)

[![Ko-fi](https://img.shields.io/badge/Ko--fi-Support_Me-FF5E5B?style=for-the-badge&logo=kofi&logoColor=white)](https://ko-fi.com/ibr3himkhaled)

[![Buy Me a Coffee](https://img.shields.io/badge/Buy_Me_a_Coffee-Support-FFDD00?style=for-the-badge&logo=buymeacoffee&logoColor=black)](https://buymeacoffee.com/ibr3himkhap)

[![PayPal](https://img.shields.io/badge/PayPal-Donate-00457C?style=for-the-badge&logo=paypal&logoColor=white)](https://paypal.me/IbrahimKhaled011)

**All donations are optional. The compatibility fix is intended to remain free.**

Your support helps fund continued research, development, debugging, and compatibility testing for older GPUs.

**Thank you for supporting independent development!**

</div>

---

## Overview

This project provides a custom compatibility solution for **Gears of War: E-Day**, targeting the **AMD Radeon RX 580 8GB** and other GPUs based on AMD's Polaris architecture.

The project combines a dedicated launcher with custom compatibility components and shader-related adjustments intended to address graphics compatibility issues on the target hardware.

The fix is distributed through a **Windows installer**. Once installation is complete, the game should be started through the included launcher, **`EDayPlay.exe`**, so the intended compatibility startup path is used.

> [!IMPORTANT]
> **After installing the fix, launch the game using `EDayPlay.exe`. Do not launch `GoWEDay-Steam.exe` directly when using this compatibility setup.**

The RX 580 8GB is the primary development and testing target. Compatibility and performance on other GPUs, drivers, and game builds may vary.

---

## Features

- Compatibility work targeting AMD Polaris GPUs.
- Custom DirectX 12 and DXGI compatibility components.
- Vulkan-based translation components used by the compatibility path.
- Targeted shader substitutions for compatibility.
- A dedicated `EDayPlay.exe` launcher for starting the game through the fix.
- A Windows installer to simplify installation of the required files.
- Separate development and validation of compatibility changes to help preserve the known-working setup.

> Performance depends on the GPU, driver, game build, graphics workload, and translation-layer behavior. This project does not guarantee a particular FPS or frame-time improvement.

---

## Installation

### Step 1 — Download the Installer

Download the latest installer from the project's GitHub Releases page:

**[Download the Latest Release](../../releases/latest)**

Use the installer provided for one release. Do not mix files from different releases or from unrelated compatibility projects.

### Step 2 — Install the Fix

1. Make sure the game is installed and close it if it is running.
2. Run the downloaded setup file.
3. Follow the installer's instructions and select the correct game location if prompted.
4. Allow the installer to place the required compatibility components and launcher.

Keep a backup of important files before installing any compatibility modification.

### Step 3 — Start the Game with the Correct Launcher

After installation, locate and run:

```text
EDayPlay.exe
```

The launcher is placed with the game's required compatibility files, typically under the game's `FairlightConcept\Binaries\Win64` directory.

**Use `EDayPlay.exe` for normal gameplay with this fix. Do not start `GoWEDay-Steam.exe` directly.**

The dedicated launcher is the intended entry point for this compatibility setup.

### Step 4 — First Launch

The first launch may take longer than later launches while graphics components initialize or shader/pipeline work is performed. Give the game time to start before assuming that it has failed.

---

## Recommended: Install the Game on an SSD

**Installing Gears of War: E-Day on an SSD is strongly recommended.**

The game may experience longer loading times, texture streaming delays, and occasional stuttering when installed on a traditional hard disk drive (HDD).

An SSD can help reduce loading times and improve asset streaming responsiveness, potentially reducing some stuttering associated with loading game assets during gameplay.

### SSD vs. HDD

| Storage Type | Expected Experience |
|:---|:---|
| SSD | Recommended for faster loading and more responsive asset streaming |
| HDD | Longer loading times, possible texture pop-in, and occasional streaming-related stuttering |

### Important Notes

- An SSD is recommended for the best possible gameplay experience.
- Installing the game on an HDD may result in delayed texture loading or temporary stuttering while assets are streamed.
- Storage-related stuttering is separate from graphics compatibility issues and may persist even when the fix is working correctly.
- An SSD cannot eliminate every source of stuttering or guarantee a specific performance improvement.

**Recommendation:** Install the game on an SSD whenever possible, especially if you experience slow texture loading or repeated stuttering while exploring the game world.

---

## Recommended: Lossless Scaling

For users who want to experiment with smoother perceived motion, **Lossless Scaling** is recommended as an optional companion application.

[![Lossless Scaling on Steam](https://img.shields.io/badge/Steam-Lossless_Scaling-1B2838?style=for-the-badge&logo=steam&logoColor=white)](https://store.steampowered.com/app/993090/Lossless_Scaling/)

Lossless Scaling includes image-scaling and frame-generation features that may improve perceived smoothness when configured appropriately.

### Notes for RX 580 Users

- Lossless Scaling is a separate application; it is **not included** with this compatibility fix.
- Frame generation requires additional GPU resources and may reduce the game's base FPS when the GPU is already heavily loaded.
- Results depend on the base frame rate, game settings, display mode, and Lossless Scaling configuration.
- A reasonably stable base frame rate generally provides a better starting point for frame generation.
- Use a supported windowed or borderless display mode and follow the application's own instructions.

**Lossless Scaling is optional.** It does not replace the compatibility fix and cannot guarantee smoother results on every system. Frame generation can improve perceived motion, but it does not make the game render more real frames per second on its own.

---

## How the Fix Works

The project investigates and adjusts parts of the game's graphics compatibility path for AMD Polaris hardware. Components used by a release may include:

- A custom Direct3D 12 proxy.
- DXGI compatibility handling.
- Vulkan-based D3D12 translation components.
- Targeted shader substitution components.
- Configuration files used by the compatibility layer.
- The `EDayPlay.exe` launcher.

These components are designed to work together. Removing files, replacing individual DLLs, or combining files from different releases can prevent the game from starting or cause rendering problems.

The precise implementation may change between releases as compatibility research continues.

---

## Performance and Stuttering

Performance is affected by multiple factors, including GPU workload, graphics-driver behavior, shader and pipeline compilation, API translation overhead, and the game's own rendering workload.

The project includes ongoing code-level investigation aimed at reducing unnecessary overhead introduced by the compatibility fix.

**A particular FPS increase or complete elimination of stuttering is not guaranteed.**

For useful bug reports, describe when the stutter occurs, whether it repeats in the same area, and whether the issue began after changing the game, driver, or fix version. Include logs when available.

---

## GPU Compatibility

| GPU | Compatibility status |
|:---|:---|
| AMD Radeon RX 580 8GB (Polaris) | Primary development and testing target |
| Other AMD Radeon RX 400 / RX 500 GPUs | Not individually verified unless stated in a release note |
| Other AMD GPUs | Not verified |
| NVIDIA GPUs | Not verified |
| Intel GPUs | Not verified |

> [!NOTE]
> The **RX 580 8GB** is the primary target. Do not assume that another Polaris GPU will behave identically; memory capacity, GPU model, driver version, and system configuration may affect compatibility.

---

## Tested Hardware and Software

The primary reference configuration is:

| Component | Specification |
|:---|:---|
| GPU | AMD Radeon RX 580 8GB (2048SP) |
| GPU architecture | AMD Polaris / GCN 4 |
| CPU | Intel Core i5-12400F |
| RAM | 16GB |
| Operating system | Windows 11 Pro 23H2 |
| Graphics driver | AMD Adrenalin 26.5.2 |
| Graphics path | DirectX 12 compatibility components / Vulkan-based translation |

Results may differ on other configurations. Check the release notes for version-specific information.

---

## Troubleshooting

### The Game Does Not Start

- Confirm that installation completed successfully.
- Launch the game through **`EDayPlay.exe`**, not `GoWEDay-Steam.exe`.
- Verify that all required files from the same release are present.
- Check whether security software quarantined any required file.
- If the issue continues, collect the relevant logs before changing or deleting files.

### Missing Textures or Other Rendering Problems

- Confirm that you are using files from a single release.
- Do not replace individual compatibility DLLs with versions from other projects.
- Record the game build, fix version, GPU driver version, and where the issue occurs.
- Attach relevant logs or screenshots when opening an issue.

### Stuttering or Frame Drops

Stuttering can have different causes, including shader or pipeline compilation, driver behavior, and graphics workload. It does not automatically mean that the compatibility fix has failed.

Report when the stutter occurs and whether it is repeatable. Avoid changing several configuration options at once, since doing so makes the cause harder to isolate.

### The Launcher Is Missing

Verify that the installer completed successfully and check whether security software removed the launcher. If needed, use the same release's installer to repair the installation rather than downloading individual files from an untrusted source.

---

## Reporting Issues

Before opening an issue, include as many of the following details as possible:

- GPU model and VRAM capacity.
- CPU and system RAM.
- Windows version.
- AMD driver version.
- Game version or build.
- Compatibility-fix release version.
- Whether the problem occurs at startup or during gameplay.
- Steps to reproduce the issue.
- Relevant logs, screenshots, or a short description of the observed behavior.

[**Open a GitHub Issue**](../../issues)

Please distinguish launch failures, crashes, rendering defects, and performance issues so each problem can be investigated appropriately.

---

## Disclaimer

This is an independent, community-developed compatibility project. It is not affiliated with or endorsed by the game's developer or publisher, AMD, Microsoft, or the developers of any third-party components used by the project.

All trademarks and game assets belong to their respective owners. This project does not guarantee compatibility or a specific performance level across every hardware configuration, driver version, or game update.

Use the installer at your own discretion. Keep backups of important files before installing modifications, and only download releases from the project's official repository.

---

## Credits

**Project Author:** [ibr3himkhaled](https://github.com/ibr3himkhaled)

Developed through independent compatibility research, graphics debugging, shader investigation, and testing focused on AMD Polaris hardware.

---

<div align="center">

**The fix is free to use. Support is always optional.**

</div>
