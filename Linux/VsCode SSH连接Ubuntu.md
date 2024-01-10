# VsCode SSH连接Ubuntu

## 1.下载官方插件`Remote - SSH`

<img src="https://img2024.cnblogs.com/blog/2282419/202401/2282419-20240110171808922-557747491.png" style="zoom:80%;" />

## 2.虚拟机查看ip地址

```bash
ip addr 
```

![](https://img2024.cnblogs.com/blog/2282419/202401/2282419-20240110172436945-1721989739.png)

## 3.配置config文件

![](https://img2024.cnblogs.com/blog/2282419/202401/2282419-20240110171820903-688299260.png)

![](https://img2024.cnblogs.com/blog/2282419/202401/2282419-20240110173443138-1416790043.png)

# 连接失败

> 过程试图写入的管道不存在。

<img src="https://img2024.cnblogs.com/blog/2282419/202401/2282419-20240110164841160-103097879.png" alt="问题" style="zoom:80%;" />

## **解决**

1. 重启ubuntu

```bash
reboot
```

2. 修改设置，将网络连接方式**NAT**  ➡  **桥接网卡**

![](https://img2024.cnblogs.com/blog/2282419/202401/2282419-20240110164907337-547334316.png)

![解决](https://img2024.cnblogs.com/blog/2282419/202401/2282419-20240110164901647-143788934.png)

3. 如果Ubuntu ip地址是`10.0.*.*`，设法将ip地址变为`192.168.*.*`

# 连接成功

![](https://img2024.cnblogs.com/blog/2282419/202401/2282419-20240110171226291-675895185.png)

## 免密连接
1. 在Windows打开命令提示符
```bash
ssh-keygen -t rsa -b 4096  # 生成密钥
cd C:\Users\29608/.ssh/  # 跳转到.ssh目录
```
2. 在Ubuntu中打开终端
```bash
mkdir .ssh # 创建.ssh目录
cd .ssh # 跳转到.ssh目录
```
3. 在Windows命令提示符中输入
```bash
#采用scp命令传输密钥 scp id_rsa.pub username@your ip address:.ssh/.
scp id_rsa.pub dzx@*.*.*.*:.ssh/.
```
4. 在Ubuntu终端中输入
```bash
cat id_rsa.pub >> authorized_keys
```