# FFMPEG Commands

**Generates frames from Video**
```
ffmpeg -i <input video file path> <output frames file name>
```

- Example
```
ffmpeg -i video.mp4 frames/out-%05d.png
```
- *frames* is the folder
- *%05d* is number of 5 characters starting from 1 - file name would be 00001.


**Generates frames from Video with FPS**
```
ffmpeg -i <input video file path> -vf fps=<frames count> <output frames file name>
```

- Example
```
ffmpeg -i video.mp4 -vf fps=35 frames/out-%05d.png
```


**Create video from frames**
```
ffmpeg -i <input frame file name> -pix_fmt <pixel format> <output video file path>
```

- Example
```
ffmpeg -i out-%05d.png -pix_fmt yuv420p out.mp4
```


**Create video from frames with FPS**
```
ffmpeg -i <input frame file name> -vf fps=<frames count> -pix_fmt <pixel format> <output video file path>
```

- Example
```
ffmpeg -i out-%05d.png -vf fps=35 -pix_fmt yuv420p out.mp4
```