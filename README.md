# Enhanced Gpac / MP4Box 2.2.x Fork

## Overview
This repository hosts a fork of Gpac / MP4Box, specifically tuned for LG OLED C9 and, latest Gpac / Mp4box 2.2.x versions and ffmpeg 6.x.

## Updates and Modifications
- **Dependencies:** All dependencies have been updated to their latest versions and thoroughly tested for seamless integration.
- **Removed Feature:** The PGS2SRT functionality has been excluded from this fork.

## Compatibility Tests with LG OLED C9 and Plex
- **Codec Support:**
  - **DTS and DTS-HD MA:** Both 5.1 and 7.1 passthrough are supported. These codecs are copied directly without any modifications.
  - **DDP 7.1:** Passthrough is mostly functional, though additional testing is in progress.
- **Work-In-Progress:**
  - **DTS:X and TrueHD:** These are currently not supported for passthrough and are being converted. The optimal conversion method is still under consideration. For now using eac3 with ffmpeg
  - **HDR10 to Dolby Vision Conversion:** Exploring potential solutions for converting HDR10 to Dolby Vision. Current focus is on MadVR's HDRMeasure application for Windows, with ongoing research for a Linux-compatible alternative.

## Contribution
Contributions and suggestions are welcome, particularly in enhancing HDR conversion and audio codec support.

# dvmkv2mp4 - Convert any Dolby Vision/HDR10+ MKV to MP4 that runs on many devices

## Build Docker image
Currently the image works only on x64 Linux. This fork does not include Tesseract data.

To build your Docker image run the following command:
```
docker build -t dvmkv2mp4  https://github.com/tinof/dvmkv2mp4.git#main -f docker/Dockerfile
```
## Use the Docker image
The usage is similar to the normal variant but here you need to attach your folder where you would like to convert your files. You can also add the flags at the end of the command.

Example:
```
# docker run -it -u $(id -u):$(id -g) --rm -v <YOUR_FOLDER_PATH>:/convert dvmkv2mp4

docker run -it -u $(id -u):$(id -g) --rm -v /media/mkvvideos:/convert dvmkv2mp4 -l und,pol,eng -r -a
```
This example does the same which is mentioned in setion Usage.


PRs are welcome :)
