![Colab Heavy ZIP Toolkit Banner](https://placehold.co/800x200/222222/00ffaa/png?text=Colab+Heavy+ZIP+Toolkit&font=Montserrat)

# 🗜️ Colab Heavy ZIP Toolkit (Direct-to-Drive)

[![Python](https://img.shields.io/badge/Python-3.x-blue.svg?logo=python&logoColor=white)](https://www.python.org/)
[![Google Colab](https://img.shields.io/badge/Google-Colab-F9AB00.svg?logo=googlecolab&logoColor=white)](https://colab.research.google.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)

Are you tired of getting the dreaded **"No space left on device"** error when trying to extract massive (100GB+) ZIP files in Google Colab? 

This interactive Python script solves that problem by **streaming data directly from Drive to Drive**, entirely bypassing Colab's limited local `/tmp` storage. It also includes a built-in file splitter to cut mammoth files into manageable chunks!

---

## ✨ Key Features

* **🔓 Direct-to-Drive Extraction:** Uses a 1MB memory buffer to stream uncompressed data directly back to your Google Drive. Zero local disk space required!
* **🔪 Built-in ZIP Splitter:** Easily chop gigantic ZIP files into custom-sized chunks (defaults to 50GB parts) for easier sharing or storage.
* **🎮 Interactive Terminal UI:** Browse your Google Drive, select files, and create new folders right from the Colab output cell.
* **📊 Byte-Level Progress:** Beautiful, color-coded `tqdm` progress bars that track exact byte transfers and uncompressed sizes.
* **☁️ Auto-Mounting:** Automatically detects and mounts your Google Drive if it isn't already connected.

---

## 🛠️ How to Use

**Step 1:** Open a [Google Colab](https://colab.research.google.com/) notebook.
**Step 2:** Copy and paste the script into a new code cell.
**Step 3:** Run the cell (`Shift + Enter`).
**Step 4:** Follow the interactive on-screen prompts!

### 🗺️ Navigation Controls

The script features a custom file browser. Use these keys in the input box:

| Command | Action | Description |
| :---: | :--- | :--- |
| **`1`, `2`, `3`...** | **Navigate** | Type the number of a directory to open it. |
| **`S`** | **✅ Select** | Confirm the current file (or folder) as your target. |
| **`B`** | **⬅️ Back** | Move up one folder level. |
| **`N`** | **🆕 New Folder** | Create a new destination folder on the fly. |
| **`Q`** | **🛑 Quit** | Safely exit the script. |

---

## 📥 Example Workflow

1. **Mount:** The script hooks up to your Google Drive.
2. **Find ZIP:** The UI prompts you to locate your ZIP file. You navigate to your folder and select your 120GB `massive_dataset.zip`.
3. **Set Destination:** You navigate to your target folder and press `S` to select it.
4. **Choose Mode:** 
   * Press `1` to **Extract** (streams the uncompressed files directly to the destination).
   * Press `2` to **Split** (cuts the ZIP into `part001`, `part002`, etc.).
5. **Relax:** Watch the green/blue progress bars do the heavy lifting without crashing your Colab instance! ☕

---

## 📝 Revision History

| Version | Updates |
| :---: | :--- |
| **v1.2** | Implemented manual stream extraction (1MB buffer) to bypass local storage. Completely prevents 'No space left on device' errors for ZIPs >100GB. |
| **v1.1** | Added byte-level `tqdm` progress bars and emoji-rich interactive UI. |

---

## ⚠️ Prerequisites & Dependencies

This script utilizes standard Python libraries pre-installed on Google Colab:
* `os`
* `zipfile`
* `shutil`
* `time`
* `tqdm` (for progress bars)
* `google.colab` (for Drive mounting)

*Happy extracting! 🏁*
