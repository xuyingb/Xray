# 介绍

最好用的 Xray 一键安装脚本 & 管理脚本

# 特点

- 快速安装
- 无敌好用
- 零学习成本
- 自动化 TLS
- 简化所有流程
- 屏蔽 BT
- 屏蔽中国 IP
- 使用 API 操作
- 兼容 Xray 命令
- 强大的快捷参数
- 支持所有常用协议
- 一键添加 VLESS-REALITY (默认)
- 一键添加 VLESS-REALITY-Enc (一步到位启用 VLESS Encryption)
- 一键添加 Shadowsocks 2022 (已弃用，建议迁移至 VLESS Encryption)
- 一键添加 Hysteria2
- 一键添加 VMess-(TCP/mKCP)
- 一键添加 VMess-(WS/gRPC)-TLS
- 一键添加 VLESS-(WS/gRPC/XHTTP)-TLS
- 一键添加 VLESS-(WS/gRPC/XHTTP)-TLS-Enc (一步到位启用 VLESS Encryption)
- 一键添加 Trojan-(WS/gRPC)-TLS
- 一键添加 VMess-(TCP/mKCP) 动态端口
- 一键启用 BBR
- 一键更改伪装网站
- 一键更改 (端口/UUID/密码/域名/路径/加密方式/SNI/动态端口/等...)
- 一键启用/重新生成 VLESS Encryption
- 还有更多...

# 设计理念

设计理念为：**高效率，超快速，极易用**

脚本基于作者的自身使用需求，以 **多配置同时运行** 为核心设计

并且专门优化了，添加、更改、查看、删除、这四项常用功能

你只需要一条命令即可完成 添加、更改、查看、删除、等操作

例如，添加一个配置仅需不到 1 秒！瞬间完成添加！其他操作亦是如此！

脚本的参数非常高效率并且超级易用，请掌握参数的使用

# 文档

安装及使用：https://233boy.com/xray/xray-script/

# 帮助

使用：`xray help`

```
Xray script v1.33 by xuyingb
Usage: xray [options]... [args]...

基本:
   v, version                                      显示当前版本
   ip                                              返回当前主机的 IP
   pbk                                             同等于 xray x25519
   get-port                                        返回一个可用的端口
   ss2022                                          返回一个可用于 Shadowsocks 2022 的密码
   vlessenc                                        生成 VLESS Encryption 字符串 (服务端+客户端)

一般:
   a, add [protocol] [args... | auto]              添加配置
   c, change [name] [option] [args... | auto]      更改配置
   d, del [name]                                   删除配置**
   i, info [name]                                  查看配置
   qr [name]                                       二维码信息
   url [name]                                      URL 信息
   log                                             查看日志
   logerr                                          查看错误日志

更改:
   dp, dynamicport [name] [start | auto] [end]     更改动态端口
   full [name] [...]                               更改多个参数
   id [name] [uuid | auto]                         更改 UUID
   host [name] [domain]                            更改域名
   port [name] [port | auto]                       更改端口
   path [name] [path | auto]                       更改路径
   passwd [name] [password | auto]                 更改密码
   key [name] [Private key | atuo] [Public key]    更改密钥
   type [name] [type | auto]                       更改伪装类型
   method [name] [method | auto]                   更改加密方式
   sni [name] [ ip | domain]                       更改 serverName
   seed [name] [seed | auto]                       更改 mKCP seed
   new [name] [...]                                更改协议
   web [name] [domain]                             更改伪装网站
   vlessenc [name]                                 启用/重新生成 VLESS Encryption

进阶:
   dns [...]                                       设置 DNS
   dd, ddel [name...]                              删除多个配置**
   fix [name]                                      修复一个配置
   fix-all                                         修复全部配置
   fix-caddyfile                                   修复 Caddyfile
   fix-config.json                                 修复 config.json

管理:
   un, uninstall                                   卸载
   u, update [core | sh | dat | caddy] [ver]       更新
   U, update.sh                                    更新脚本
   s, status                                       运行状态
   start, stop, restart [caddy]                    启动, 停止, 重启
   t, test                                         测试运行
   reinstall                                       重装脚本

测试:
   client [name]                                   显示用于客户端 JSON, 仅供参考
   debug [name]                                    显示一些 debug 信息, 仅供参考
   gen [...]                                       同等于 add, 但只显示 JSON 内容, 不创建文件, 测试使用
   genc [name]                                     显示用于客户端部分 JSON, 仅供参考
   no-auto-tls [...]                               同等于 add, 但禁止自动配置 TLS, 可用于 *TLS 相关协议
   xapi [...]                                      同等于 xray api, 但 API 后端使用当前运行的 Xray 服务

其他:
   bbr                                             启用 BBR, 如果支持
   bin [...]                                       运行 Xray 命令, 例如: xray bin help
   api, x25519, tls, run, uuid, vlessenc [...]     兼容 Xray 命令
   h, help                                         显示此帮助界面

# 支持的协议

| 协议 | 支持 | 说明 |
|------|------|------|
| VLESS-REALITY | ✅ | 含 VLESS-REALITY-Enc (一步启用 Encryption) |
| VLESS-WS-TLS | ✅ | 含 VLESS-WS-TLS-Enc |
| VLESS-gRPC-TLS | ✅ | 含 VLESS-gRPC-TLS-Enc |
| VLESS-XHTTP-TLS | ✅ | 含 VLESS-XHTTP-TLS-Enc |
| VMess-TCP | ✅ | 含动态端口 |
| VMess-mKCP | ✅ | 含动态端口 |
| VMess-WS-TLS | ✅ | |
| VMess-gRPC-TLS | ✅ | |
| Trojan-WS-TLS | ✅ | |
| Trojan-gRPC-TLS | ✅ | |
| Shadowsocks | ✅ | 含 2022-blake3 (⚠️ 已被 Xray-core 标记为弃用) |
| Hysteria2 | ✅ | |
| Socks | ✅ | |

# 关于 Caddy（自动化 TLS）

脚本内置 Caddy 用于自动 TLS 证书管理，**按协议分工不同**：

## TLS 反向代理模式

适用于 **WS / gRPC / XHTTP** 类协议（VLESS、VMess、Trojan）：

```
用户 --TLS--> Caddy (443) --明文--> Xray (本地端口)
               ↑
        自动申请/续签 Let's Encrypt 证书
