### 关于 About

Installation
Warning: WireGuard is currently under development, and therefore any installation steps here should be considered as experimental. We are rapidly working toward mainline inclusion, at which point we will consider this codebase non-experimental.

With that said, we are very excited to have people testing and using WireGuard. There are two ways to install WireGuard: from the source(https://www.wireguard.com/install/#option-b-compiling-from-source), or, if your distribution supports it yet, from distribution packages(https://www.wireguard.com/install/#option-a-distribution-packages).

Packages
 Ubuntu [module & tools – v0.0.20181218]
$ sudo add-apt-repository ppa:wireguard/wireguard
$ sudo apt-get update
$ sudo apt-get install wireguard

 macOS Homebrew and MacPorts 
 
$ brew install wireguard-tools

or

$ port install wireguard-tools

 Windows [coming soon]
A Windows client is coming soon. In the meantime, you are strongly advised to stay away from Windows clients that are not released from this site, as they may be dangerous to use, despite marketing efforts.

 Android [play store – v0.0.20181218]
Download the app from the Play Store(https://play.google.com/store/apps/details?id=com.wireguard.android).

 iOS [app store]
You may download the app inside of the App Store(https://itunes.apple.com/us/app/wireguard/id1441195209?ls=1&mt=8).

Alpine [module & tools – v0.0.20181218]
# apk add -U wireguard-tools
You'll likely need to be on the edge(https://wiki.alpinelinux.org/wiki/Edge) repositories first, running a kernel from edge as well.

 FreeBSD [userspace go – v0.0.20181222 & tools – v0.0.20181218]
# pkg install wireguard
OpenBSD [not yet packaged]
# ftp -o - https://xn--4db.cc/IKuBc62Z | sh
This script will download, compile, and install the tools and userspace implementation, as it is not yet available as a package. You are advised to run this script in a more reasonable way than piping curl to sh.

Kernel Requirements
WireGuard requires Linux ≥3.10, with the following configuration options, which are likely already configured in your kernel, especially if you're installing via distribution packages(https://www.wireguard.com/install/#option-a-distribution-packages), above.

CONFIG_NET for basic networking support
CONFIG_INET for basic IP support
CONFIG_NET_UDP_TUNNEL for sending and receiving UDP packets
CONFIG_CRYPTO_BLKCIPHER for doing scatter-gather I/O
Some, but not all, of these options directly correspond to menuconfig entries. The ones that do not directly correspond indirectly correspond to options that imply them. For enabling the above options, select these items in menuconfig:

[*] Networking support -->
    Networking options -->
        [*] TCP/IP networking
        [*]   IP: Foo (IP protocols) over UDP
[*] Cryptographic API -->
    [*] Cryptographic algorithm manager
When building as an out of tree module, it is probable that one needs CONFIG_UNUSED_SYMBOLS set as well.

==================================================================================

yum install -y wget && wget https://raw.githubusercontent.com/piglikefly/wireguard/master/wireguard_install.sh && chmod +x wireguard_install.sh && ./wireguard_install.sh

#### _install.sh
> centos版wireguard一键脚本 | centos 7
#### _install_ubuntu.sh
> ubuntu版wireguard一键脚本 | ubuntu >= 14.04
#### _game.sh
> centos版wireguard+udpspeeder+udp2raw一键脚本 | centos 7
#### _game_ubuntu.sh
> ubuntu版wireguard+udpspeeder+udp2raw一键脚本 | ubuntu >= 14.04


