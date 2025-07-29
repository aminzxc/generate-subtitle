### `Python` needs to be installed
### install `openai-whisper`
```
pip install -U openai-whisper
```
### install `ffmpeg` ubuntu
```
apt install ffmpeg -y
```
### install `ffmpeg` window
```
open site https://www.gyan.dev/ffmpeg/builds/
download ffmpeg-7.0.2-essentials_build.zip
unzaip file
copy path : C:\Users\user\Downloads\ffmpeg-6.1.1-essentials_build\bin
past env on window : User variables --> path --> new --> past path 
```
### install test
```
ffmpeg -version
```
### change format ffmpeg
```
ffmpeg -i input.mkv output.mp4
embeded subtitle
ffmpeg -i output.mp4 -vf "subtitles=output.srt" -c:a copy final.mp4
```
### generate subtitle
```
nohup whisper output.mp4 --model large-v3 --language English --output_format srt > whisper.log 2>&1 &
```
### merge the video
```
Creating a text file and naming the videos
vim videos.txt
file '1.mp4'
file '2.mp4'
We use ffmpeg after
ffmpeg -f concat -safe 0 -i videos.txt -c copy output.mp4
```
### Using a GPU card instead of a CPU
```
pip uninstall torch -y
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118
```
### GPU usage test
```
import torch
print("CUDA Available:", torch.cuda.is_available())
print("Device Name   :", torch.cuda.get_device_name(0) if torch.cuda.is_available() else "No GPU detected")
print("Device Count  :", torch.cuda.device_count())

True
NVIDIA GeForce RTX 3050 Laptop GPU
```
