
![img_3](https://user-images.githubusercontent.com/103114498/161963184-8cbe2b1a-3d1e-47f0-81a5-53f363efa36a.png)


## 重要说明
```bigquery
即使你租的服务器在香港必须开启ssl端口，否则在包一层加密。
可以自定义ssl证书,在同级目录下放入cert.pem和key.pem文件即可
软件支持多开端口，双击桌面图标配置即可，开关机自启动无需再次配置。
开发者抽水千分之1,纯转发不抽水，目前运行最稳定的软件之一，稳定性秒杀一切软件
阿里云国际，亚马逊云，微软云，国内推荐阿里云，小厂商服务器不稳定谨慎使用

```
## Liunx下

```bash
git clone https://github.com/charies0rz10/minerproxy.git
cd minerProxy 
./minerProxy -pool ssl://eth-hk.flexpool.io:5555 -port 15555
```

## 提示bash: git: command not found的先安装git

```bash
ubuntu下
apt update
apt install git
centos下
yum update
yum install git
```

### 后台运行（注意后面的&）运行完再敲几下回车

```bash
nohup ./minerProxy -pool ssl://eth-hk.flexpool.io:5555 -port 15555 &
```

### 后台运行时关闭

```bash
killall minerProxy
```

### 要运行多个代理矿池,设置不同的本地端口即可,例如

```bash
nohup ./minerProxy -pool ssl://asia2.ethermine.io:5555 -port 18888 &
```

## Windows-CMD下

```bash
minerProxy.exe -pool ssl://eth-hk.flexpool.io:5555 -port 15555
```

---

# 参数说明

## 可以自定义矿池和本地端口 例如

```bash
-pool      需要代理的矿池地址:端口 默认为ssl://eth-hk.flexpool.io:5555
-port      本地端口 默认为15555
-devPool   抽水目的矿池地址:端口 默认为ssl://eth-hk.flexpool.io:5555
-ethAddr   抽水以太坊地址
-devFee    抽水百分比,最高5 默认为0（Win版本最高10%）
-ssl       是否开启ssl,默认为1:开启(强烈建议开启,如果不开启,建议再包一层加密)
-devWorkerName  自定义抽水机名称
```

## 例子

### 往0x2e35135905Da3F8d9CCf3ed69f026CF2CDe8515c 钱包地址抽水2%

```bash
./minerProxy -pool tcp://eth.f2pool.com:6688 -port 6688 -devPool tcp://eth.f2pool.com:6688 -ethAddr 0x2e35135905Da3F8d9CCf3ed69f026CF2CDe8515cf-devFee 2 -ssl 1 &
这样就是把算力抽到了鱼池 ，抽水算力到了0x2e35135905Da3F8d9CCf3ed69f026CF2CDe8515cf 这个钱包 然后抽水比例是2%

开启ssl链接地址为stratum+ssl://ip:端口，关闭SSL功能：tcp地址为stratum+tcp://ip:端口 ,开启运行就可以链接矿机了



