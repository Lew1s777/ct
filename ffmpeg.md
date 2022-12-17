set video bit rate to 5500kbps
```
ffmpeg -i input.avi -b:v 5750k output.mp4
```

set video fps to 29.97
```
ffmpeg -i input.avi -r 59.97 output.mp4
ffmpeg -i 1.mp4 -vf fps=fps=59.97 11.mp4
```

set video file size to 1024KB
```
ffmpeg -i input.avi -fs 1024K output.mp4
```

set video format to H264
```
ffmpeg -i input.mp4 -vcodec h264 output.mp4
```
