# passwall plus  

[![GitHub release](https://img.shields.io/github/release/yiguihai/luci-app-passwall-plus.svg)](https://github.com/yiguihai/luci-app-passwall-plus/releases/latest)
[![GitHub downloads](https://img.shields.io/github/downloads/yiguihai/luci-app-passwall-plus/latest/total.svg)](https://github.com/yiguihai/luci-app-passwall-plus/releases/latest)
[![Compile IPK Package](https://github.com/yiguihai/luci-app-passwall-plus/workflows/Compile%20IPK%20Package/badge.svg)](https://github.com/yiguihai/luci-app-passwall-plus/actions)  

这是一个简陋的项目，个人精力与学习能力有限仍然有许多的不足之处。目前仅用于测试使用。已经实现:

- 默认直连，撞墙自动切换服务器(调节"等待时间"设置实现)
- 多线服务器转发负载均衡
- 按域名分流解决版权问题
- 自动选择最优线路(本地路由)
- 自动选择最优dns返回(本地路由)
    
使用了以下开源项目
    
1. [ipt2socks](https://github.com/zfl9/ipt2socks) 透明代理   
2. [TcpRoute2](https://github.com/GameXG/TcpRoute2) 代理流量转发器   
3. [SmartDNS](https://github.com/pymumu/smartdns) 防止dns污染  

云编译默认使用了[bcm53xx-generic](https://downloads.openwrt.org/snapshots/targets/bcm53xx/generic/)的工具链

必须包含有一组国外dns像8.8.8.8，主要是针对运营商返回 127.0.0.1 的污染，如 rfa.org jav321.com 和域名黑名单等功能。  
其它的推荐添加使用运营商的dns服务  
目前发现raw.githubusercontent.com恶毒的返回0.0.0.0污染，已经添加到默认配置文件屏蔽。

仅处理tcp流量，不会造成udp走代理出现的卡顿。目前发现谷歌市场无法下载是因为走了udp和tcp的5228端口流量。等待tcproute2支持udp代理转发解决

## 计划
* ~~增加自动编译ipk包~~  
* ~~透明代理替换成ipt2socks~~  
* ~~开启运行时自动修改dns劫持流量到smartdns来处理~~
* 添加Shadowsocks-libev与Obfs混淆插件
* 添加Tor暗网访问功能
* ~~优化Makefile文件代码~~
### 预览图
<img src="https://github.com/yiguihai/luci-app-passwall/raw/master/view/1.jpg" alt="展示图" title="查看图片" />
<img src="https://github.com/yiguihai/luci-app-passwall/raw/master/view/2.png" alt="展示图" title="查看图片" />
