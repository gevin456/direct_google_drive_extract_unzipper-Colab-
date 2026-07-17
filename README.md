![Colab Heavy ZIP Toolkit Banner](https://placehold.co/800x200/222222/00ffaa/png?text=Colab+Heavy+ZIP+Toolkit&font=Montserrat)

# 🗜️ Colab Heavy ZIP Toolkit (Direct-to-Drive)

[![Python](https://img.shields.io/badge/Python-3.x-blue.svg?logo=python&logoColor=white)](https://www.python.org/)
[![Google Colab](https://img.shields.io/badge/Google-Colab-F9AB00.svg?logo=googlecolab&logoColor=white)](https://colab.research.google.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)

An interactive Google Colab utility designed to extract and split massive ZIP files directly within Google Drive. By completely bypassing local storage limits, this script prevents the dreaded **"No space left on device"** error when handling files larger than 100GB.

---

## ✨ Key Features

* **🔓 Zero Local Space Extraction:** Streams uncompressed data directly to your Google Drive using a 1MB memory buffer. 
* **⏩ Smart Resume (Skip Existing):** If your extraction gets interrupted, just run it again! The script checks existing file sizes and automatically skips fully extracted files.
* **💾 Forced Drive Sync:** Implements `flush()` and `fsync()` to guarantee your data is instantly and safely written to Google Drive, preventing data loss.
* **🔪 Built-in ZIP Splitter:** Easily chop gigantic ZIP files into custom-sized chunks (defaults to 50GB parts) for easier sharing or storage.
* **🎮 Clean Interactive UI:** A built-in terminal browser with auto-clearing screens allows you to navigate Google Drive, select files, and create folders seamlessly.

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
| **`1`, `2`, `3`...** | **Navigate** | Type the number of a directory or file to interact with it. |
| **`S`** | **✅ Select** | Confirm the current folder as your destination. |
| **`B`** | **⬅️ Back** | Move up one folder level. |
| **`N`** | **🆕 New Folder** | Create a new destination folder on the fly. |
| **`Q`** | **🛑 Quit** | Safely exit the script. |

---

## 📥 Example Workflow

1. **Mount:** The script hooks up to your Google Drive (if not already mounted).
2. **Find ZIP:** The UI prompts you to locate your ZIP file. You navigate to your folder and type the number for your 120GB `massive_dataset.zip`.
3. **Set Destination:** You navigate to your target folder and press `S` to select it.
4. **Choose Mode:** 
   * Press `1` to **Extract** (streams uncompressed files to the destination, skipping anything already extracted).
   * Press `2` to **Split** (cuts the ZIP into `part001`, `part002`, etc.).
5. **Relax:** Watch the beautiful green/blue progress bars track exact byte transfers without crashing your Colab instance! ☕

---

## 📝 Revision History

| Version | Updates |
| :---: | :--- |
| **v1.4** | Fixed double-input prompt bug and implemented clean UI terminal clearing via Colab's `output.clear()`. |
| **v1.3** | Added **'Skip Existing'** logic for pausing/resuming and force flush/sync to guarantee Drive writes. |
| **v1.2** | Implemented manual stream extraction (1MB buffer) to completely bypass local `/tmp` storage. |
| **v1.1** | Added byte-level `tqdm` progress bars and emoji-rich interactive UI. |

---

## ⚠️ Prerequisites & Dependencies

This script utilizes standard Python libraries pre-installed on Google Colab:
* `os`, `sys`, `time`, `shutil`
* `zipfile`
* `tqdm` (for beautiful progress tracking)
* `google.colab` (for Drive mounting and clean output clearing)

*Happy extracting! 🏁*
