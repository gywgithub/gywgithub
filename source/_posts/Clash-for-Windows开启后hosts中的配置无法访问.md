---
title: Clash for Windows开启后hosts中的配置无法访问
date: 2023-11-29 09:46:15
tags:
---




## 系统，软件版本

- Windows11
- Clash for Windows v0.20.3

## 遇到的问题


由于项目接口的独特设置，这个域名地址需要前端开发人员在本地 `hosts` 文件中进行配置，不然前端项目启动后接口无法正常访问，运行效果如下

![](https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/fc6ae562ad0348738f5a7530bfad5dda~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=1134&h=216&s=11075&e=png&b=1e1e1e)

在 `hosts` 中的配置如下

![](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/0cd1bb2164464f69a57283f45e3367a9~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=933&h=900&s=80008&e=png&b=f9f9f9)


不启动 `Clash` 的情况下，`a.t.nxin.com:80` 这个地址可以正常访问，开启了 `Clash` 后，运行的前端项目就无法访问了 

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/9ed92b3cf136467c981aedb838134adf~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=1624&h=802&s=46464&e=png&b=ffffff)

## 解决

打开 `Clash` 的 `Dashboard` 找到对应下图的对应位置 `Settings` > `System Proxy` > `Bypass Domin/IPNet` > `Edit`

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/76c98d69a4fe4198bad6d96bc0a5fe19~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=1327&h=731&s=76656&e=png&b=f3f3f3)

点击 `Edit` 修改配置，添加代理忽略的域名或 `ip`，添加 `a.t.nxin.com`, 点击右下角的保存按钮

![](https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/cac89e8bd4644b4ba69884e8dc374671~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=1327&h=731&s=67908&e=png&b=1e1e1e)

重启 `Clash` 后 `hosts` 中的配置的地址就自动忽略了