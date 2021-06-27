# Xpass2 - Xray 快速安装包

又一个 Xray 自动安装程序 [( English )](https://github.com/w30089/xpass2/blob/main/readme.md)

## 介绍

- 仅需要三分钟即可完成安装

- 自动请求 letsencrypt 证书，每月 1/16 日 自动更新

- 流量统计

- 网页版后台, 支持自定义路径


## 安装

> 注意

- 本安装程序支持 Linxu 系统，完美运行在 centos 7/8、 ubuntu 18/20， freebsd 等请自行测试

- 要求 Root 权限进行安装

> 安装

请将以下脚本贴到控制台运行

```
curl -L https://github.com/w30089/xpass2/releases/download/1.0.0/xpass2.tar.gz -o xpass2.tar.gz && tar xzvf xpass2.tar.gz && ./xpass2 install  
```

## 网页管理

当完成安装的时候，控制台将显示以下信息： 地址、密码

```
---- install successfully  ----

admin:  https://yourdomain.com/admin88888
passwd: 888888
```

> 网页端功能

- 客户端的连接信息

- 添加新用户、删除用户

- 暂停、恢复用户

- 重置用户流量

![](https://raw.githubusercontent.com/w30089/xpass2/main/image/web1.jpg)

![](https://raw.githubusercontent.com/w30089/xpass2/main/image/web2.jpg)

![](https://raw.githubusercontent.com/w30089/xpass2/main/image/web3.jpg)



## 控制台管理

输入 `xpass2` 获得使用菜单

终端提供更多的功能，相对网页版来说

![](https://raw.githubusercontent.com/w30089/xpass2/main/image/console.jpg)


###  用户
| command | function | params |
| --- | --- | --- |
| user | `list` `add ` `del` `url` `enable` `disable` | -e email |

#### [ add ]

> 添加一个用户，使用随机的 email 和 随机的 uuid

```
xpass2 user add
```
> 添加一个用户，使用指定 email 和 随机的 uuid

```
xpass2 user add -e xxxx@xxxx.com
```

> 添加一个用户，使用指定 email 和 指定的 uuid

```
xpass2 user add -e xxxx@xxxx.com -u 8b745d15-4e19-4b98-9a31-6eb3d4a3e550

```

#### [ url ]

> 显示一个用户的连接信息

```
xpass2 user url -e xxx@xxxx.com
```

> 快捷方法

```
xpass2 user xxx@xxxx.com
```

#### [ delete ]

```
xpass2 user del -e xxx@xxxx.com
xpass2 user delete -e xxx@xxxx.com
```

#### [ enable / disable / reset ]
```
xpass2 user enable -e xxx@xxxx.com
xpass2 user disable -e xxx@xxxx.com
xpass2 user reset -e xxx@xxxx.com
```

### 网页后台

| command | function |
| --- | --- |
| admin | `password` `folder`|

> 重置网页版后台密码

```
xpass2 admin password
```

请注意如果密码小于 6 位，将不被网页后台接受

> 修改网页管理的访问入口地址

```
xpass2 admin folder
```

### 域名

修改域名、更新证书

```
xpass2 domain
```

### 服务

> 启动 xpass2 服务

```
xpass2 start
```

> 关闭 xpass2 服务

```
xpass2 stop
```

### 卸载

```
xpass2 remove
```
