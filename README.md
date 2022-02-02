# 功能介绍
- 系统状态监控
- 支持多用户多协议，网页可视化操作
- 支持的协议：vmess、vless、trojan、shadowsocks、dokodemo-door、socks、http
- 支持配置更多传输配置
- 流量统计，限制流量，限制到期时间
- 可自定义 xray 配置模板
- 支持 https 访问面板（自备域名 + ssl 证书）
- 更多高级配置项，详见面板

# 安装&升级
```
bash <(curl -Ls https://raw.githubusercontent.com/womade/x-ui/main/install.sh)
```

## 手动安装&升级
1. 首先从 https://github.com/womade/x-ui/releases 下载最新的压缩包，一般选择`amd64`架构
2. 然后将这个压缩包上传到服务器的`/root/`目录下，并使用`root`用户登录服务器

> 如果你的服务器 cpu 架构不是`amd64`，自行将命令中的`amd64`替换为其他架构

```
cd /root/
rm x-ui/ /usr/local/x-ui/ /usr/bin/x-ui -rf
tar zxvf x-ui-linux-amd64.tar.gz
chmod +x x-ui/x-ui x-ui/bin/xray-linux-* x-ui/x-ui.sh
cp x-ui/x-ui.sh /usr/bin/x-ui
cp -f x-ui/x-ui.service /etc/systemd/system/
mv x-ui/ /usr/local/
systemctl daemon-reload
systemctl enable x-ui
systemctl restart x-ui
```

## 使用docker安装

>Build 自己的镜像
```shell
docker build -t x-ui .
```

## 建议系统
- CentOS 7+
- Ubuntu 16+
- Debian 8+
