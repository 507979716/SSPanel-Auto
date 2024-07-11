# SSPanel-AutoCheckin
实现SSPanel框架搭建的平台流量自动签到功能,windows,mac,linux 都可以使用

## 相关说明 
适用于使用 SSPanel 用户管理面板搭建的网站，网站页面底部会有 Powered by SSPANEL 字段
支持一日多次签到
支持推送签到信息到微信


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
下载运行包 https://github.com/linabellbiu/SSPanel-AutoCheckin/releases
## mac,linux

```shell
./SSPanel-AutoCheckin -d=https://www.onesy.cc/ -e=xxx@gmail.com -p=123456 -C
```
## Windows
```shell
./SSPanel-AutoCheckin.exe -d=https://www.onesy.cc/ -e=xxx@gmail.com -p=123456 -C
```

## 如果运行在国内,请求访问失败可能需要配置科学上网
```shell
./SSPanel-AutoCheckin.exe -d=https://www.onesy.cc/ -e=xxx@gmail.com -p=123456 -t=http://127.0.0.1:7890 -s=https://127.0.0.1:7890 -C
```