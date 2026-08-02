# 🚀 Disable Bing Web Search in Windows 10/11 Search Bar

[![Windows 10](https://img.shields.io/badge/Windows-10-blue?logo=windows&logoColor=white)](https://microsoft.com)
[![Windows 11](https://img.shields.io/badge/Windows-11-0078D4?logo=windows&logoColor=white)](https://microsoft.com)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

A lightweight registry fix (`.reg`) to completely disable Bing online web search results in the Windows Search Bar and Start Menu. Keep your Windows search **fast, private, and local-only**.

---

## 🛑 Problem

When searching for local apps, files, or settings in the Windows 10/11 search bar, Windows often defaults to searching Bing or opening Edge browser tabs. This leads to:
- Unnecessary delays when opening local applications.
- Accidental web searches instead of launching installed software.
- Unwanted data sending to external Bing telemetry servers.

---

## ✨ Solution

This registry tweak sets key policy parameters to ensure Windows Search **only looks for local files, programs, and settings** on your machine.

### What it modifies:
* `DisableSearchBoxSuggestions` = `1` *(Disables web suggestion popups)*
* `BingSearchEnabled` = `0` *(Disables Bing integration entirely in Search)*

---

## 🛠️ Installation

### Option 1: Quick Install (Download `.reg` File)
1. Download the [`disable_bing.reg`](./disable_bing.reg) file from this repository.
2. Double-click the file to run it.
3. Click **Yes** when prompted by User Account Control (UAC).
4. **Restart File Explorer** (via Task Manager) or restart your PC for changes to take effect.

### Option 2: Manual Registry File Creation
1. Open Notepad or any text editor.
2. Paste the following code:

```reg
Windows Registry Editor Version 5.00

[HKEY_CURRENT_USER\Software\Policies\Microsoft\Windows\Explorer]
"DisableSearchBoxSuggestions"=dword:00000001

[HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Search]
"BingSearchEnabled"=dword:00000000

```

3. Save the file as `disable_bing.reg` (ensure *All Files (`*.*`)* is selected in file type).
4. Run the file and restart Explorer / PC.

---

## 🔄 How to Revert (Enable Bing Search Again)

If you ever want to restore Bing web search back to default, download and run [`enable_bing.reg`](https://www.google.com/search?q=./enable_bing.reg) or run this registry code:

```reg
Windows Registry Editor Version 5.00

[HKEY_CURRENT_USER\Software\Policies\Microsoft\Windows\Explorer]
"DisableSearchBoxSuggestions"=dword:00000000

[HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Search]
"BingSearchEnabled"=dword:00000001

```

---

## 🛡️ Safety & Security

* **No third-party background software required.**
* Uses native Microsoft Windows Group Policy registry keys.
* Clean, transparent, and open-source.

---

## 📄 License

This project is licensed under the [MIT License](https://www.google.com/search?q=LICENSE). Free to use, modify, and distribute.

```
