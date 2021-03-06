# Xpass2 - Xray quick install package 

Another automatic installation for xray server. [( 中文 )](https://github.com/w30089/xpass2/blob/main/readme-cn.md)

## Introduce

- Only need 3 minutes to finished installation

- Automatic request for letsencrypt certificates, update automaticly 1/16 per month

- Transfer counting

- Web admin manager, support customerize admin path


## Install

> Notice

Support for Linux system , run on centos 7/8 and ubuntu 18/20 perfectly.

> Install 

<font color="red">Root Permission Required!</font>

```
curl -L https://github.com/w30089/xpass2/releases/download/1.0.0/xpass2.tar.gz -o xpass2.tar.gz && tar xzvf xpass2.tar.gz && ./xpass2 install  
```

## Web admin manager

When finished the intallation, terminal will show content like:

```
---- install successfully  ----

admin:  https://yourdomain.com/admin88888
passwd: 888888
```

> Web admin funtions:

- Show user connect messages.

- Add a new user.

- Enable / Disable user.

- Reset user traffic.


![](https://raw.githubusercontent.com/w30089/xpass2/main/image/web1.jpg)

![](https://raw.githubusercontent.com/w30089/xpass2/main/image/web2.jpg)

![](https://raw.githubusercontent.com/w30089/xpass2/main/image/web3.jpg)


## Terminal manager

Type `xpass2` for usage menu.

Terminal suppor more functions than web admin manager

![](https://raw.githubusercontent.com/w30089/xpass2/main/image/console.jpg)

###  User
| command | function | params |
| --- | --- | --- |
| user | `list` `add ` `del` `url` `enable` `disable` | -e email |

#### [ add ]

> add a new user with random email and random uuid

```
xpass2 user add
```
> add a new user with email and random uuid

```
xpass2 user add -e xxxx@xxxx.com
```

> add a new user with email and uuid

```
xpass2 user add -e xxxx@xxxx.com -u 8b745d15-4e19-4b98-9a31-6eb3d4a3e550

```

#### [ url ]

> show connect link (by email)

```
xpass2 user url -e xxx@xxxx.com
```

> quickly way

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

### Admin

| command | function |
| --- | --- |
| admin | `password` `folder`|

> reset web admin password.

```
xpass2 admin password
```
please note: password less 6 length, cann't be accepted by web program

> change web admin visiable folder name.

```
xpass2 admin folder
```

### Domain

Change domain name or certificate.

```
xpass2 domain
```


### Service

> start

```
xpass2 start
```

> stop

```
xpass2 stop
```

### Uninstall

```
xpass2 remove
```
