Currently, Youtube has their own propriety encoding scheme for 360-degree video in 2K and 4K resolution. 
If you download these videos, you will see the frame is cut and arranged into two rows.

In oder to download the equirectangular format, youtube-dl is the best solution

Install youtube-dl with Python:

`sudo -H pip install --upgrade youtube-dl`

Execute this command to download highest resolution in equirectangular:

`youtube-dl -f bestvideo[ext=mp4] --user-agent '' URL`


More detail [here](https://github.com/ytdl-org/youtube-dl/issues/15267)
