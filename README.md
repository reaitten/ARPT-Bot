<!--
 * @Date: 2021-06-05 12:04:51
 * @LastEditors: Ben
 * @LastEditTime: 2021-11-10 21:16:31
-->

[![GitHub Stars](https://img.shields.io/github/stars/666wcy/ARPT-Bot.svg?color=inactived&labelColor=555555&logoColor=ffffff&style=for-the-badge&logo=github)](https://github.com/linuxserver/docker-qbittorrent) [![Docker Pulls](https://img.shields.io/docker/pulls/benchao/arpt.svg?color=inactived&labelColor=555555&logoColor=ffffff&style=for-the-badge&label=pulls&logo=docker)](https://hub.docker.com/repository/docker/benchao/arpt) [![GitHub Release](https://img.shields.io/docker/v/benchao/arpt?color=inactived&labelColor=555555&logoColor=ffffff&style=for-the-badge&label=最新版本&logo=docker)](https://github.com/linuxserver/docker-qbittorrent/releases)

# Changelog

v2.0.9 (current)

Modify the rclone call to rc http api call.

Added support for [RcloneNg](https://github.com/ElonH/RcloneNg).

Mapping `rclone rc`, support for customizing the operation of `rclone rc`, the specific operation can be referred to [rclone rc tutorial](https://rclone.org/rc/).

***
Automatic update is supported after this version, Python file changes can be updated by simply rebooting, other hard updates will only update the version via Docker

Fix conflict between tasks added by aria2 panel and configuration of `conf` file causing local files to be deleted [#18](https://github.com/666wcy/ARPT-Bot/issues/18)[#16](https://github.com/666wcy/ARPT-Bot/) issues/16)

Fix odprivate command failure (conflict with subsequent command causes failure) [#17](https://github.com/666wcy/ARPT-Bot/issues/17)

Fix the default panel account password as default, which is a security risk, change it to account:`admin`, password:the value of `Aria2_secret` you set

<details>

<summary>Previous changelog</summary>

v2.0.8

修复rclone剩余时间显示问题

新增支持多文件同时发送上传TG

新增支持多种子文件同时发送

同步原作者[更新](https://github.com/gaowanliang/OneDriveShareLinkPushAria2/commit/a8dd447040ccd0aca89a3e2680a871200ca8c446)，修复od分享链接文件数直到30的问题，感谢原作者



v2.0.7

修复Bot添加的任务重复调用上传

新增群组功能，支持设置整个群组的人员拥有使用权限，支持自定义设定拒绝词

新增上传完成后返回分享链接(仅支持OD)，权限为：同域、只读

修复Nhentai下载本子失败以及下载完成后本子文件未删除问题

新增发送磁力链接直接链添加任务，默认上传网盘，支持批量磁力

v2.0.6

新增带有密码的公开分享链接的od、sp分享链接下载

新增需要登录账号的分享链接下载，需要同域账号的账号和密码

优化上述推送完成的显示


v2.0.5

新增本子的搜索，此版本支持哔咔、ehentai、nhentai

nhentai支持直接识别链接下载



v2.0.4

合并[搜图机器人](https://github.com/666wcy/search_photo-telegram-bot-heroku)，支持[saucenao](https://saucenao.com/)、[WhatAnime](https://trace.moe/)、[ascii2d](https://ascii2d.net/)、[iqdb](http://www.iqdb.org/)

搜索下载哔咔的本子，支持ZIP文件格式发送到TG和上传网盘

对接 [nhentai](https://github.com/RicterZ/nhentai),下载nhentai本子并支持以ZIP文件格式发送TG、ZIP格式上传网盘、网页格式发送到TG


v2.0.3

对接[OneDriveShareLinkPushAria2](https://github.com/gaowanliang/OneDriveShareLinkPushAria2)的更新，支持sharepoint分享链接。

修复网易云歌单显示不全的问题。

v2.0.1

修复docker构建时rclone安装失败，修复网易云歌单下载到无版权音乐时整个歌单下载停止

v2.0.0

Bot开源，支持arm64，目前没有机子测试，理论可行

v1.1.7

修复pixiv发送到tg时因为尺寸不符合tg api要求报错，取消发送不符合尺寸的图片。

尝试修复下载卡99%的概率性问题，效果未知。

新增网易云音乐的下载，目前支持搜索下载，id下载，整个歌单下载，支持发送到tg和上传到网盘。API接口项目：[NeteaseCloudMusicApi](https://github.com/Binaryify/NeteaseCloudMusicApi),目前使用的是本人的API，有黑胶会员，后续会支持自定义API地址。

QQ音乐如果有稳定接口项目，也可推荐对接Bot

![](https://cdn.jsdelivr.net/gh/666wcy/img_share@main/img/xxx.6kk2hr659yw0.png)

![](https://cdn.jsdelivr.net/gh/666wcy/img_share@main/img/image.l6bobb2z9vk.png)

![](https://cdn.jsdelivr.net/gh/666wcy/img_share@main/img/image.7b3nuhohe4o0.png)

v1.1.6

将pixivtop命令更改为pixivtopall,优化按键选择方式，新增插画榜和男性榜、女性榜、新人榜、原创榜，支持指定日期榜单下载

![](https://cdn.jsdelivr.net/gh/666wcy/img_share@main/img/image.1q6zlq2sggow.png)

v1.1.5

取消pixivuser、pixivusertg、pixivuserphoto、pixivusertele

优化为单个命令pixivauthor

![](https://cdn.jsdelivr.net/gh/666wcy/img_share@main/img/image.7huyt6u0ne40.png)

新增pixiv排行榜的下载(日榜、月榜、周榜),后续将增加插画榜和男性榜、女性榜等

![](https://cdn.jsdelivr.net/gh/666wcy/img_share@main/img/image.1iniuqwtbojk.png)

v1.1.4

新增下载OneDrive 公开分享链接中的文件，保持文件路径推送到Aria2.已实现。采用项目地址：[OneDriveShareLinkPushAria2](https://github.com/gaowanliang/OneDriveShareLinkPushAria2)

修复**downtgfile**命令下载视频失败的错误

优化/rclone命令的显示

</details>


# Introduction

A Python3 based Bot. currently supports deployment on vps as a Docker.

[! [Readme Card](https://github-readme-stats.vercel.app/api/pin/?username=666wcy&repo=ARPT-Bot)](https://github.com/666wcy/ARPT-Bot)

Main features:

- [X] File management
  - [X] Modify the main interface to [filebrowser](https://github.com/filebrowser/filebrowser), the account is **admin**, the password is `Aria2_secret` that you set, the path to the main interface: http://ip:port,请自行修改 Password

- [X] Web Panel
  - [X] Support [AriaNg](https://github.com/mayswind/AriaNg) panel at https://ip:port/ng/
  - [X] Use **Nginx** for internal port inverse generation, replacing the original Python Flask, more lightweight
- [X] Support [RcloneNg](https://github.com/ElonH/RcloneNg), login at `http://ip:port`, please change `ip` and `port` by yourself, username is root, password is `Aria2_secret` that you set

- [X] Aria2
  - [X] Automated Aria2 installation with custom keys
  - [X] Simple Aria2 side control with Bot (add tasks, pause tasks, delete tasks)
  - [X] Support for adding tasks in batches
  - [X] Show download progress
  - [X] Upload via rclone after task completion (**display upload progress**), the latest version of rclone already supports CenturyLink
  - [X] Support rpc connection for aria2 panel-like tools (get, post)
  - [X] Support automatic uploading of tasks added by panel-like tool rpc connection automatically (without displaying progress). The upload method of tasks added via panel is changed to PU's upload script, keeping the original path.
  - [X] Use PU's configuration to add tracker automatically.
  - [X] Download files from OneDrive, sharepoint public share links, keep the file path pushed to Aria2. Implemented. Using the project address: [OneDriveShareLinkPushAria2](https://github.com/gaowanliang/OneDriveShareLinkPushAria2)
  - [ ] Rss automatic download, already finished, not yet docked

- [X] Rclone
  - [X] rclone official lsd, lsf method adaptation
  - [X] rclone copy adaptation, i.e., dual-disk transfer, support for viewing transfer progress
  - [X] rclone copyurl method to upload files, real-time progress display
  - [ X ] support for aria2 panel class tool rpc connection (get, post method)
  - [ ] TG button view rclone directory
  - [ ] Name the current directory file as emby scan format
  - [ ] add rclone configuration, clear rclone configuration via Bot
  - [ ] Get share links for single or multiple folders (gd,od)
  
- [X] Pixiv
  - [X] Get pictures according to PID
  - [X] Download all the works of the artist, support package to upload netdisk, package to send tg, image way to send tg, telegraph (web) way to send images. Archive format is zip.
  - [X] Download daily, weekly and monthly charts, support package uploading, package sending tg, image sending tg, telegraph (web) sending. Archive format is zip.
  - [X] Support downloading the list of specified date

- [X] Audio and video related
  - [X] Download videos with YouTube dl, support uploading to netbook or sending to tg. highest quality by default, currently perfect for YouTube & 和哔哩哔哩 [(Bilibili)](https://www.bilibili.com/)
  - [X] Download YouTube music, support id download, search download, whole song list download, support send to tg and upload to netdisk
  - [X] Add video to MP3 format for sending and uploading
  - [ ] Video and subtitle mixing
  - [ ] Convert common video and audio formats to each other

- [X] Telegram
  - [X] Only the current user's commands take effect
  - [X] Send file id to get file
  - [X] Send file to get file id
  - [X] Send TG file to upload to network drive
  - [X] Support command to view Bot runtime and remaining space
  - [X] Support group use. PS: group version available, considering how to mix and match
  - [ ] Add Bot whitelist

- [X] Image related
  - [X] Merge [Searchbot](https://github.com/666wcy/search_photo-telegram-bot-heroku), support [saucenao](https://saucenao.com/), [WhatAnime](https:// trace.moe/), [ascii2d](https://ascii2d.net/), and [iqdb](http://www.iqdb.org/).
  - [X] Search and download beeping books, support for .zip archive format to send to .zip archive format and upload to netbook
  - [X] Docking [nhentai](https://github.com/RicterZ/nhentai), download nhentai book and support sending Telegram in .zip archive format, uploading netdisk in .zip archive format, sending Telegram in web format
  - [X] 本子的搜索, 支持哔咔, ehentai, nhentai
  - [X] saucenao search map support quick search

 


# Bot Commands

通过在 **@BotFather** 设置命令

<!-- TODO: reword some of the commands below -->

```
start - Check the status of the Bot
help - Get help on using the Bot
pixivauthor - operate on pixiv artists' works
pixivtopall - operate on pixiv leaderboards
pixivtopillust - operate on the illustration leaderboard
pixivpid - send pixiv images with that id
magfile - send seeds to aria2 for downloading and uploading
mirror - send a direct link to aria2 to download and upload to the web site
mirrortg - Push direct link to aria2 to download and send to Telegram
magnet - push magnet link to aria2 for download and upload to netdisk
downtgfile - Send Telegram file and upload to netdisk
rclonecopy - use rclone to transfer between disks
rclonelsd - Show network folders with rclone
rclone - Show details in a folder with rclone
rclonecopyurl - Upload direct link files with rclonecopyurl
getfileid - send a file to get the fileid
getfile - send a fileid to get a file
video - send a link to a video
neteaseid - Get song information by id
searchsong - Search for Netease songs
playlist - Get song list information
odshare - download public od, sp share link files and upload to netease
odprivate - Download odshare links from within the domain and upload them to NetDisk
nhentai - Download the book with the corresponding id in nhentai
ehentai - Download the book with the corresponding id in nhentai
picacgsearch - Search the book in beep, support ZIP upload to netbook and send to Telegram
ehentaisearch - Search for books in ehentai, support ZIP upload to disk and send to Telegram, send to web
nhentaisearch - Search for books in nhentai, support ZIP upload to disk and send to Telegram, send web page
```

# Installation

Docker 部署命令：

~~评论区反馈docker不支持arm架构，推测原因为原docker为amd64架构,目前只在amd64上测试成功~~
目前理论支持所含架构，具体没有进行真机测试

```
docker run -d \
    --name arpt \
    -e Api_hash=xxx \
    -e Api_id=xxx \
    -e Aria2_secret=xxx \
    -e Remote=yun \
    -e Telegram_bot_api=xxx \
    -e Telegram_user_id=xxx \
    -e Upload=xxx \
    -e Rclone_share=False \
    -e Error_user_info="你没有使用权限" \
    -p 8868:8868 \
   benchao/arpt:v2.0.8

```

Configuration explanation

```
Api_hash Api_id 这两项在https://my.telegram.org中注册应用后得到

Aria2_secret    Aria2的密匙

Telegram_bot_api    Bot的API，在@BotFather申请获得

Telegram_user_id    使用者的TG id，可在@userinfobot处获得，设置为群组ID则该群组所有人员可用，需要设置Bot的群组权限

Remote  上传目的地的rclone盘符

Upload  上传文件夹名称，后面不需要加/

Rclone_share 可不填，True 为上传网盘后返回分享链接(onedrive)，False 为关闭该功能，不设置该变量则默认关闭

Error_user_info 可不填，可设置非允许使用者发送消息时的提示，不设置该变量则使用默认语句

```

After Docker is running, visit ip:port to access the file manager, ~~create a new rclone.conf in the folder under /.config/rclone, and paste your own rclone configuration.~~
PS: Some people reported that the configuration here is not successful, you can try to add the configuration in the directory `/root/.config/rclone`, bot run **/rclone disk:**, you can check whether it is successful
About the upload method, just drag the .conf file into the browser.

![Example of Successful Setup](https://cdn.jsdelivr.net/gh/666wcy/img_share@main/img/image.2abs656qyrb4.png)

Docker currently does not support automatic updates, currently updates need to reinstall the new image version by themselves

You can check the latest mirror version number by yourself: [View Address](https://hub.docker.com/repository/docker/benchao/arpt)

# Miscellaneous notes

About the configuration of Aria2 in the panel, ip is the vps port, port is the port set by docker
For example, if the command in docker is
`-p 8868:8868 \`
then the port is 8868
The panel key is the value of your Aria2_secret when docker was created



# Bot Demonstrations 

![](https://cdn.jsdelivr.net/gh/666wcy/img_share@main/img/bot下载种子.501pcym934k0.png)

![](https://cdn.jsdelivr.net/gh/666wcy/img_share@main/img/image.2zx3yt2f8ow0.png)

![](https://cdn.jsdelivr.net/gh/666wcy/img_share@main/img/image.52jb1gwlv4o0.png)

![](https://cdn.jsdelivr.net/gh/666wcy/img_share@main/img/bot视频下载.7b1arubsqa00.png)

![](https://cdn.jsdelivr.net/gh/666wcy/img_share@main/img/bot文件下载.327tinslwa00.png)

![](https://cdn.jsdelivr.net/gh/666wcy/img_share@main/img/image.771n1tka9dg0.png)


# Thanks for the contributions of the following

[![Readme Card](https://github-readme-stats.vercel.app/api/pin/?username=ytdl-org&repo=youtube-dl)](https://github.com/ytdl-org/youtube-dl)

[![Readme Card](https://github-readme-stats.vercel.app/api/pin/?username=pyrogram&repo=pyrogram)](https://github.com/pyrogram/pyrogram)

[![Readme Card](https://github-readme-stats.vercel.app/api/pin/?username=pawamoy&repo=aria2p)](https://github.com/pawamoy/aria2p)

[![Readme Card](https://github-readme-stats.vercel.app/api/pin/?username=FolderMagic&repo=FolderMagic)](https://github.com/FolderMagic/FolderMagic)

[![Readme Card](https://github-readme-stats.vercel.app/api/pin/?username=mayswind&repo=AriaNg)](https://github.com/mayswind/AriaNg)

[![Readme Card](https://github-readme-stats.vercel.app/api/pin/?username=cokemine&repo=ServerStatus-Hotaru)](https://github.com/cokemine/ServerStatus-Hotaru)

[![Readme Card](https://github-readme-stats.vercel.app/api/pin/?username=P3TERX&repo=aria2.conf)](https://github.com/P3TERX/aria2.conf)

[![Readme Card](https://github-readme-stats.vercel.app/api/pin/?username=filebrowser&repo=filebrowser)](https://github.com/filebrowser/filebrowser)

[![Readme Card](https://github-readme-stats.vercel.app/api/pin/?username=gaowanliang&repo=OneDriveShareLinkPushAria2)](https://github.com/gaowanliang/OneDriveShareLinkPushAria2)




