# Aria2 Perfect Configuration

[![LICENSE](https://img.shields.io/github/license/mashape/apistatus.svg?style=flat-square&label=LICENSE)](https://github.com/P3TERX/aria2_perfect_config/blob/master/LICENSE)
[![GitHub Stars](https://img.shields.io/github/stars/P3TERX/aria2_perfect_config.svg?style=flat-square&label=Stars&logo=github)](https://github.com/P3TERX/aria2_perfect_config/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/P3TERX/aria2_perfect_config.svg?style=flat-square&label=Forks&logo=github)](https://github.com/P3TERX/aria2_perfect_config/fork)

This project is a set of Aria2 configuration scheme, including configuration files, additional function scripts and other files, used to achieve the enhancement and expansion of Aria2 features, improve the download speed and experience of Aria2, solve the problems encountered in the use of Aria2 BT download speed, file residuals occupy disk space, task loss, repeated downloads and other problems.

## Features

* High BT download rate and fast speed
* No loss of task progress after restart, no duplicate downloads
* Download error or cancel download automatically delete unfinished files to prevent disk space occupation
* Auto-clean `.aria2` suffix file when download is finished
* Get BT tracker with one click to further improve BT download speed
* Better PT download support
* Certain anti-copyright complaints and anti-Xunlei blood-sucking effects
* Automatic uploading to Google Drive and OneDrive by linking RCLONE

## Deployment options

**Recommended to deploy with the following projects for the best experience**

- [Aria2 Pro](https://github.com/P3TERX/docker-aria2-pro) (Docker)

- [Aria2 One-Click Installation and Management Script Enhanced](https://github.com/P3TERX/aria2.sh) (GNU/Linux)

## Advanced Play

* [OneDrive, Google Drive, etc. offline download](https://p3terx.com/archives/offline-download-of-onedrive-gdrive.html)
* [Baidu.com dump to OneDrive, Google Drive and other network drives](https://p3terx.com/archives/baidunetdisk-transfer-to-onedrive-and-google-drive.html)

## File description

> **TIPS:** Script needs to be used with configuration file, only for GNU/Linux

| File | Description |
| ----------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `aria2.conf` | The Aria2 configuration file. Version 1.35.0 and above is recommended. Modifying without knowledge may invalidate features of this solution.                                                                                                                                                                           |
| `delete.sh` | File deletion script. Execute ([on-download-stop](https://aria2.github.io/manual/en/html/aria2c.html#cmdoption-on-download-stop)) after downloading has stopped to automatically delete files and files with the `.aria2` suffix. prevent unnecessary disk space usage. (enabled by default)
| `clean.sh` | Cleanup script. Execute ([on-download-complete](https://aria2.github.io/manual/en/html/aria2c.html#cmdoption-on-download-complete)) after the download is complete to automatically clean up the `.aria2` 后缀名文件。 （默认启用） |
| `upload.sh` | Upload script. Execute ([on-download-complete](https://aria2.github.io/manual/en/html/aria2c.html#cmdoption-on-download-complete)) after the download is complete, which automatically calls RCLONE to upload ( move) the downloaded files to the network drive and automatically clear the `.aria2` suffix files with empty directories. (Not enabled by default) |
| `move.sh` | File move script. Execute ([on-download-complete](https://aria2.github.io/manual/en/html/aria2c.html#cmdoption-on-download-complete)) after the download is complete to automatically move the downloaded files to the specified directory and automatically removes `.aria2` suffix files with empty directories. (Not enabled by default) |
| `tracker.sh` | BT tracker list update script. Execute it in the directory where the Aria2 configuration file (`aria2.conf`) is located to get the [latest tracker list](https://raw.githubusercontent.com/XIU2/TrackersListCollection/master/all.txt) and add it to the configuration file. This script has more powerful features, see [tracker.md](./tracker.md) |
| `dht.dat`<br>`dht6.dat` | DHT files. One of the keys to improve BT download rate and download speed. Related Science：《[Solve the problem that Aria2 can not download magnetic links, BT seeds and slow speed](https://p3terx.com/archives/solved-aria2-cant-download-magnetic-link-bt-seed-and-slow-speed. html)》 |

## How to deal with issues

You can also join the [Aria2 TG Group](https://t.me/Aria2c) to discuss with your buddies. Be careful how you ask questions and provide useful information, before asking questions it is recommended to study the [Wisdom of Asking Questions](https://github.com/ryanhanwu/How-To-Ask-Questions-The-Smart-Way/blob/master/README-zh_CN.md), which can better help you to solve problems and save time. Questions such as "Why doesn't it work?" , "Can you help me then?" No one should know about such questions.

## Changelog

**A brand new version is coming soon, stay tuned...**

Update Push: [Aria2 Channel](https://t.me/Aria2_Channel)

### 2020-06-27 | V2 Ultimate

Configuration file (`aria2.conf`).
- Optimize option parameters to improve download speed and usage experience
- Optimize the layout format and comments to improve the reading experience

Additional function scripts.
- `delete.aria2.sh` renamed to `clean.sh`
- renamed `autoupload.sh` to `upload.sh`
- Detailed improvements to improve the experience

<details>
<summary>History</summary>

### 2020-06-08

Configuration file (`aria2.conf`).
- Turn off file preallocation by default (`file-allocation=none`) to maximize filesystem compatibility.
- Other detail improvements

Other.
- Update DHT files

### 2020-05-03

Configuration file (`aria2.conf`).
- Optimize some setting options with comment descriptions.
- Add unofficial enhancement options. Only available for projects built by [myfreeer/aria2-build-msys2](https://github.com/myfreeer/aria2-build-msys2) and [P3TERX/aria2-builder](https://github.com/P3TERX/ aria2-builder) built by the project.

### 2020-04-16

- Added file move script (`move.sh`) to move downloaded files to the specified directory. Similar to the auto-upload script, the directory structure can be preserved intact for BT multiple files.

### 2020-04-12

- Refactor the BT tracker list update script (`tracker.sh`) to add the ability to update the BT tracker via RPC, without restarting Aria2.

### 2020-03-11

Configuration file (`aria2.conf`).
- Added Logging settings. The default log level is `warn`, which only outputs warnings and errors, significantly reducing log generation and facilitating troubleshooting.

### 2020-02-18

> **TIPS:** This update refactors all additional function scripts. For those who use the [Aria2 one-click installation management script](https://github.com/P3TERX/aria2.sh), please uninstall and upgrade to the latest script deployment. For those who use the [Aria2 Pro](https://github.com/P3TERX/docker-aria2-pro) Docker image, please delete the configuration file directory and then pull the latest image for deployment.

RCLONE auto-upload script (`autoupload.sh`):
- The file filtering function has returned strongly, with more powerful functions for file size filtering and file type filtering.
- Added RCLONE advanced settings: custom configuration file path, configuration file decryption, number of parallel uploads and other functions.
- Enhanced upload failure retry mechanism.

other:
- Optimize the judgment logic of automatic deletion scripts (`delete.sh`, `delete.aria2.sh`).
- Removed outdated configuration items in configuration file (`aria2.conf`)
- Update DHT files

### 2020-02-05

Configuration file (`aria2.conf`):
- Update client masquerading settings
- Forced encryption is enabled by default (anti-copyright complaint, Thunder blood-sucking)

### 2020-01-22

Configuration file (`aria2.conf`):
- By default, IPv6-related functions are disabled to prevent abnormal DHT functions caused by not supporting IPv6.
- Update client camouflage settings to better support PT download in theory.
- Added BT encryption settings, which theoretically can prevent copyright complaints and Thunder blood-sucking.

### 2020-01-15

- Adjusted script comments and formatting.
- Optimize the `delete.sh` judgment logic to prevent files from being deleted due to incorrect usage (inconsistent paths).

### 2019-11-28

Configuration file (`aria2.conf`):

- Optimize configuration parameters

Other documents:

- Update DHT files

### 2019-11-25

Additional function script:

- Modify Trackers source ([XIU2/TrackersListCollection](https://github.com/XIU2/TrackersListCollection))

### 2019-10-23

Additional function script:

- Added BT tracker acquisition script

### 2019-10-21

Configuration file (`aria2.conf`):

- Optimize configuration parameters
- Solved the bug of repeated download of completed tasks after restarting
- ~~Added a bug where completed tasks disappear after restarting (fog~~

Additional function script:

- Fixed a bug in `autoupload.sh` that caused **upload failure retry function** misjudgment due to the remaining empty directory after Rlone upload
- Improve the path judgment logic of `delete.sh` and `delete.aria2.sh`, and add the function of deleting empty directories.

### 2019-10-10

Additional function script (`autoupload.sh`):

- Add upload failure retry function

### 2019-06-08

Additional function script (`autoupload.sh`):

* Optimized path judgment logic
* Fix the bug that the path cannot be determined when all files under the BT download folder are downloaded

### 2019-05-23

Additional function script (`autoupload.sh`):

* Remove upload size limit
* Optimized path judgment logic
* Adjust script trigger log

### 2019-02-13

Configuration file:

* Optimize configuration parameters

### 2019-01-31

Configuration file:

* Adjustment Notes

Other files:

* Update DHT (IPv4) files

### 2019-01-14

Additional function script:

* Fixed `autoupload.sh` uploading the entire `root` directory bug in some cases
* Optimize `autoupload.sh` to output upload file path in log

### 2019-01-09

Additional function script:

* Fix `autoupload.sh` bug where file upload location is incorrect in some cases
* Fix `delete.sh` bug not deleting files in some cases
* Other optimization adjustments
* ~~Add a bug where `autoupload.sh` uploads the entire `root` directory in some cases~~

### 2018-12-25

Configuration file:

* Adjusted to run `info.sh` when the download is paused, not enabled by default

Additional function script:

* Optimize the experience of using `autoupload.sh` to automatically upload scripts. When the script is triggered, a high-energy reminder will be output in the log to prevent Mengxin from being confused
* Added `info.sh` download task information display script
* Remove `test.sh` test script

### 2018-12-22

Configuration file:

* Adjust the expected download speed parameters

Additional function script:

* Fixed a bug with complications when downloading folders
* Optimize the judgment conditions when downloading folders

### 2018-12-11

Additional function script:

* Fix incomplete upload and other bugs when BT downloads multi-level directories

### 2018-12-07

* Add DHT (IPv4) file
* Adjust the configuration file
* Integrated into [Aria2 one-click installation management script](https://github.com/P3TERX/aria2.sh)

### 2018-11-10

* first submission

</details>

## declaration

This project uses the [MIT](https://github.com/P3TERX/aria2.conf/blob/master/LICENSE) open source agreement. Please abide by the relevant agreement for copying, modifying, publishing, etc. to retain the copyright in all files. thank you for your cooperation!
