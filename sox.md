
#### 调整速度
1. speed factor[c]

 > Adjust the audio speed (pitch and tempo together). factor is either the ratio of the new speed to the old speed: greater than 1 speeds up, less than 1 slows down, or, if appended with the letter ‘c’, the number of cents (i.e. 100ths of a semitone) by which the pitch (and tempo) should be adjusted: greater than 0 increases, less than 0 decreases.Technically, the speed effect only changes the sample rate information, leaving the samples themselves untouched. The rate effect is invoked automatically to resample to the output sample rate, using its default quality/speed. For higher quality or higher speed resampling, in addition to the speed effect, specify the rate effect with the desired quality option.See also the bend, pitch, and tempo effects.
 
> 调整音频速度（音调和节奏）。因子是新速度与旧速度的比率：大于1的速度，小于1的速度，或者，如果附加字母“C”，则应该调整音调（和节拍）的分值（即百分之一百）：大于0的增加，小于0的减少。
从技术上讲，速度效应只会改变样本率信息，使样本本身不受影响。速率效应被自动调用，以使用其默认质量/速度重采样到输出采样率。对于更高质量或更高速度的重采样，除了速度效应之外，还用期望的质量选项指定速率效应。



#### 噪音处理

- [How To Do Noise Reduction Using ffmpeg And sox](http://www.zoharbabin.com/how-to-do-noise-reduction-using-ffmpeg-and-sox/ )
1. Split the audio and video streams into 2 seperate files:
```
    The VIDEO stream: ffmpeg -i input.mp4 -sameq -an tmpvid.mp4
    The AUDIO stream: ffmpeg -i input.mp4 -sameq tmpaud.wav 
```
2. Generate a sample of noise from the audio of the file:
```
    ffmpeg -i input.mp4 -vn -ss 00:00:00 -t 00:00:01 noiseaud.wav
    -ss: the time offset from beginning. (h:m:s.ms).
    -t duration: record or transcode duration seconds of audio/video.

    Choose a segment of the audio where there’s no speech, only noise (e.g. speaker was silent for a sec).
```
3. Generate a noise profile in sox:
```
    sox noiseaud.wav -n noiseprof noise.prof
```
4. Clean the noise samples from the audio stream:
```
    sox tmpaud.wav tmpaud-clean.wav noisered noise.prof 0.21
    Change 0.21 to adjust the level of sensitivity in the sampling rates (I found 0.2-0.3 often provides best result).
```
5. Merge the audio and video streams back together:
```
    ffmpeg -i tmpaud-clean.wav -i tmpvid.mp4 -sameq vid.mp4
```
- [How to denoise with SOX?](https://stackoverflow.com/questions/44159621/how-to-denoise-with-sox )