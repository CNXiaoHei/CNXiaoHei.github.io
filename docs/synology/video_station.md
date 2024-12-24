# 群晖7.2+如何安装Video Station套件

群晖官方在7.2+版本中已出了Video Station套件和音视频硬件解码组件 Advanced Media Extensions。这代表着群晖计划放弃基于机器本身解码方案。

## 下载Video Station安装脚本

首先下载所需要的脚本

下载地址：https://github.com/007revad/Video_Station_for_DSM_722/releases

下载并解压最新版本，将其中`videostation_for_722.sh`文件上传至群晖中，放置在你的用户目录下(你也可以放置在其他地方)，例如`/volume1/homes/user/`

在控制面板->连接性->终端机，启动ssh

windows中：
打开cmd，输入以下命令，其中user指你的用户名，nas_ip指你的nas在局域网中的ip

```bash
ssh {user}@{nas_ip}
```

输入后会提示你输入密码，直接输入即可，命令行中没有反应是正常现象！！！输入过程后回车可进入nas的命令行界面

执行

```bash
cd /volume1/homes/user/
./videostation_for_722.sh
```

然后会开始安装步骤

安装完成之后打开Advanced Media Extensions，跟随步骤登录群晖账号，下载解码工具

至此，基础部分安装完成

------

如需DTS、EAC3 以及 TrueHD Audio 解码器，需要执行以下步骤

在套件中心增加套件源

名称：Synocommunity

位置：[https://packages.synocommunity.com](https://packages.synocommunity.com/)

完成后在套件中心->社群中搜索FFmpeg6下载并安装

下载脚本工具**[VideoStation-FFMPEG-Patcher](https://github.com/AlexPresso/VideoStation-FFMPEG-Patcher)**并解压

将`patcher.sh`上传至`/volume1/homes/user/`文件夹

执行命令`sudo /volume1/homes/user/patcher.sh -v 6`

到这就OK了