![Colab Heavy ZIP Toolkit Banner](https://placehold.co/800x200/222222/00ffaa/png?text=Colab+Heavy+ZIP+Toolkit&font=Montserrat)

# 🗜️ Colab Heavy ZIP Toolkit (Direct Streaming)

[![Python](https://img.shields.io/badge/Python-3.x-blue.svg?logo=python&logoColor=white)](https://www.python.org/)
[![Google Colab](https://img.shields.io/badge/Google-Colab-F9AB00.svg?logo=googlecolab&logoColor=white)](https://colab.research.google.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)

An interactive Google Colab utility engineered to extract and split massive ZIP files directly within Google Drive, utilizing a raw 2MB direct-to-Drive memory stream.

---

> ### ⚠️ **CRITICAL NOTE FOR MASSIVE FILES (>90GB)**
> Google Colab provides a free local disk resource of roughly 107GB. If your ZIP file is exceptionally large (above 90GB), the Colab instance may eventually run out of background space, causing the program to stop automatically. 
>
> **If this happens, do not panic!** 
> Simply run the script again and **choose the exact same extraction location as before**. The script features a built-in size/hash check. It will safely skip all existing files and continue extracting exactly where you left off. **No damaged files, no corruption.**

---

## ✨ Key Features

* **⏩ Smart Resume (Skip Logic):** Designed specifically to beat Colab's storage limits. If your extraction stops, re-running the script will instantly verify existing files and resume progress safely.
* **🔓 Direct Streaming:** Streams uncompressed data directly to your Google Drive using a 2MB memory buffer to minimize local disk footprint.
* **🖥️ Live Disk Monitoring:** Keep an eye on Colab's background storage in real-time right from your extraction progress bar.
* **🔪 Built-in ZIP Splitter:** Easily chop gigantic ZIP files into custom-sized chunks for easier sharing or storage.
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

1. **Mount:** The script hooks up to your Google Drive.
2. **Find ZIP:** The UI prompts you to locate your ZIP file. You navigate to your folder and type the number for your 120GB `massive_dataset.zip`.
3. **Set Destination:** You navigate to your target folder and press `S` to select it.
4. **Choose Mode:** 
   * Press `1` to **Extract**. 
   * Press `2` to **Split** (cuts the ZIP into manageable chunks).
5. **Relax:** Watch the green progress bars. If the script halts due to the 107GB limit, just restart the cell, pick the same folders, and let the **Smart Resume** finish the job! ☕

---

## 📝 Revision History

| Version | Updates |
| :---: | :--- |
| **v2.4** | Removed auto-restart/disk guard. Shifted core focus to raw extraction speed and manual resume capability. |
| **v2.3** | Replaced background cleaning loops with a clean runtime restart prompt. |
| **v1.7** | Added Live Disk Monitoring directly into the `tqdm` console output. |
| **v1.3** | Added **'Skip Logic'** for rock-solid pausing/resuming. |
| **v1.2** | Implemented manual stream extraction to minimize local `/tmp` storage. |

---

## ⚠️ Prerequisites & Dependencies

This script utilizes standard Python libraries pre-installed on Google Colab:
* `os`, `sys`, `time`, `shutil`
* `zipfile`
* `tqdm` (for beautiful progress tracking)
* `google.colab` (for Drive mounting and clean output clearing)
