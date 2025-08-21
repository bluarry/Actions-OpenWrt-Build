# Actions-OpenWrt
Build Immortalwrt for CMCC RAX3000Q/QY using GitHub Actions

Kernel Version : 5.4-QSDK

- Support IPV6
- Support Wi-Fi NSS
- Support NAT NSS

Base from [P3TERX/Actions-OpenWrt](https://github.com/P3TERX/Actions-OpenWrt)

Get SSH: [GetSSH](https://hugo.utermux.dev/default/rax3000q-latest/)

UBoot: [UBoot](https://github.com/hzyitc/openwrt-redmi-ax3000/issues/73#issuecomment-2259591683) Set computer ip to:192.168.1.8, use LAN1 port.
## Actions
- kkstone-build-openwrt_rax3000q.yaml use kkstone branch to build openwrt for rax3000q
- [work in progross]lede-build_rax3000q.yaml  use lede branch to build openwrt for rax3000q


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

## License

[MIT](https://github.com/P3TERX/Actions-OpenWrt/blob/main/LICENSE) © P3TERX 

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

### golang版本不对
1. golang 使用以下仓库的1.20分支
https://github.com/sbwml/packages_lang_golang/tree/20.x

2. 执行以下命令安装golang
./scripts/feeds install -p lang -a golang

3. 执行以下命令编译golang
make feeds/packages/lang/golang/compile -j1 V=s    

### dns46报错编译失败
1. vi /home/ubuntu/Actions-OpenWrt-Build/openwrt/package/kernel/nat46/Makefile
2. 增加 -Wno-vla选项，忽略warning转为error

