# Bilibili Evolved 视频链接下载器

> **重要: 链接下载器将停止更新, 请更换使用 aria2. [详细信息](https://github.com/the1812/Bilibili-Evolved/blob/preview/aria2-notice.md)**

从 [Bilibili Evolved](https://github.com/the1812/Bilibili-Evolved/) 复制的视频数据下载视频, 用于解决 Chrome 无法下载超过 2GB 视频的限制, 以及 Firefox 内存占用过大导致标签页卡顿的问题.

适用于长视频(几个小时)的下载, 短视频可以直接在浏览器中完成下载.

## 安装

环境需求: 需要已安装 [Node.js](https://nodejs.org/zh-cn/), 否则会没有 `npm` 命令.

在您的终端中执行:
```shell
npm install -g bilibili-evolved-video-link-downloader
```
> Windows 系统的终端可以从 **资源管理器** 里的 **文件** - **打开 Windows Powershell** 启动.

安装完成后, 即可使用 `vld` 命令来下载视频.

要卸载的话, 只需把 `install` 换成 `uninstall`.
```shell
npm uninstall -g bilibili-evolved-video-link-downloader
```

## 使用
在网页中选择 附加功能-下载视频, 选择清晰度后选择`复制数据`或`导出数据`.

然后在要保存视频的文件夹中打开终端.

如果选择的是`复制数据`, 直接执行`vld`, 程序会自动读取剪贴板中的内容:
```shell
vld
```
如果选择的是`导出数据`, 且假定保存的文件是`xxx.json`, 则要在后面加上文件名:
```shell
vld xxx.json
```

## 其他选项

### 指定分段数
一个视频下载时会分成多段同时下载, 分段数默认为30, 更改分段数可使用`-p`或`--parts`选项.

例如分12段下载:
```shell
vld -p 12
```

### 指定输出目录
如果需要下载到不同于当前目录的位置, 可以指定一个输出目录, 使用`-o`或`--output`选项.

例如下载到`xxx`文件夹中:
```shell
vld -o xxx
```

## 已知问题
下载过程中有时候会出现速度降为0或者疑似下载完成但没有写入磁盘的情况, 多发于批量导出或大文件. [issue #139](https://github.com/the1812/Bilibili-Evolved/issues/139)
