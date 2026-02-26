# Colab Remote Uploader 🚀

A robust, Object-Oriented Google Colab notebook that securely mounts Google Drive, streams downloads directly into a designated Drive folder, and automatically generates public shareable links using the Google Drive API.

## ✨ Features
- **Interactive UI:** Utilizes Colab Forms for easy input of URLs, custom names, and feature toggles.
- **Smart Filename Extraction:** Automatically parses the original filename from server HTTP headers (`Content-Disposition`) or the URL string.
- **Drive API Integration:** Authenticates and communicates with the Google Drive API to adjust file permissions and generate direct `uc?export=download` links.
- **Robust Error Handling:** Includes connection timeouts, `try/except` blocks for network stability, and a retry mechanism to handle Google Drive's cloud synchronization delays.
- **Clean Logging & Progress:** Features a visual `tqdm` progress bar with percentage, speed, and size reports, while suppressing unnecessary backend warnings.
- **Auto-Directory Setup:** Automatically detects or creates the target destination folder inside your Drive.

> ⚠️ **Requires Legal/Security Review:** The `create_public_link` feature automatically modifies Google Drive file permissions to "Anyone with the link can view." If you are using this script in a corporate, enterprise, or sensitive environment, ensure you are not inadvertently exposing proprietary, sensitive, or PII data to the public internet.

## 📂 Files
- `remote_uploader.ipynb` — The main Colab notebook containing the two execution cells.

## 🛠️ Requirements
- A Google Account with Google Colab and Google Drive.
- Internet access to the target download URL.
- Python 3 environment (built into Colab) with standard libraries (`os`, `time`, `logging`, `urllib`).

## 🚀 Usage

1. Open `remote_uploader.ipynb` in Google Colab.
2. ### **Run Cell 1:** 
This will prompt you to mount Google Drive. Follow the popup to authorize access to your account.

3. **Configure Cell 2 (Using the right-hand panel):**
   - `url`: Paste the direct download link of the file.
   - `keep_original_name`: Check this box to let the script automatically extract the file's real name from the server.
   - `custom_file_name`: If you uncheck the box above, type your desired filename here (include the extension, e.g., `.zip` or `.exe`).
   - `create_public_link`: Check this box if you want the script to use the Drive API to generate a direct download URL after finishing.

4. ### **Run Cell 2:** 
The script will download the file directly to `My Drive/remote upload/`, verify the file size, and output your shareable link!

## 📝 Notes
- The default destination is `My Drive/remote upload/`. You can change the `base_folder` variable in the `SecureDownloader` class to target a different directory.
- Generating a public link requires a secondary, one-time API authentication popup during the first run of the session.

## 📜 License
under MIT. LICENSE