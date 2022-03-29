# Download equirectuangular 360-degree videos from Youtube in highest quality

Recently, Youtube has developed their own [propriety encoding scheme](https://youtube-eng.googleblog.com/2017/03/improving-vr-videos.html) for 360-degree videos. Most videos from Youtube which have 2K and 4K resolution have already been converted into this format. 

As a result, if you download these videos, you will see the frame is cut and arranged into two rows
![Youtube propriety format](https://github.com/phananh1010/download-highres-youtubevid/blob/master/deerbox_0_01.png?raw=true)

The equirectangular is still useful in some niche cases e.g. showing snapshot to represent the video content. In oder to download the equirectangular format, youtube-dl is the best solution:

Install youtube-dl with Python:

`pip install --upgrade youtube-dl`

Update youtube-dl to the newest version:
`youtube-dl --update`

Execute this command to download highest resolution in equirectangular:

`youtube-dl -f bestvideo[ext=mp4] --no-check-certificate --user-agent '' URL`

The downloaded videos should be in equirectangular format now:
![Equirectangular](https://github.com/phananh1010/download-highres-youtubevid/blob/master/deer_0_01.jpg?raw=true)

<!--
That's being said, equirectangular is not the best format in many situations (notice the high distortion near the top and bottom of equirectangular format). 

More detail [here](https://github.com/ytdl-org/youtube-dl/issues/15267)
-->

# Convert stereoscopic 360-degree video to monoscopic
Sometime, a video is in stereoscopic format. The equirectangular frames show two similar parts on top of each other like this:
![Stereoscopic](https://github.com/phananh1010/download-highres-youtubevid/blob/master/moose_stereoscopic.jpg?raw=true)

In order to get the equirectangular, simply discard one part of the frame with ffmpeg: 
```
ffmpeg -i [InputVideo] -vf crop=h=in_h/2:y=0 -c:a copy [OutputVideo].
```
The result is an equirectangular frame.
![Monoscopic](https://github.com/phananh1010/download-highres-youtubevid/blob/master/moose_monoscopic.jpg?raw=true)
