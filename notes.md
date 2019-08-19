## Some helpful notes

### Animal video list (4K, static camera, no human)
Snake, `https://www.youtube.com/watch?v=JRPafnjumPk`
Squirrel, `https://www.youtube.com/watch?v=DcEoXpEIe1c`

### Download highest resolution
```youtube-dl -f bestvideo[ext=mp4] --user-agent '' URL```

### Extract frame from video
```ffmpeg -ss 00:10:20 -t 1 -i <INPUT_FILE> -f mjpeg <OUTPUT_FILE>```

### Cut video with reencoding & change resolution
```ffmpeg -ss 1:09 -i kangaroo0.mp4 -t 0:23 -c:v libx264 -c:a aac -strict experimental -vf scale=3840x2048  kangaroo_109_131.mp4```
