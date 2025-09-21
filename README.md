'#@title 📥 Download with Progress { display-mode: "form" }

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
'
