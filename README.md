![Colab Heavy ZIP Toolkit Banner](https://placehold.co/800x200/222222/00ffaa/png?text=Colab+Heavy+ZIP+Toolkit&font=Montserrat)

# 🗜️ Colab Heavy ZIP Toolkit (Direct-to-Drive)

[![Python](https://img.shields.io/badge/Python-3.x-blue.svg?logo=python&logoColor=white)](https://www.python.org/)
[![Google Colab](https://img.shields.io/badge/Google-Colab-F9AB00.svg?logo=googlecolab&logoColor=white)](https://colab.research.google.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)

An interactive Google Colab utility engineered to extract and split massive ZIP files directly within Google Drive. 

By utilizing a direct-to-Drive 2MB memory stream and a brand new **Emergency Deep Clean** system, this script guarantees you will never hit the dreaded **"No space left on device"** or **"Transport endpoint is not connected"** errors again—even when handling uncompressed files well over 100GB!

---

## ✨ Key Features

* **🧹 Emergency Deep Clean (NEW):** Actively monitors Colab's hidden local `/tmp` disk. If usage crosses 70%, the script automatically pauses and wipes apt caches, pip caches, and temporary files to free up space without breaking the Drive connection.
* **🛡️ Transport-Endpoint Safe (NEW):** Replaced harsh Drive unmounting with soft sync pauses (`time.sleep(20)`). This allows the Google Drive backend buffer to empty naturally, completely fixing the notorious "Transport endpoint is not connected" Colab crash.
* **🖥️ Live Disk Monitoring:** Keep an eye on Colab's background storage in real-time right from your extraction progress bar.
* **⏩ Smart Resume (Skip Existing):** If your connection drops or the notebook restarts, just run it again! It checks existing file sizes and automatically skips fully extracted files.
* **🎮 Bulletproof UI:** Features a cleanly clearing terminal browser, quick Google Drive navigation, and validated input loops so typos won't break your workflow.

---

## 🛠️ How to Use

**Step 1:** Open a [Google Colab](https://colab.research.google.com/) notebook.
**Step 2:** Copy and paste the script into a new code cell.
**Step 3:** Run the cell (`Shift + Enter`).
**Step 4:** Follow the interactive on-screen prompts!

### 🗺️ Navigation Controls

The built-in terminal file browser makes locating your files a breeze. Use these keys in the input box:

| Command | Action | Description |
| :---: | :--- | :--- |
| **`1`, `2`, `3`...** | **Navigate** | Type the number of a directory or file to interact with it. |
| **`S`** | **✅ Select** | Confirm the current folder or ZIP file as your target. |
| **`B`** | **⬅️ Back** | Move up one folder level. |
| **`N`** | **🆕 New Folder** | Create a new destination folder on the fly. |
| **`Q`** | **🛑 Quit** | Safely exit the script. |

---

## 📥 Example Workflow

1. **Mount:** The script hooks up to your Google Drive safely.
2. **Find ZIP:** The UI prompts you to locate your ZIP file. You navigate to your folder and type the number for your 150GB `massive_dataset.zip`.
3. **Set Destination:** You navigate to your target folder and press `S` to select it.
4. **Choose Mode:** 
   * Press `1` to **Extract**. 
   * Press `2` to **Split** (cuts the ZIP into manageable chunks).
5. **Relax:** Watch the beautiful green progress bars. If Colab's background disk gets full, the script will automatically pause, trigger a **Deep Clean**, allow the Drive buffer to sync, and keep going safely. ☕

---

## 📝 Revision History

| Version | Updates |
| :---: | :--- |
| **v1.9** | **Major Stability Update:** Added **Deep Clean** function to wipe local apt/pip/tmp caches when local space hits 70%. Upped chunk buffer to 2MB. |
| **v1.8** | **Bug Fix:** Resolved the "Transport endpoint is not connected" crash by replacing forced unmounts with soft sync pauses. |
| **v1.7** | Added **Live Disk Monitoring** directly into the `tqdm` console output. |
| **v1.6** | Implemented input validation loop for Mode selection to prevent accidental crashes. |
| **v1.5** | Added the initial Self-Healing System (Deprecated in v1.8 for safer soft-syncs). |
| **v1.4** | Fixed double-input prompt bug and implemented clean UI terminal clearing. |
| **v1.3** | Added **'Skip Existing'** logic for pausing/resuming. |

---

## ⚠️ Prerequisites & Dependencies

This script utilizes standard Python libraries pre-installed on Google Colab:
* `os`, `sys`, `time`, `shutil`
* `zipfile`
* `tqdm` (for beautiful progress tracking)
* `google.colab` (for Drive mounting and clean output clearing)
