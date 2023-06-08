# NewBing_proxy

基于NewBing用Vue3和Go简单定制的NewBing镜像站，拥有一致的UI，支持ChatGPT提示词，国内可直接访问，基本兼容微软NewBing所有功能，无需登录即可试用，登录功能更多。原仓库[go-proxy-bing](https://github.com/adams549659584/go-proxy-bingai/blob).

## 功能
⭐ 支持现有开源 ChatGPT 提示词库

⭐ 需要画图等高级功能时(需选更有创造力模式或右上角 设置 => 图像创建 )，可登录微软账号设置用户 Cookie 进行体验

📢 遇到一切问题，先点左下角 ![新主题](https://github.com/adams549659584/go-proxy-bingai/raw/master/docs/img/bing-clear.png) 试试，不行使用刷新大法（Shift + F5 或 Ctrl + Shift + R 或 右上角设置中的一键重置），最终大招就 清理浏览器缓存 及 Cookie ，比如（24 小时限制、未登录提示等等）

## 网页展示

- 电脑端未登录状态

![电脑未登录](https://github.com/adams549659584/go-proxy-bingai/raw/master/docs/img/bing-nologin.png)

- 电脑端登录

![电脑端登录](https://github.com/adams549659584/go-proxy-bingai/raw/master/docs/img/bing-login-1.png)
![提示词1](https://github.com/adams549659584/go-proxy-bingai/raw/master/docs/img/bing-prompt-1.png)
![提示词2](https://github.com/adams549659584/go-proxy-bingai/raw/master/docs/img/bing-prompt-2.png)
![聊天服务器选择](https://github.com/adams549659584/go-proxy-bingai/raw/master/docs/img/bing-sydney-service-1.png)

- 电脑端画图

> 📢 需登录，并选择 更有创造力 对话模式

![电脑端画图](https://github.com/adams549659584/go-proxy-bingai/raw/master/docs/img/bing-draw.png)

- 手机端未登录状态

![手机端未登录](https://github.com/adams549659584/go-proxy-bingai/raw/master/docs/img/bing-m-nologin.png)

## 侧边栏

- 在 Edge 浏览器可把聊天和撰写分别添加侧边栏

![添加侧边栏](https://github.com/adams549659584/go-proxy-bingai/raw/master/docs/img/sidebar-add.png)

![聊天](https://github.com/adams549659584/go-proxy-bingai/raw/master/docs/img/sidebar-chat.png)

![撰写](https://github.com/adams549659584/go-proxy-bingai/raw/master/docs/img/sidebar-compose.png)

## 设置用户

- 访问 https://www.bing.com 或 https://cn.bing.com ，登录

- F12 或 Ctrl + Shift + I 打开控制台

- 拿到 Cookie 中 _U 的值 后，在网站设置 => 设置用户 中填入即可。

![获取Cookie](https://github.com/adams549659584/go-proxy-bingai/raw/master/docs/img/bing-cookie.png)

## 环境变量

```bash
# 运行端口 默认 8080 可选
PORT=8080
# Socks 环境变量 示例 可选
Go_Proxy_BingAI_SOCKS_URL=192.168.0.88:1070
# Socks 账号、密码 可选
Go_Proxy_BingAI_SOCKS_USER=xxx
Go_Proxy_BingAI_SOCKS_PWD=xxx
# 默认用户 Cookie 设置，可选，不推荐使用，固定前缀 Go_Proxy_BingAI_USER_TOKEN 可设置多个，未登录用户将随机使用，多人共用将很快触发图形验证，并很快达到该账号的24小时限制
Go_Proxy_BingAI_USER_TOKEN_1=xxx
Go_Proxy_BingAI_USER_TOKEN_2=xxx
Go_Proxy_BingAI_USER_TOKEN_3=xxx ...
# 简单授权认证密码，可选
Go_Proxy_BingAI_AUTH_KEY=xxx
```

## Render 部署

> ⭐ Render相对于Vercel的优点是支持WebSocket，不需要额外建立聊天服务器。

> 📢 需 https 域名 (自行配置 nginx 等) (前后端都有限制 只有在HTTPS的情况下，浏览器 Accept-Encoding 才会包含 br)

[![Deploy to Render](https://render.com/images/deploy-to-render-button.svg)](https://render.com/deploy?repo=https://github.com/JERRY-SYSTEM/NewBing_proxy)

![Render 一键部署](https://github.com/adams549659584/go-proxy-bingai/raw/master/docs/img/render-1.png)

![Render 域名](https://github.com/adams549659584/go-proxy-bingai/raw/master/docs/img/render-2.png)
