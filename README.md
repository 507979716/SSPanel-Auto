# SSPanel-AutoCheckin
实现SSPanel框架搭建的平台流量自动签到功能,windows,mac,linux 都可以使用

## 相关说明 
适用于使用 SSPanel 用户管理面板搭建的网站，网站页面底部会有 `Powered by SSPANEL` 字段  
登录页面张这个样子

<img src=".github/img2.png" width="300">

# 参数
```
Usage:
  SSPanel-AutoCheckin [OPTIONS]

Application Options:
  -h, --host=       需要访问的域名 例如: http://wwww.xxx.com
  -e, --email=      账户名,注册的邮箱账号
  -p, --passwd=     密码,注册的密码
  -r, --remember=   登录的请求参数 (default: week)
  -n, --tryCount=   请求失败重试次数 (default: 3)
  -t, --httpProxy=  设置http代理 例如:http://127.0.0.1:7890
  -s, --httpsProxy= 设置https代理 例如:https://127.0.0.1:7890
  -C, --cron        设置每天定时执行,只用在本地执行,如果是放在github action中要关闭这个选项.
                    每天的执行时间: 1 0 0 * * *

```
# 使用方式

## 推荐使用github action 每天自动运行,无需执行环境,简单快速0成本
1. fork 仓库代码到自己仓库
2. 把email和passwd添加到仓库的`secrets`中,[使用指南](https://docs.github.com/zh/actions/security-guides/using-secrets-in-github-actions#creating-secrets-for-a-repository)  

   <img src=".github/img.png" width="600">  

3. 手动开启 Actions，执行一次工作流。(因为 Github 默认 Fork 后的项目 Github Actions 处于关闭状态)


## mac,linux
### [下载可执行文件](https://github.com/linabellbiu/SSPanel-AutoCheckin/releases)

```shell
./SSPanel-AutoCheckin -d=https://www.xxxx.com/ -e=xxx@gmail.com -p=123456 -C
```
## Windows
```shell
./SSPanel-AutoCheckin.exe -d=https://www.xxx.com/ -e=xxx@gmail.com -p=123456 -C
```

## 如果运行在国内,请求访问失败可能需要配置科学上网
```shell
./SSPanel-AutoCheckin.exe -d=https://www.xxx.com/ -e=xxx@gmail.com -p=123456 -t=http://127.0.0.1:7890 -s=https://127.0.0.1:7890 -C
```