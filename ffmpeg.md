> FFmpeg is the leading multimedia framework, able to **decode**, **encode**, **transcode**, **mux**, **demux**, **stream**, **filter** 
and **play** pretty much anything that humans and machines have created. It supports the most obscure ancient formats up to the cutting 
edge. No matter if they were designed by some standards committee, the community or a corporation. It is also highly portable: FFmpeg 
compiles, runs, and passes our testing infrastructure [FATE](http://fate.ffmpeg.org/) across Linux, Mac OS X, Microsoft Windows, the BSDs, 
Solaris, etc. under a wide variety of build environments, machine architectures, and configurations.

### change a video container
The following example changes the container from flash format .flv to .mp4

`ffmpeg -i input.flv -c:v copy -c:a copy -copyts output.mp4`

Sources:
[FFmpeg](http://ffmpeg.org/ffmpeg.html)
[CRF Guide](http://slhck.info/articles/crf)
[FFmpeg common usage](http://fatbellyman.com/webstuff/ffmpeg_common_usage/index.htm)
