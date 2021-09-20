# multi-v2ray
a tool to manage v2ray/xray config json, support multiple user && group manage  

## Features

- Support Xray manage, different commands (v2ray/xray) enter different core management
- V2ray && Iptables Traffic Statistics
- Command line to manage
- Multiple user && port manage
- Cloudcflare cdn mode
- Support pure ipv6 VPS
- Support Docker
- Dynamic port
- Ban bittorrent
- Range port
- TcpFastOpen
- Vmess/VLESS/Socks5/MTproto share link
- Support protocol modify:
  - TCP
  - Fake http
  - WebSocket
  - mkcp
  - mKCP + srtp
  - mKCP + utp
  - mKCP + wechat-video
  - mKCP + dtls
  - mKCP + wireguard
  - HTTP/2
  - Socks5
  - MTProto
  - Shadowsocks
  - Quic
  - VLESS_TCP
  - VLESS_TLS
  - VLESS_WS
  - VLESS_XTLS
  - Trojan

## How To Use
new install
```
sudo apt update && apt upgrade -y && git clone https://github.com/MalinrRuwan/multi-v2ray.git && cd multi-v2ray && bash v2ray.sh
```

keep profile to update
```
sudo git clone https://github.com/MalinrRuwan/multi-v2ray.git && cd multi-v2ray && bash v2ray.sh -k
```

uninstall
```
sudo git clone https://github.com/MalinrRuwan/multi-v2ray.git && cd multi-v2ray && bash v2ray.sh --remove
```

## Command Line
```bash
v2ray/xray [-h|help] [options]
    -h, help             get help
    -v, version          get version
    xray                 get xray panel
    v2ray                get v2ray panel
    start                start V2Ray
    stop                 stop V2Ray
    restart              restart V2Ray
    status               check V2Ray status
    new                  create new json profile
    update               update v2ray to latest
    update [version]     update v2ray to special version
    update.sh            update multi-v2ray to latest
    add                  add new group
    add [protocol]       create special protocol, random new port
    del                  delete port group
    info                 check v2ray profile
    port                 modify port
    tls                  modify tls
    tfo                  modify tcpFastOpen
    stream               modify protocol
    cdn                  cdn mode
    stats                v2ray traffic statistics
    iptables             iptables traffic statistics
    clean                clean v2ray log
    log                  check v2ray log
    rm                   uninstall core
```

## Docker Run
default will create random port + random header(srtp | wechat-video | utp | dtls) kcp profile(**if use xray replace image to MalinrRuwan/xray**)  
```
docker run -d --name v2ray --privileged --restart always --network host MalinrRuwan/v2ray
```

custom v2ray config.json:
```
docker run -d --name v2ray --privileged -v /path/config.json:/etc/v2ray/config.json --restart always --network host MalinrRuwan/v2ray
```

check v2ray profile:
```
docker exec v2ray bash -c "v2ray info"
```

**warning**: if u run with centos, u should close firewall first
```
systemctl stop firewalld.service
systemctl disable firewalld.service
```

## Dependent
pip: https://pypi.org/project/v2ray-util/  
python3: https://github.com/MalinrRuwan/python3-install  
acme: https://github.com/Neilpang/acme.sh

## Special Credits
> [Jrohy](https://github.com/Jrohy)