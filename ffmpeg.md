> FFmpeg is the leading multimedia framework, able to **decode**, **encode**, **transcode**, **mux**, **demux**, **stream**, **filter** 
and **play** pretty much anything that humans and machines have created. It supports the most obscure ancient formats up to the cutting 
edge. No matter if they were designed by some standards committee, the community or a corporation. It is also highly portable: FFmpeg 
compiles, runs, and passes our testing infrastructure [FATE](http://fate.ffmpeg.org/) across Linux, Mac OS X, Microsoft Windows, the BSDs, 
Solaris, etc. under a wide variety of build environments, machine architectures, and configurations.

### change a video container
The following example changes the container from flash format .flv to .mp4

`ffmpeg -i input.flv -c:v copy -c:a copy -copyts output.mp4`

### Trim video

`ffmpeg -i input.wmv -ss 30 -c copy -to 40 output.wmv`

`-i` indicates the input file
`-ss` is the start timestamp in seconds. This option allows you to skip to a certain point.
`-t` is the encoding duration in seconds
`-to` is the timestamp to which you want to cut

Timestamp needs to be in HH:MM:SS.xxx format or in seconds

### MP3 Encoding

`ffmpeg -i input.wav -codec:a libmp3lame -qscale:a 2 output.mp3`

`qscale:a` (alias -q:a)

Values are encoder specific, so for libmp3lame the range is 0 - 9 where a lower value translates to a higher quality.

LAME Bitrate Overview

| Bitrate range (kbit/s) | ffmpeg option |
|=======================:|==============:|
| 320 CBR (Non VBR Example | -b:a 32k (this is 32KB/s, or its max) |


Native ffmpeg aac encoder

`ffmpeg -i input.wav -c:a aac -b:a 160k output.m4a`

### List all installed encoders

`ffmpeg -encoders`

### Common Errors

`Output file is empty, nothing was encoded (check -ss / -t / -frames parameters if used)`

This message is often seen when the `-ss` option value is greater than the duration of the input.
For example, if `-ss 30` is used for a 15 second input you may see this message. 

Make sure your `-ss`, `-t`, `-to`, and/or `-frames` value does not exceed the input duration.

Sources:  
[FFmpeg](http://ffmpeg.org/ffmpeg.html)   
[CRF Guide](http://slhck.info/articles/crf)   
[FFmpeg common usage](http://fatbellyman.com/webstuff/ffmpeg_common_usage/index.htm)  
[FFmpeg Errors](https://trac.ffmpeg.org/wiki/Errors)   
[FFmpeg Cheatsheet](http://www.rodrigopolo.com/ffmpeg/cheats.php)  
[Useful FFmpeg Commands](http://www.labnol.org/internet/useful-ffmpeg-commands/28490/)
