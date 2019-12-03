## 简介

Kitsunebi 是一个全功能的 V2Ray 客户端，支持 SOCKS, Shadowsocks 和 VMess 代理协议，更可选择 TCP/KCP/WebSocket/HTTP(H2)/QUIC 作为代理传输协议。

**下载**

[iOS](https://apps.apple.com/app/apple-store/id1446584073) / [Android](https://play.google.com/store/apps/details?id=fun.kitsunebi.kitsunebi4android&hl=zh)

## 规则

| 版本 | 下载                                                         | 描述                           |
| ---- | ------------------------------------------------------------ | ------------------------------ |
| Air  | [点击复制](https://raw.githubusercontent.com/DivineEngine/Rules/core/Kitsunebi/Air.conf) | 出国轻量版，不带阻止规则       |
| Pro  | [点击复制](https://raw.githubusercontent.com/DivineEngine/Rules/core/Kitsunebi/Pro.conf) | 出国专业版                     |
| Back | [点击复制](https://raw.githubusercontent.com/DivineEngine/Rules/core/Kitsunebi/Back.conf) | 回国版，解锁流媒体及购物等服务 |

## 帮助

**官方文档**

- [Kitsunebi 使用常见问题](https://eycorsican.github.io/kits-faq/)
- [README](https://github.com/eycorsican/kitsunebi-android/blob/master/README.md)

**导入教程**

- [Kitsunebi 配置导入](https://www.notion.so/divineengine/Kitsunebi-f5f298d57a4c4ab88236f141a00524df)

### 说明

Kitsunebi 可以看作是 V2Ray-Core 的图形化界面客户端，也就是说一些功能的实现是取自于 V2Ray-Core（其不支持的 Kitsunebi 也不支持），那么常见的问题如为什么 Shadowsocks 不支持 rc4-md5 等协议，因为 V2Ray-Core 就没支持。

**iOS 与 Android 两个版本的差异性**

iOS 版因系统特性可以支持 User-Agent 规则，但 Android 版不行。

Android 版因系统特性支持分应用代理及正则表达式匹配，但 iOS 版不行。

*以上功能为 Kitsunebi 自行实现功能。*

**切勿与 Shadowrocket 规则混用**

Kitsunebi 解决 DNS 污染的办法是 V2Ray-Core 的 DNS 分流，即配置中的 `[DnsRule]`，这与 Shadowrocket 等应用中的 `force-remote-dns` 参数不同，使用 Shadowrocket 规则无法解决 DNS 污染问题。

**关于 `DnsClientIp`**

`DnsClientIp` 是给支持 [EDNS Client Subnet](https://developers.google.com/speed/public-dns/docs/ecs) 的 DNS 的一个客户端 IP（有助于获取更准确的 CDN 解析结果），故而可以自行修改成你所使用的运营商的省会 DNS 的 IP。设置成所在省会的 DNS IP 是最好的方式，解决家庭宽带每次重新拨号变更 IP 地址（反正都在同一城市或省份）