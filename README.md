# skyland-auto-sign

明日方舟森空岛一键签到脚本，基于python

使用Github Actions托管（相比云函数来讲非常推荐，因为有日志会存储，而且也免费）

## 快速导航

- [使用Github Actions托管](#mode3)
- [使用家用NAS](#mode4)
- [多账号支持](#multiple_account)
- [多端登录问题](#multiple_login)
- [有关新版本参数验证](#sign-headers)
- [有关新版本获得Cred必传的dId参数](#dId)

[视频用法]( https://www.bilibili.com/video/BV1DP411h7s6)

<a name="mode1"></a>

## 方法3

使用Github Action自动运行脚本

本方法需要你有一定的git使用经验

首先确认自己的github处于登录状态，然后自己新建一个仓库

将本仓库的源代码全部下载下来，上传到github

进入自己仓库的项目主页后，在上方的菜单中进入Settings > Secrets and variables > Actions

点击 New repository secret


 **创建名为`TOKEN`的环境变量（注意变量名全大写），并填入你的鹰角网络通行证，如果要管理多个账号，换行即可** 

 **如果要开启 Server酱³ APP 推送的话，就创建名为 `SC3_SENDKEY` 的环境变量；如果是第一次使用 Server酱³ 的话，需要到 [Server酱³ 官网](https://sc3.ft07.com/) 注册一个账号，再在手机上下载 Server酱³ App。**

`SC3_SENDKEY`: Server酱³ SendKey（形如 sctp12345tXXXX...）


如果是第一次使用GitHub Action的话，还需要手动打开这个功能 在你仓库上方菜单中进入Actions

点击 I understand... enable them > Enable workflow

之后就可以自动运行签到了, 想要手动测试的话，选择左侧的Auto Sign > Run workflow, 刷新页面就能看到结果了

现在可以在Github Action Variable中设置变量`EXIT_WHEN_FAIL = on`，当签到发生错误时，脚本会返回错误，进而你会收到来自Github的邮件，及时知道脚本运行情况

<a name="mode3"></a>
