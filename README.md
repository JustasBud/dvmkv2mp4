# dvmkv2mp4 - Convert any Dolby Vision/HDR10+ MKV to MP4 that runs on many devices

This fork works with newest Gpac / MP4Box 2.2.x. Similiarly all other depencies have been updated & tested.
- Removed PGS2SRT functionality
- After testing I can confirm that with LG OLED C9 the following audio codecs works with Plex:
  DTS and DTS-HD MA 5.1/7.1 passthrough. So these are left alone and copied as they are.
  DDP 7.1 passthrough. Some testing
  DTS:X and TrueHD are not being passthroughed, so they are being converted. Still deciding on what is the best form, so WIP
- Trying to work out a way to convert HDR10 to Dolby Vision, maybe with MadVR's HDRMeasure Windows app. Looking for something that works on Linux, though

## Build Docker image
Currently the image works only on x64 Linux. Also note that the final image size will be close to 6 GB which is normal as it includes the Tesseract OCR models.

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
