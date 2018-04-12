# 📹 foggycam

![Foggycam logo](foggycam-logo.png)

(_Icon derivative from the [work of Steven Kuiper](https://www.iconfinder.com/icons/408402/camera_icon#size=256)_)

📹  A tool to capture Nest video streams locally, without having to pay for Nest Aware. The current release is tested on macOS. Windows and Linux adaptations coming soon (minor tweaks required).

>**NOTE:** Worth noting that we don't yet support audio recording, due to the fact that only the visual stream is captured.

## How To Configure

Make sure you rename `_config.json` to `config.json` and specify the following parameters:

|Parameter|Description|
|-----|-----|
|`username`|Nest account username.|
|`password`|Nest account password.|
|`path`|Absolute path to local folder where content needs to be stored.<br/><br/>Default is the script path.|
|`frame_rate`|Frame rate for the generated video.<br/><br/>Default is 24.|
|`threshold`|Number of images that need to be combined in a video in a single buffer.<br/><br/>Default is 200.|
|`width`|Image width for the capture image.<br/><br/>Default is 1280.|
|`clear_images`|Determines whether images are removed after video is produced.<br/><br/>Default is false.|
|`produce_video`|Determines whether a video is generated after a threshold of captured images is hit.<br/><br/>Default is false.|
|`upload_to_azure`|Determines whether the final video will be uploaded to Azure Storage.<br/><br/>Default is false.|
|`az_account_name`|Name of the Azure Storage account.|
|`az_sas_token`|SAS token for the Azure Storage account. Should have `write`, `list` and `read` permissions.|

**If you want to capture video**, you will need to [download `ffmpeg`](https://www.ffmpeg.org/download.html) and place it in the `tools` folder, in the script root directory.

Alternatively, if you are on Linux, install `ffmpeg`:

```
sudo apt-get install ffmpeg
```

On a Mac, run:

```
brew install ffmpeg
```

## How To Start

Make sure you install the requirements for the project, by `cd`-ing in the folder with the project, and running:

```
pip install -r requirements.txt
```

Run `python start.py` after you configured the settings above. Exit by pressing <kbd>Ctrl</kbd>+<kbd>C</kbd>.

## Disclaimer

I do not make any claims regarding the stability of the application, or its applicability for your own purposes. Use at your own risk. Code is licensed under the [MIT License](https://opensource.org/licenses/MIT).

**DO NOT USE** in critical security/surveillance scenarios.

## Stability 

Tested on Linux Ubuntu 14.04, runs fine for 3 days so far. parameter: threshold 300 frame rate 23, bascially you can watch 5min length of actual recording in less than 2 mins.
