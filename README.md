# PyAudioClip
A python library for playing treaded audio clips in windows.

To use:
```
from PyAudioClip import AudioClip
from time import sleep

audio_clip = AudioClip('path_to_audio_file')
audio_clip.play()
sleep(10)
```
Note that this uses a daemon thread to play the audio clip. This means that the sound will end when the program reaches the end.

If you want to have a callback function when the audio clip has finished playing then you can pass the function when you create the AudioClip or add it later by setting the AudioClip.callback value.

```
from PyAudioClip import AudioClip

def callback_func():
  is_playing = False
  print("Audio Clip Finished")
  
is_playing = True
  
audio_clip = AudioClip('path_to_audio_file', callback_func)
audio_clip.play()

while is_playing:
  pass
```

### Commands include:
```
audio_clip.cue()  # this is used to load a file into memory before playing.
audio_clip.play()  # starts playing the audio clip
audio_clip.pause()  # pauses the audio clip
audio_clip.seek(20)  # set where in the clip the audio clip is playing
audio_clip.set_volume(500)  # sets the volume of the clip
audio_clip.stop()  # stops the audio clip, if it is then played it starts at the beginning of the audio clip
```
