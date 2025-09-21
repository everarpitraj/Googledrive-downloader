# Download with Progress for Google Colab

## Run on Colab
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1AItPbluMIWygsMoahZnXwuIiNkao55KB#scrollTo=aoXU2vhBShBc&line=1&uniqifier=1)

This code allows you to download files with progress tracking in Google Colab.

```python
# @title 📥 Download with Progress { display-mode: "form" }
from google.colab import drive
import os

# Mount Drive
drive.mount('/content/drive')

# Form inputs with dropdowns
url = "https://cdn.fsl-buckets.xyz/Maargan.2025.UNCUT.720p.DS4K.WEB-DL.Hindi.2.0-Tamil.5.1.ESub.x264-HDHub4u.Ms.mkv?token=f8ec562e5e29742dd2c34b70823743a5_1757951522_12" #@param {type:"string"}
download_path = "/content/drive/MyDrive" #@param {type:"string"}
filename = "Maargan.2025.UNCUT.720p.DS4K.WEB-DL.Hindi.2.0-Tamil.5.1.ESub.x264.mkv" #@param {type:"string"}
show_progress = True #@param {type:"boolean"}

# Construct full path
full_path = os.path.join(download_path, filename)

# Download command
if show_progress:
    !wget -c --progress=bar:force "$url" -O "$full_path"
else:
    !wget -c --quiet "$url" -O "$full_path"
```

## Usage

1. Run this code in a Google Colab notebook
2. Mount your Google Drive when prompted
3. Modify the parameters as needed:
   - `url`: The download URL
   - `download_path`: Where to save the file (default: Google Drive)
   - `filename`: What to name the downloaded file
   - `show_progress`: Whether to show download progress

## Features

- **Progress tracking**: Shows download progress with progress bar
- **Resume capability**: Uses `-c` flag to resume interrupted downloads
- **Google Drive integration**: Saves directly to your mounted Google Drive
- **Flexible parameters**: Easy to customize URL, path, and filename
