# I had a really massive video to compress.

## Act 1

Install ffmpeg 

```bash
sudo xbps-install ffmpeg
```

## Act 2

Compression commands

```bash
ffmpeg -i input.mp4 -c:v libx264 -preset medium -crf 23 -c:a aac -b:a 128k output.mp4
```

A crf of 23 yields decent compression without compromising on the video quality.

But, you can go even further and crank up the crf to 100.

**you can go even faster**

```bash
ffmpeg -i input.mp4 -c:v libx264 -preset ultrafast -crf 28 -c:a aac -b:a 96k output.mp4
```

`ultrafast` speeds up the process, but the compression will be a bit ineffecient.

At the end of the day, it's all tradeoffs. Compression takes processing to make everything memory effecient, or you can optimize for runtime processing by trading away memory.

fin.