```

Caddy 监听 `443` 端口终止 TLS，将解密后的明文流量转发给 Xray。Xray **不接触证书**，也不需要处理 TLS 加解密。

## 仅签发证书模式

适用于 **Hysteria**：

```
Caddy (443) → respond "OK"（仅触发证书签发）
               ↓
        证书复制到 /etc/xray/ssl/
               ↓
Xray (自定义端口) → 加载证书，直接处理 TLS+QUIC
```

Hysteria 基于 QUIC 传输，Caddy 无法反向代理。脚本利用 Caddy 自动申请证书，复制到 `/etc/xray/ssl/` 目录供 Xray 加载。

## 不使用 Caddy 的协议

| 协议 | 原因 |
|------|------|
| **VLESS-REALITY** | 使用 REALITY 技术，不依赖证书 |
| **VMess-TCP / mKCP** | 不使用 TLS |
| **Shadowsocks** | 内置加密，不使用 TLS |
| **Socks** | 不使用 TLS |

# 新增功能

## VLESS Encryption

VLESS Encryption 为 VLESS 协议提供前向安全性 (Forward Secrecy) 和后量子安全加密。

两种使用方式：

```bash
# 方式一：一步到位添加（推荐）
xray add vws-enc              # VLESS-WS-TLS + 加密
xray add vgrpc-enc            # VLESS-gRPC-TLS + 加密
xray add vxhttp-enc           # VLESS-XHTTP-TLS + 加密
xray add r-enc                # VLESS-REALITY + 加密

# 方式二：为已有 VLESS 配置启用加密
xray change <name> vlessenc

# 查看加密字符串
xray vlessenc
```

## Hysteria2

Hysteria2 基于 QUIC 传输，提供高速度低延迟的代理能力。

```bash
xray add hy                            # 交互式添加
xray add hy example.com mypass 8443    # 命令行添加（域名 密码 端口）
```

TLS 证书由 Caddy 自动签发并复制到 `/etc/xray/ssl/`，无需手动操作。

## Shadowsocks 弃用警告

Xray-core 已将 Shadowsocks 标记为弃用 (缺乏 Forward Secrecy)，建议迁移至 VLESS Encryption。添加、查看或生成 Shadowsocks 配置时会显示弃用提示。

---

谨慎使用 del, ddel, 此选项会直接删除配置; 无需确认
反馈问题) https://github.com/xuyingb/Xray/issues
文档(doc) https://233boy.com/xray/xray-script/
```