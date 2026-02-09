# Colab Remote Uploader

A simple Google Colab notebook that mounts Google Drive and downloads a file into a Drive folder with progress reporting.

## Features
- One‑click Google Drive mount
- Configurable download URL and output filename
- Auto‑creates a destination folder in Drive
- Progress bar and final size report

## Files
- `remote uploader .ipynb` — Colab notebook with two cells: mount Drive and download to Drive

## Requirements
- Google Colab (Python 3)
- Internet access to the download URL

## Usage
1. Open `remote uploader .ipynb` in Google Colab.
2. Run **Cell 1** to mount Google Drive and authorize access.
3. In **Cell 2**, set:
   - `url` to the file you want to download
   - `file_name` to the name you want saved
   - `folder_name` to the destination folder inside `My Drive`
4. Run **Cell 2** to download the file to Drive.

## Notes
- The notebook writes to `My Drive/<folder_name>` in Google Drive.
- If Drive isn’t mounted, Cell 2 will print an error.

## License
MIT. See `LICENSE`.
