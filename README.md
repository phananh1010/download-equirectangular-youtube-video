Recently, Youtube has developed their own [propriety encoding scheme](https://youtube-eng.googleblog.com/2017/03/improving-vr-videos.html) for 360-degree videos. Most videos from Youtube which have 2K and 4K resolution have already been converted into this format. 
As a result, if you download these videos, you will see the frame is cut and arranged into two rows
![Youtube propriety format](https://github.com/phananh1010/download-highres-youtubevid/blob/master/deerbox_0_01.png?raw=true)

In oder to download the equirectangular format, youtube-dl is the best solution

Install youtube-dl with Python:

`sudo -H pip install --upgrade youtube-dl`

Execute this command to download highest resolution in equirectangular:

`youtube-dl -f bestvideo[ext=mp4] --user-agent '' URL`

The downloaded videos should be in equirectangular format now:
![Youtube propriety format](https://github.com/phananh1010/download-highres-youtubevid/blob/master/deer_0_01.jpg?raw=true)


More detail [here](https://github.com/ytdl-org/youtube-dl/issues/15267)
