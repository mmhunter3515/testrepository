# V2Ray教程: 安装和配置教学
V2Ray实际上是在Shadowsocks基础上革新出来的一个代理工具，它的性能虽然是基于Shadowsocks，但是却优于Shadowsocks，它将Shadowsocks功能当中的缺陷问题进行了弥补。同时加强了混淆协议的处理，让中国防火墙更难以墙到V2Ray，本文将对V2Ray进行具体的说明，其中包括[V2Ray节点的搭建](http://bit.ly/3NakH92)，以及如何使用一键安装脚本进行安装，此外还将对V2Rady节点优化以及V2Ray客户端软件的下载和设置等内容进行介绍。

## [第一部分：V2Ray简介]

很多人想要去V2Ray的官网了解V2Ray为何物，但是总会被官网上面的各种专业术语逼得完全看不下去，甚至失去了对V2Ray的兴趣，实际上我们对于V2Ray只要进行基础了解就完全够了。

### [V2Ray是什么？](http://bit.ly/37xEv6q)

简单地说，就是一个科学上完的工具，V2Ray和Shadowsocks性能类似，都是用于翻墙。

## V2Ray和Shadowsocks有什么区别?

由于种种原因，Shadowsocks的开发者被“喝茶”，所以和Shadowsocks有关的一切系统开发都停下来了，V2Ray就是在这个时候站起来了，他在前辈的基础上又加深了自己的性能，让自己的隐蔽性更高，让中国防火墙更难检测到。实际上，V2Ray就是Shadowsocks的升级版。

而这二者的相似点都在于，双方都没有商业公司提供技术支持，完全就是软件高手自己开发出来给大家使用的。

既然是在Shadowsocks的基础上进行的更新，V2Ray的功能自然是更加的强大，不仅改正了Shadowsocks的一些缺点，还进行了系统的更新化，让中国防火墙更难检测到它的存在，由于V2Ray还算是新星软件，所以很多人还不知道它的存在。就目前V2Ray还是在从事与电脑技术行业的工作者当中较为流行，由于V2Ray节点的搭建并不简单，需要涉及一定技术，所以很多人都会直接干脆选择VPN。

## 自己不会安装搭建V2Ray怎么办？

如果自己不会搭建V2Ray节点，但也想用V2Ray节点，那么就可以参考以下两种方案。

1. 用别人的V2Ray:  
    这个就很简单了，只要你有朋友愿意和你分享V2Ray账号，你们可以共同使用。
    
2. 购买V2Ray:  
    目前出售V2Ray的商家不多，在购买的时候一定要擦亮自己的双眼，千万不要被骗子给骗了。在这里可以推荐大家使用WannaFlix。
    
3. 改用VPN：  
    V2Ray和VPN一样都属于翻墙软件，它们只是科学上网的一个工具，如果你对于V2Ray的执念并没有那么深的话，就可以直接用VPN软件了。
    

### 1.ExpressVPN 评测（中文）

» 访问 ExpressVPN

(含三个月免费折扣)

### \# 2NordVPN 评测（中文）

» 访问 NordVPN

(含优惠折扣)

### \# 3PureVPN 评测（英文）

» 访问 PureVPN

(含优惠折扣)

\# 4VyprVPN 评测（中文）

» 访问 VyprVPN

## V2Ray翻墙系统的组成：

V2Ray翻墙系统由两大部分组成：

### V2Ray节点

节点的设立地点一定要是位于墙外（中国大陆以外）的VPS电脑服务器上搭建。

一个V2Ray节点（服务器）可以给多个用户一起使用，可以并联使用，不会影响彼此。

可以自己搭建V2Ray节点

### V2Ray客户端软件

直接用来使用V2Ray翻墙的软件，可以在不同的设备上使用：如电脑、手机等。

V2Ray客户端软件的下载是不需要花费任何的钱哦，如果遇到付费才可以下载的，就可以pass它。

## 自己搭建V2Ray节点所需条件：

首先你不能是一个电脑小白，如果你是电脑小白，也需要学会掌握基本的Linux系统操作指令：例如pwd、cd、ls、cp等，这些就相当于是建房子钱的地基了，没有了地基，自建的大楼是完全没有办法搭建的起来。

有能力的用户可以直接购买海外VPS服务器，这样就会更加的稳定，而且每月资费仅仅需要三十五元人民币。

英文语言能力：要能够明白产品页面的基础信息，如果不知道的话，可以借助于翻译软件，就是相对而言会麻烦点，毕竟有一些界面的单词是不可以复制粘贴翻译的，就需要自身手动输入。

付款：要有一张有贝宝账号的卡，少部分的公司支持支付宝的付款方式。

懂得怎样使用SSH方式连接VPS服务器：苹果电脑客户端用户可以使用MaciOS系统里面自带的终端Terminal，Windows用户就可以使用Putty或者乌班图。

## 第二部分：V2Ray节点的搭建和优化

### 1\. 购买墙外服务器（VPS）:

DigitalOcean、Vultr、搬瓦工、亚马逊都是海外较为常见的VPS供应商包括，以下将以DigitalOcean为例子为大家展开说明，目前新用户只要登录了[DigitalOcean](https://www.vpndada.com/go/digitalocean%22%20/t%20%22https://www.vpndada.com/v2ray-tutorial-cn/_blank)的官网，就可以获取优惠折扣。DigitalOcean的注册和购买账号的方式很简单，就和我们平时注册别的网站一样，如果还不清楚，就可以去网上搜索相关的教程。

### 2\. 创建虚拟主机VPS

完成购买服务器之后的下个步骤就是创建虚拟主机VPS。

在DigitalOcean的主界面上端会有”Create”，的字眼，点击进入就可以调到菜单当中，选择虚拟主机—–“Droplets”即可。

创建Droplet选项：

选择一个图片：选择配置下面的”乌班图”。

选择一个资费项目：当我们看到Starter的界面，就可以注意页面的最下方位置，选择最便宜的三十块钱一个月的就好了。

添加备份：正常情况是不需要。

添加存储卡：不需要。

选择服务器位置：这是很重要的，因为直接影响到你日后上网的速度，如果你要翻墙到海外，那么海外的节点一定要选择在亚洲海岸或是美国西海岸的服务器，目前推荐亚洲的节点是新加坡，美国的节点推荐选择圣佛朗西斯科。

选择其他选项：看个人的需求进行选择，需要还是不需要。

添加 SSH 的公钥（重要）：在这里添加自己用于SSH登录虚拟主机的公钥。

多少个虚拟主机? 不需要变动，选择一个就好了。

给虚拟主机取名字：看自己的喜好了，我是将主机命名为Siri。

虚拟主机创建好之后，你会看到主机的IP地址，这里的IP地址是很重要的，因为下一步的登录需要用到。

## 3\. 用SSH登录虚拟主机：

命令行基本是“ssh root@\[IP Address\]”。

连接好虚拟主机之后，先运行下面这个命令更新主机并下载相关软件：

apt-get update -y && apt-get install curl -y

## 4\. 一键安装V2Ray:

以Root身份连接到虚拟主机，然后运行以下命令：

bash <(curl -L -s https://install.direct/go.sh)

这个V2Ray一键安装脚本，在安装完毕V2Ray之后，还会将基本的配置都安置好，如果你没有别的需求，就直接可以上网使用了，每次系统重启后也会自动运行 V2Ray，非常的人性化且令人省心。

## 5\. 修改V2Ray配置：

V2Ray一键安装脚本会自动生成一个V2Ray配置文件，其配置文件的名为（/etc/v2ray/config.json），如果你要修改配置，就可以在这个程序的基础上进行编辑更改，具体的运行方式如下。

nano /etc/v2ray/config.json

下文会有关于连接节点的重要问题，读者需要多加注意。

用于后面使用软件V2Ray连接V2Ray节点：

Port指的是端口，ID那一行就是用户ID，alterID值得是额外的ID地址，ID的格式一定不能有变化，而有些参数是可以改动的。端口可以改变，用户可以改成445，额外ID和ID还是有区别的，额外ID是可以改动的。

当你对服务器配置修改完毕之后，就可以输入以下命令。从而重启V2Ray软件:

service v2ray restart

## 6\. V2Ray服务器端提速优化（可选项）：

当我们创建完毕之后，就可以开始进行优化V2Ray节点，让翻墙速度变得更快的选项了，毕竟没有人可以拒绝更快的网速。

## 安装谷歌 TCP BBR拥塞控制算法

这是我的朋友SUKI所用到的一键安装脚本，在输入所有命令之前，我们都需要以Root身份SSH连接主机，接着再运行。

wget –no-check-certificate https://github.com/teddysun/across/raw/master/bbr.sh && chmod +x bbr.sh && ./bbr.sh

当系统出现“按任意键”提示的时候，就可以直接点击回车键，系统就会开始自动安装。

在安装过程中有时候会弹出来几个选项窗口，用户直接点击回车键就可以，如果系统提示是否需要重启，你就看个人需要选择。

重启V2Ray的命令程序字眼:

service v2ray restart

当界面出现这个字眼的时候，就恭喜用户已经优化提速完成了，可以开启更快速的科学上网模式了。

下面来介绍一下V2Ray客户端的使用方法。

## 第三部分：V2Ray客户端的下载和配置

### V2Ray客户端软件下载：

- Windows电脑：[下载 V2RayN](https://github.com/2dust/v2rayN/releases%22%20/t%20%22https://www.vpndada.com/v2ray-tutorial-cn/_blank) (选择latest release，下载v2rayN-Core.zip形式的压缩包，安装到电脑之后就可以开始解压，并且运行其中的v2rayN.exe即可)
    
- 苹果系统电脑：[下载 V2RayX](https://github.com/Cenmrev/V2RayX/releases/%22%20/t%20%22https://www.vpndada.com/v2ray-tutorial-cn/_blank) (下载名为latest release.zip的压缩包就可，)
    
- 安卓手机/平板：[下载 V2RayNG](https://github.com/2dust/v2rayNG/releases/%22%20/t%20%22https://www.vpndada.com/v2ray-tutorial-cn/_blank) (下载latest release的app-universal-release.apk安装文件即可)
    
- 苹果手机/平板：这就简单了，直接买一个海外的账号，然后就可以在Apple store里面下载使用了。
    

### V2Ray客户端的基本配置：

因为V2Ray软件在每个系统平台上展示的界面都会有略微的差别，下面对于基础不会变的信息进行说明。

- Server（服务器地址）：所指的就是VPS虚拟主机的IP地址
    
- Port（端口）：在服务器配置文件config.json中可以找到
    
- ID（用户ID）：在服务器配置文件config.json中可以找到
    
- AlterID（额外ID）：在服务器配置文件config.json中可以找到
    
- Security（加密方式）：凭个人喜好来决定。
    

### V2Ray代理模式的设置：

V2Ray主要有两种代理模式：

- 全局模式：非常适合给大部分都是访问国外网站的用户使用，当你开启了这个选项知乎，电脑所有流量都走V2Ray代理，隐蔽性会更高。
    
- PAC模式（PAC）：可以定义谷歌浏览器翻墙，而火狐浏览器不翻墙，或是定义360浏览器不翻墙，这样就可以把流量端口岔开，然后上网更加的方便快捷，就不会出现，翻墙时候国外网站不好使的情况了。
    

希望阅读了此文的读者都可以学会自建V2Ray，一同通向科学上网之路
