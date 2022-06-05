# Frequently asked questions

Feedback QQ group: 689636812

Chat QQ group: 725135081 (chit-chat only, no support provided)

Feedback Email: rec@danmuji.org

This page is intended for BililiveRecorder Desktop, but most information should also apply to the CLI version.

## Installation

### Unsupported operating systems

BililiveRecorder does not support certain outdated operating systems. For details, please read [System Requirements](./system-requirements.md).

### Download failed

Sometimes browsers like Microsoft Edge might block download for reasons like "**This file might be unnecessary program**".

Solution: click the menu/options icon next to the downloading file icon (might look like three dots or an up arrow), and select things like "**Keep file**" or "**Download anyway**" from the menu.

### Installation blocked by operating system

Sometimes Windows shows a pop-up that reads "**SmartScreen has protected your PC**" and block installation of BililiveRecorder.

Solution: click the "**More info**" on the pop-up (which will be in a slightly different color), then a "**Run anyway**" button will appear. Click that button.

### Error message "Installation has failed"

Your system might lack certain components or the system was modified somehow.

Solution: try to manually install [.NET Framework 4.8](https://dotnet.microsoft.com/zh-cn/download/dotnet-framework/thank-you/net48-offline-installer). If this failed to install, maybe your system is too old to be supported.

It is also possible that your anti-virus silently blocked installation or silently removed some files.

Solution: temporarily turn off the anti-virus, or whitelist BililiveRecorder in your anti-virus.

### Crash or error after installation

If an error message reads "**Cannot load file or program set**", it's because some files needed are deleted. In most cases, this is because your anti-virus deleted some files silently in the background.

Solution: re-download installation program and re-install. (You don't need to first uninstall, just run installation again.)

Crash might also be due to other reasons, like a system fault, a problem of graphics drivers, a problem with your hardware, etc. If reinstalling doesn't help, please ask by joining the QQ groupchat or sending an email.

## Usage

### Can I record my own live stream using BililiveRecorder?

Yes, but **not recommended**.

As your stream gets uploaded to and downloaded from Bilibili's servers, some weird things might happen, and it's also subject to outside factors like network problems.

We recommend you to use the recording function within your live streaming program, which is more stable and uses less of your device's resources.

For Bilibili 直播姬, just click the recording button next to the start stream button.

For OBS, please check **Settings** -> **Output** -> **Recording** -> **Recording quality**, and set to **Same as stream**. If you are using advanced output mode, then set **Encoder** to **(Use stream encoder)**.

When recording with OBS, it is recommended to set recording format to `MKV`. This makes the file still playable in case OBS unexpectedly closed (like crash or power outage). If you need `MP4`, you might use **File** -> **Remux recordings** to convert file format quickly.

### I can't switch to the channel list page

In order to record a live stream, you need to first select a working directory. The working directory is where config and recordings are saved.

If you instead clicked **Toolbox** on startup, then you can only use toolbox features for this session and cannot record a live stream.

### When I select a working directory, it says there are already other files

BililiveRecorder needs a empty folder for its own in order to save its data. You cannot select paths like Desktop, Documents or root of C:\. Please create a new folder for BililiveRecorder in a place with plenty of remaining disk space.

If you have been previously using a directory and it starts saying **already have other files**, maybe it's because the config file is lost. BililiveRecorder stores its config in `config.json` in the working directory, and it will also make a backup of this file as `config.backup.json`. If the config file is lost, you can copy the backup file and rename to `config.json`.

### In the logs, it says "error when starting recording: NotFound"

It is **normal** to get this error when the stream just started or just ended.

I'll spare you the wall of text from the original Chinese FAQ, but this basically happens when the channel is "live" on the Bilibili dashboard but not streaming any data to the servers. Unlike Twitch which automatically detects you streaming data to their servers, Bilibili requires you to toggle your channel status manually, creating this period of problematic time.

### What are the differences between recording modes?

Read [Recording Mode](./record-mode.md).

(Translator's note: in a nutshell, raw mode dumps data from the servers directly onto your hard drive, while normal mode attempts to parse and analyse the data, and attempt to fix any problems.)

### What do I do with the files from recording chat?

You can open the file directly in a modern web browser like Chrome, Firefox or Edge. IE is unsupported.

For more ways to use them, read [Recording Chat](./danmaku.md).

### What is "raw chat data"?

Raw chat data is the original JSON data from the servers.

If you don't know what to do with it, likely you don't need to save it. Turning off "save raw chat data" to massively reduce file size of recorded chat.

### 画质 ID 是什么？

画质 ID 决定了录播姬会录制哪个“画质”的直播，不同的画质全部都是B站直播服务器提供的。

具体设置说明请查看 [软件设置](./settings.md#画质ID) 页面。

### 可以录制 “原画 Pro” 吗？

带 “Pro” 字样的画质的视频编码格式是 HEVC (H.265)，压缩率更高、码率更低。  
“原画 Pro”(HEVC, H.265) 是从 “原画”(AVC, H.264) 二压出来的。

录播姬不支持录制 HEVC 流。

### 可以设置录制的码率吗？

不能，录播姬不会对直播画面重新编码，不能设置录像的码率。

请注意，画质 ID 不是码率设置。

### 可以设置录制的分辨率、帧率吗？

不能，录播姬不会对直播画面重新编码，不能设置录像的分辨率和帧率。

请注意，画质 ID 不是分辨率、帧率设置。

### 可以修改录制的文件格式吗？

不能，录播姬只能输出 FLV 文件。

如果需要 MP4 格式，推荐使用 [其他工具和项目](./other-projects.md) 页面给出的视频处理工具进行 **转封装** 操作。

录播姬桌面版的工具箱里也提供了转封装功能。

### 可以多开吗？怎么多开？

只要选择的工作目录不同，就可以同时运行多个录播姬。

同一个工作目录只能运行一个录播姬。

如果曾经在选择工作目录时勾选了 **不再询问**，可以在房间列表界面的 **文件** 菜单中点击 **切换工作目录** 然后取消勾选 **不再询问** 并确认。

??? note "关于命令行版"
    命令行版没有这个限制，不会检测是否有多个进程在同一个工作目录运行。不过一般来说不会有人会想要在同一个工作目录运行多个录播姬的，用户需要自己检查是否重复运行了。

### 怎么设置开机启动？

录播姬自身没有开机启动设置功能。

可以手动把录播姬的快捷方式复制到系统的 **启动** 文件夹内，启动文件夹的打开方式是：

1. 按 `Windows + R` 快捷键
2. 输入 `shell:startup`
3. 点击运行

推荐阅读 [命令行参数](./commands.md) 页面。

不推荐使用计划任务来实现开机启动，因为计划任务可能会在桌面环境运行之前执行，导致录播姬崩溃或出现其他问题。

??? note "关于命令行版"
    根据具体使用的是 “散装” 的可执行文件还是 Docker 镜像，以及不同的操作系统，实现开机启动的方法各不相同。

    比如 systemd 是 `systemctl enable <service-name>`  
    docker 是加上 `--restart unless-stopped`

    需要用户自行根据自己的使用方式来实现

<!-- 录制 -->

### 房间卡片上的状态条的颜色和箭头是什么意思？

颜色表示的是录制的“稳定”程度，绿色最好、红色最差。

箭头表示的是当前录制的速度是更快还是更慢  
:material-arrow-up-bold: 是当前录制的速度比主播直播的速度快（追赶进度）  
:material-arrow-down-bold: 是当前录制的速度比主播直播的速度快（落后进度）

原始数据模式的状态条显示为 白色/浅蓝色。  
录制速度只有标准模式才能统计到，原始数据模式因为是不经处理直接写入硬盘，所以没有这些统计信息。

### B站二压原画后如何录制真原画？

从大约 2022 年 3 月初开始，哔哩哔哩直播区会对大主播的 “原画” 画质进行二压，在此之前 “原画” 就是主播推流的原始数据。

二压原画的直播流 URL 有 `_blueray` 后缀，而真原画的直播流 URL 没有任何后缀。

```http
https://cn-example-host.bilivideo.com/live-bvc/000000/live_00000_0000000.flv?expires=....
https://cn-example-host.bilivideo.com/live-bvc/000000/live_00000_0000000_bluray.flv?expires=....
```

二压原画是动态码率，实际码率根据画面复杂度变化，metadata 中显示的码率为 10M (10000 kbps)。  
二压原画的音频码率通常是 125K。

![二压原画显示的视频信息](../assets/images/user-faq-yuanhuaerya.png)

只有在直播间观众达到一定数量之后才会启动直播转码，在刚开始直播观众很少的时候是只有真原画这一个选项的。

所以如果想要录真原画直播，需要：

- 在主播开始直播之前就打开录播姬、打开自动录制
- 主播开始直播后立刻开始录制
- 保持录制不断开，直到直播结束

如果录制断开了，重连时就只能获取到二压原画的直播流了。
