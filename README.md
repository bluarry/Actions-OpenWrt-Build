#首先致敬两位大神：

@coolsnowwolf大神  项目地址https://github.com/coolsnowwolf/lede

@P3TERX大神        项目地址：https://github.com/P3TERX/Actions-OpenWrt

Actions-OpenWrt 本项目可编译自定义固件，就算恢复出厂也能保留预设的参数。

##注意，注意，注意，用本教程得到的my.files 会保存你的宽带账号、密码，WIFI等个人信息，必须把仓库设为个人，不能是公开！避免泄露个人信息！

##第一步：先按大神的教程定制你需要的固件，在my.config文件内填入按教程得到seed.config内容，生成定制固件。

##第二步，路由器刷固件，然后设置好各项参数WFI,账号之类的，重启。（不要增加删除软件，要在第一步做好选择）

##第三步：获取files文件，以K2为例：SSH进入路由器，输入：
#####   find /overlay/upper -type f | xargs tar -cvpf /tmp/my.files
#########说明 /overlay/upper 为固件的用户数据区，你设置路由器后更改过的文件都在这里

##第四步：到 /tmp 目录下找到 my.files 文件，把该文件上传至本项目的根目录（和.config相同目录）##

##第五步：再次打开 my.config 在最后回车加空行，就能保存了。

##第六步：等固件生成，路由器刷最后得到的固件。现在你恢复出厂，之前设定好的参数一样还在。


其余文件说明##############################################################

Actions-OpenWrt内增加了K2的配置编译文件，

beta.config ：固件为默认功能，重新保存后。会启动2个编译程序，生成2款固件。一款代码为LEDE-Actions/lede（代码不更新版），另一款代码为coolsnowwolf/lede大神同步更新源码。

K2.config ：同上生成2款固件。功能如下:界面主题argon，IPv6，adbyby-plus去广告，IP/MAC绑定，计划重启，DDNS，防火墙，网络加速，访客WIFI，内存释放，ShadowSocksR Plus+ ，ShadowSocksR服务端，UPnP，WIFI计划，网络唤醒。
###（VPN用SSR替代； 内网穿透种类太多，没集成需要装就是了（ROM剩余860KB）,去掉了不实用的FTP、打印机之类的无用功能。）###

##############################################################


# Actions-OpenWrt

[![LICENSE](https://img.shields.io/github/license/mashape/apistatus.svg?style=flat-square&label=LICENSE)](https://github.com/P3TERX/Actions-OpenWrt/blob/master/LICENSE)
[![GitHub Stars](https://img.shields.io/github/stars/P3TERX/Actions-OpenWrt.svg?style=flat-square&label=Stars)](https://github.com/P3TERX/Actions-OpenWrt/stargazers)
[![GitHub Forks](https://img.shields.io/github/forks/P3TERX/Actions-OpenWrt.svg?style=flat-square&label=Forks)](https://github.com/P3TERX/Actions-OpenWrt/fork)

Build OpenWrt using GitHub Actions

[Read the details in my blog (in Chinese) | 中文教程](https://p3terx.com/archives/build-openwrt-with-github-actions.html)

[GitHub Actions Group](https://t.me/GitHub_Actions) | [GitHub Actions Channel](https://t.me/GitHub_Actions_Channel)

## Usage

- Sign up for [GitHub Actions](https://github.com/features/actions/signup)
- Fork [this GitHub repository](https://github.com/P3TERX/Actions-OpenWrt)
- Generate `.config` files using [Lean's OpenWrt](https://github.com/coolsnowwolf/lede) source code.
- Push `.config` file to the GitHub repository, and the build starts automatically.Progress can be viewed on the Actions page.
- When the build is complete, click the `Artifacts` button in the upper right corner of the Actions page to download the binaries.

## Acknowledgments

- [Microsoft](https://www.microsoft.com)
- [Microsoft Azure](https://azure.microsoft.com)
- [GitHub](https://github.com)
- [GitHub Actions](https://github.com/features/actions)
- [tmate](https://github.com/tmate-io/tmate)
- [mxschmitt/action-tmate](https://github.com/mxschmitt/action-tmate)
- [csexton/debugger-action](https://github.com/csexton/debugger-action)
- [Cisco](https://www.cisco.com/)
- [OpenWrt](https://github.com/openwrt/openwrt)
- [Lean's OpenWrt](https://github.com/coolsnowwolf/lede)

## License

[MIT](https://github.com/P3TERX/Actions-OpenWrt/blob/master/LICENSE) © P3TERX
