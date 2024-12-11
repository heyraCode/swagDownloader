<div align=center>
<img  src="./zReadme/logo.png" alt="Buy Me A Coffee" style="height: 120px !important;width: 120px !important;" >
</div>

# Swag.live Downloader

[![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](https://choosealicense.com/licenses/mit/)

这是一个xx网站的视频下载器, 请注意本项目只能下载你在xxx上已经购买的视频，详情查看: [xxx](https://baidu.com)
需要注意的是，本项目只适合个人学习使用，请遵守相关协议。

这里放演示视频

## 安装

你可以前往 [Release](xxx) 页面下载对应系统的安装包，如果没有找到对应的安装包则说明目前暂不支持。

### Mac OS

在下载完成并安装之后，如果你是mac的包版本系统 (>= Big sur) 则会提示你如下信息:

![](./zReadme/mac-open-fail.png)

这是因为该项目为学习项目, 所以并没有签署相关苹果秘钥，解决这个问题也很简单，你只需要执行如下指令

```shell
xattr  -d com.apple.quarantine /Applications/SwagDwonloader.app
```

### Windows

## 登录账号

你可以选择两种方式登录你的 `xxx` 账号并用以拉取你已经购买的视频

### 直接登录(推荐)

如果你信任本项目，你可以点击`Activate Your Account` 按钮并且使用账号或者密码进行登录

### 使用Token

如果你比较担心，那么你可以使用源站的`token`进行激活, 详细步骤如下:

**step-1**. 请使用 `Chome`, `Firefox`, `Edge` 等浏览器前往 [xxx.login]() 并登录

**step-2**. 当你登录成功之后，请使用`F12`打开你的浏览器调试工具并选择`console`选项

**step-3**. 你可以使用如下代码尝试提取你的Token

```javascript
var db
var request = indexedDB.open('localforage', 3)
request.onsuccess = function () {
  db = request.result
  var tx = db.transaction('keyvaluepairs', 'readonly')
  var store = tx.objectStore('keyvaluepairs')
  var _request = store.getAll('_refreshToken')
  _request.onsuccess = function () {
    var token = _request.result.toString()
    console.log(token)
  }
}
// or
var db
var request = indexedDB.open('localforage', 2)
request.onsuccess = function () {
  db = request.result
  var tx = db.transaction('keyvaluepairs', 'readonly')
  var store = tx.objectStore('keyvaluepairs')
  var _request = store.getAll('_refreshToken')
  _request.onsuccess = function () {
    var token = _request.result.toString()
    console.log(token)
  }
}
```

**step-4**. 将`_refreshToken`粘贴到`Use Token`输入框中点击`Activate`按钮激活你的账号

## issue

如果你有任何问题可以发布相关的 **issue** 并提供下载日志详情

## Thanks

[FFmpeg](https://ffmpeg.org/)

[N_m3u8dl-RE](https://github.com/nilaoda/N_m3u8DL-RE)

## Sponsor

<a href="https://www.buymeacoffee.com/SwagDownloader" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" alt="Buy Me A Coffee" style="height: 60px !important;width: 217px !important;" ></a>
