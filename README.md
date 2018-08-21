# GxbManager for BeiHang v0.0.1b
快捷进行后台挂课，并自动完成中途的弹出问题，并自动跳过讨论与测验。

本项目完全开源，目的是为了促进技术交流学习，禁止任何对国家、企业、个人等构成危害的非法用途，否则后果自负。

## 安装与运行
GxbManager依赖selenium运作。
```console
pip install selenium
```
欲运行，在终端键入
```console
python console.py
```

## 使用
GxbManager会自动打开浏览器窗口，在终端输入指令即可执行。大部分指令都需要你打开一个课程的视频才能运作，这可能在之后的版本中改进。
### 指令列表
| 指令     | 作用               |
| :------: | :----------------: |
| h        | 输出帮助信息       |
| s        | 输出视频状态       |
| p        | 播放/停止当前视频  |
| a        | 回答弹出问题*      |
| n        | 跳转到下一视频     |
| g [链接] | 打开指定链接       |
| q        | 退出程序**         |
| lg       | 一键登录           |
| ao       | 开启全自动挂课模式 |
| af       | 关闭全自动挂课模式 |

*目前未遇到多问题的情况，因此暂时仅支持单问题。<br>
**程序运行正常的情况，请务必使用q命令退出程序，即使关掉了浏览器窗口也是如此。
### 自动登录
使用lg命令，你可以快速登录你的账户。替换user.json中的USERNAME及PASSWORD即可。你也可以使用命令行参数选择其他配置文件。
```console
python console.py -f filename
```
### 无头模式
使用命令行参数-n开启无头（无界面）模式。无头模式需要headless chrome或headless chromium支持，根据[chromium文档](https://chromium.googlesource.com/chromium/src/+/lkgr/headless/README.md)的说法，目前似乎是只支持Linux的。

一个无头模式的典型用法是在服务器使用GxbManager，一键登录后使用g命令跳转到视频页面并在服务器自动挂课。

一个在晚上4点连续看网课的人显然是异常的，请酌情使用。
### 全自动挂课
全自动挂课将自动处理视频暂停，弹出问题，同时跳过讨论与测验。在使用全自动挂课前，亦需打开一个有效视频。
## 开发
欲在其他院系使用此脚本，可能需要做出以下更改：
- GxbManager.CLASS_REGEX
- GxbManager.CLASS_STRING
- console.GXB_LOGIN
## TODO
- 加入不同课程之间的跳转
- 加入完全无人值守模式
- 使用http server替端
- 增强代码通用性
- 增加日志机制，改善错误处理
