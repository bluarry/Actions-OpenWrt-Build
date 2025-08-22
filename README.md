# Actions-OpenWrt
Build OpenWrt for some routers using GitHub Actions

## 支持的路由器
- xiaomi router r3
- cmcc rax3000q/rax3000qy

| 路由器 | openwrt版本 | 源码链接 |
| --- | --- | --- |
| cmcc rax3000q/rax3000qy | openwrt-21.02 | https://github.com/kkstone/immortalwrt-ipq50xx |
| xiaomi router r3 | openwrt-21.02 | https://github.com/bluarry/openwrt.git |



## Actions
- kkstone-build-openwrt_rax3000q.yaml use kkstone branch to build openwrt for rax3000q
- build-openwrt-xiaomi-r3.yml  use openwrt branch openwrt-21.02 to build openwrt for xiaomi router r3


## Extra
local build use ubuntu:22.04

```
sudo apt install -y ack antlr3 asciidoc autoconf automake autopoint binutils bison build-essential \
          bzip2 ccache clang cmake cpio curl device-tree-compiler ecj fastjar flex gawk gettext gcc-multilib-x86-64-linux-gnu \
          g++-multilib-x86-64-linux-gnux32 git gnutls-dev gperf haveged help2man intltool lib32gcc-s1-amd64-cross libc6-dev-i386-cross libelf-dev \
          libglib2.0-dev libgmp3-dev libltdl-dev libmpc-dev libmpfr-dev libncurses5-dev libncursesw5 \
          libncursesw5-dev libpython3-dev python3-distutils libreadline-dev libssl-dev libtool lld llvm lrzsz mkisofs msmtp \
          nano ninja-build p7zip p7zip-full patch pkgconf python2.7 python3 python3-pip python3-ply \
          python3-pyelftools qemu-utils re2c rsync scons squashfs-tools subversion swig \
          texinfo uglifyjs upx-ucl unzip vim wget xmlto xxd zlib1g-dev libtiff-dev
```
### 安装包说明
1. 支持passwall2
2. 支持wireguard

### golang版本不对
1. golang 使用以下仓库的1.21分支
https://github.com/sbwml/packages_lang_golang/tree/21.x

2. 执行以下命令安装golang
./scripts/feeds install -p lang -a golang

3. 执行以下命令编译golang
make feeds/packages/lang/golang/compile -j1 V=s    

### dns46报错编译失败
1. vi /home/ubuntu/Actions-OpenWrt-Build/openwrt/package/kernel/nat46/Makefile
2. 增加 -Wno-vla选项，忽略warning转为error
```
sed -i 's/\(EXTRA_CFLAGS=".*\)"/\1 -Wno-vla"/' package/kernel/nat46/Makefile
```



## Acknowledgments

- [Microsoft](https://www.microsoft.com)
- [Microsoft Azure](https://azure.microsoft.com)
- [GitHub](https://github.com)
- [GitHub Actions](https://github.com/features/actions)
- [tmate](https://github.com/tmate-io/tmate)
- [mxschmitt/action-tmate](https://github.com/mxschmitt/action-tmate)
- [csexton/debugger-action](https://github.com/csexton/debugger-action)
- [Cisco](https://www.cisco.com/)
- [ImmortalWrt](https://github.com/kkstone/immortalwrt-ipq50xx)
- [OpenWrt](https://github.com/openwrt/openwrt)
- [OpenWrt-21.02](https://github.com/bluarry/openwrt)
- [kkstone/Actions-OpenWrt-RAX3000Q](https://github.com/kkstone/Actions-OpenWrt-RAX3000Q)

## License

[MIT](https://github.com/P3TERX/Actions-OpenWrt/blob/main/LICENSE) © P3TERX 
