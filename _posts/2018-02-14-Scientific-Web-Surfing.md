---
layout: post
title: Scientific Web Surfing!
data: 2018-02-14 16:18:00
---
# Refered to [Litcc](https://www.litcc.com/2016/12/29/Ubuntu16-shadowsocks-pac/)
> Ironically, you need to kexueshangwang before you visit this guide. I'm considering paste screenshots of original page here.

# Download shadowsocks-qt5
Go to [ss-qt5 download page](https://github.com/shadowsocks/shadowsocks-qt5/releases).\
Download [Shadowsocks-Qt5-3.0.0-x86_64.AppImage](https://github.com/shadowsocks/shadowsocks-qt5/releases/download/v3.0.0/Shadowsocks-Qt5-3.0.0-x86_64.AppImage).
Say you downloaded ss-qt5 AppImage at `home/*username*/Downloads/Shadowsocks-Qt5-3.0.0-x86_64.AppImage`.
Fire up a terminal by `Ctrl` `Alt` `t`. Type and run `cd home/*username*/Downloads/` to land on the directory contains ss-qt5 AppImage.
Run `chmod a+x Shadowsocks-Qt5-3.0.0-x86_64.AppImage` to give permissions to run this ss-qt5.
Run `./Shadowsocks-Qt5-3.0.0-x86_64.AppImage` to start ss-qt5.

# Config shadowsocks-qt5
`Connection` --> `Add` --> `Scan QR Code on Screen`. Then `Connection` --> `Connect`\
You can test your latency after you have connected to the specific server.

# Global Proxy Config
## Install pip
`sudo apt-get install python-pip`\
`pip install --upgrade pip`

## Install GenPac
`sudo pip install genpac`\
`pip install --upgrade genpac`\

## Generate proxy auto-config file
Jump to the directory that you want to store your proxy auto-config file. I went to home: `cd ~` 
genpac --pac-proxy "SOCKS5 127.0.0.1:1080" --gfwlist-proxy="SOCKS5 127.0.0.1:1080" --gfwlist-url=https://raw.githubusercontent.com/gfwlist/gfwlist/master/gfwlist.txt --output="autoproxy.pac"\
The proxy config file has created at `/home/*username*/autoproxy.pac`

## Apply global proxy
`System settings` -->  `Network` --> `Network Proxy`, select *Automatic* in *Method*, *Configuration URL* type in `file:///home/linzhank/autoproxy.pac`. Click *Apply system wide*

# Enjoy kexueshangwang
Now you can read details of [Litcc guide of kexueshangwang](https://www.litcc.com/2016/12/29/Ubuntu16-shadowsocks-pac/)
