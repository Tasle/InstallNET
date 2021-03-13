**# 萌咖大佬的一键DD脚本**



**## 注意:**

全自动安装默认root密码:``` MoeClub.org ```,安装完成后请立即更改密码.



能够全自动重装Debian/Ubuntu/CentOS等系统.



同时提供dd安装镜像功能,例如: 全自动无救援dd安装windows系统



全自动安装CentOS时默认提供VNC功能,可使用VNC Viewer查看进度,



VNC端口为``` 1``` 或者``` 5901``` ,可自行尝试连接.(成功后VNC功能会消失.)



目前CentOS系统只支持任意版本重装为 CentOS 6.x 及以下版本.



特别注意:OpenVZ构架不适用.





**## 确保安装了所需软件:**



```

#Debian/Ubuntu:

apt-get install -y xz-utils openssl gawk file


#RedHat/CentOS:

yum install -y xz openssl gawk file

```



**## 如果出现了错误,请运行:**

``` 

#Debian/Ubuntu:

apt-get update


#RedHat/CentOS:

yum update

```



**## 快速使用示例:**

```  

bash <(wget --no-check-certificate -qO- 'https://moeclub.org/attachment/LinuxShell/InstallNET.sh') -d 8 -v 64 -a

```



**## 甲骨文使用示例(勿混合使用):**

``` 

bash <(wget --no-check-certificate -qO- 'https://moeclub.org/attachment/LinuxShell/InstallNET.sh') -d 10 -v 64 -p pasSw0rd -a -firmware

```



**## 下载及说明:**

``` 

wget --no-check-certificate -qO InstallNET.sh 'https://moeclub.org/attachment/LinuxShell/InstallNET.sh' && chmod +x InstallNET.sh

```

```

Usage:

​    bash InstallNET.sh   -d/--debian [dist-name]

​                -u/--ubuntu [dist-name]

​                -c/--centos [dist-version]

​                -v/--ver [32/i386|64/amd64]

​                -p

​                --ip-addr/--ip-gate/--ip-mask

​                -apt/-yum/--mirror

​                -dd/--image

​                -a/-m

 

# dist-name: 发行版本代号

# dist-version: 发行版本号

# -p: 自定义密码

# -apt/-yum/--mirror : 使用定义镜像

# -a/-m : 询问是否能进入VNC自行操作. -a 为不提示(一般用于全自动安装), -m 为提示.

```



**## 使用示例:**

```

#使用默认镜像全自动安装

bash InstallNET.sh -d 8 -v 64 -a

bash InstallNET.sh -d 9 -v 64 -a

bash InstallNET.sh -d 10 -v 64 -a

分别表示自动安装Debian 8x64 9x64 10x64

 

#使用自定义镜像全自动安装

bash InstallNET.sh -d 10 -v 64 -a --mirror 'http://mirrors.ustc.edu.cn/debian/' 

bash InstallNET.sh -c 6.9 -v 64 -a --mirror 'http://mirror.centos.org/centos'

 

# 以下示例中,将X.X.X.X替换为自己的网络参数.

# --ip-addr :IP Address/IP地址

# --ip-gate :Gateway  /网关

# --ip-mask :Netmask  /子网掩码

 

#使用自定义镜像自定义网络参数全自动安装

bash InstallNET.sh -u 16.04 -v 64 -a --ip-addr x.x.x.x --ip-gate x.x.x.x --ip-mask x.x.x.x --mirror 'http://archive.ubuntu.com/ubuntu'

 

#使用自定义网络参数全自动dd方式安装

bash InstallNET.sh --ip-addr x.x.x.x --ip-gate x.x.x.x --ip-mask x.x.x.x -dd 'https://moeclub.org/get-win7embx86-auto'

 

#使用自定义网络参数全自动dd方式安装存储在谷歌网盘中的镜像(调用文件ID的方式)

bash InstallNET.sh --ip-addr x.x.x.x --ip-gate x.x.x.x --ip-mask x.x.x.x -dd "$(echo "1cqVl2wSGx92UTdhOxU9pW3wJgmvZMT_J" |xargs -n1 bash <(wget --no-check-certificate -qO- 'https://moeclub.org/get-gdlink'))"

 

#使用自定义网络参数全自动dd方式安装存储在谷歌网盘中的镜像

bash InstallNET.sh --ip-addr x.x.x.x --ip-gate x.x.x.x --ip-mask x.x.x.x -dd "$(echo "https://drive.google.com/open?id=1cqVl2wSGx92UTdhOxU9pW3wJgmvZMT_J" |xargs -n1 bash <(wget --no-check-certificate -qO- 'https://moeclub.org/get-gdlink'))"

```



**## 常用示例:**

```

#重装为CentOS 6.9：

#以下命令中的 -c 后面为CentOS版本号，-v 后面为64位/32位，可根据需求进行替换。

#CentOS 6.9 64位：

bash <(wget --no-check-certificate -qO- 'https://moeclub.org/attachment/LinuxShell/InstallNET.sh') -c 6.9 -v 64 -a



#重装为Debian：

#以下命令中的 -d 后面为Debian版本号，-v 后面为64位/32位，可根据需求进行替换。

#Debian 9 64位：

bash <(wget --no-check-certificate -qO- 'https://moeclub.org/attachment/LinuxShell/InstallNET.sh') -d 9 -v 64 -a



#重装为Ubuntu：

#以下命令中的 -u 后面为Ubuntu版本号，-v 后面为64位/32位，可根据需求进行替换。

# Ubuntu 12.04 64位：

bash <(wget --no-check-certificate -qO- 'https://moeclub.org/attachment/LinuxShell/InstallNET.sh') -u 12.04 -v 64 -a


# Ubuntu 14.04 64位：

bash <(wget --no-check-certificate -qO- 'https://moeclub.org/attachment/LinuxShell/InstallNET.sh') -u 14.04 -v 64 -a


# Ubuntu 16.04 64位：

bash <(wget --no-check-certificate -qO- 'https://moeclub.org/attachment/LinuxShell/InstallNET.sh') -u 16.04 -v 64 -a


# Ubuntu 18.04 64位：

bash <(wget --no-check-certificate -qO- 'https://moeclub.org/attachment/LinuxShell/InstallNET.sh') -u 18.04 -v 64 -a

```



耐心等待系统安装成功后，出于安全考虑，建议立即输入：```passwd root```  更改默认密码:``` MoeClub.org ```





**## 一些可用镜像地址:**

```

# 推荐使用带有 /GoogleDrive/<File_ID> 链接, 速度更快.

# 当然也可以使用自己GoogleDrive中储存的镜像,使用方式:

 https://image.moeclub.org/GoogleDrive/<File_ID>

 
# win7emb_x86.tar.gz:

 https://image.moeclub.org/GoogleDrive/1srhylymTjYS-Ky8uLw4R6LCWfAo1F3s7 

 https://image.moeclub.org/win7emb_x86.tar.gz


# win8.1emb_x64.tar.gz:

 https://image.moeclub.org/GoogleDrive/1cqVl2wSGx92UTdhOxU9pW3wJgmvZMT_J

 https://image.moeclub.org/win8.1emb_x64.tar.gz

```



**## 一些提示:**



特别注意:



萌咖提供的dd安装镜像



远程登陆账号为: ```Administrator```



远程登陆密码为: ```Vicer```



仅修改了主机名,可放心使用.(建议自己制作.)



在dd安装系统镜像时:



在你的机器上全新安装,如果你有VNC,可以看到全部过程.



在dd安装镜像的过程中,不会走进度条(进度条一直显示为0%).完成后将会自动重启.



分区界面标题一般显示为: “Starting up the partitioner“





**### GD直连获取方法**

1.下载脚本

```

wget -N --no-check-certificate https://raw.githubusercontent.com/veip007/DDWIN/master/gdlink.sh && chmod +x gdlink.sh && ./gdlink.sh

```

2.使用方法

```

#Work with share link/使用分享链接方式

gdlink 'https://drive.google.com/open?id=0B8SvBXZ3I5QMcUduTMJEanRkMzQ'



#Work with file id/使用文件ID方式

gdlink '0B8SvBXZ3I5QMcUduTMJEanRkMzQ'

 

#download with share link/使用分享链接方式直接使用wget下载链接

##可将其中./download改成自己需要的文件名或文件绝对路径

gdlink 'https://drive.google.com/open?id=0B8SvBXZ3I5QMcUduTMJEanRkMzQ' |xargs -n1 wget -c -O ./download

```



转载于萌咖https://moeclub.org/2018/04/03/603/



**# 甲骨文VNC连接**

**## 一、准备密钥**

首先准备一台`Linux系统的VPS`用于转发及认证VNC，在SSH中执行`ssh-keygen`，生成当前系统的公钥及私钥；所有的选项默认即可，这里为了方便用不着设置密码，毕竟不是作为公开使用的。在生成完成后将`/root/.ssh/`目录下`id_rsa.pub`保存下来，`cat .ssh/id_rsa.pub`将其中的公钥内容复制下来。

<img src="https://github.com/Tasle/InstallNET/blob/main/IMG/1.png?raw=true" alt="1.png" style="zoom: 85%;" />

**## 二、设置VNC**

进入甲骨文的控制台，打开实例的面板，在左下角找到`控制台连接`，点击`创建控制台连接`。

<img src="https://github.com/Tasle/InstallNET/blob/main/IMG/2.png?raw=true" alt="img" style="zoom: 38%;" />

选择粘贴SSH密钥，将刚才复制的`id_rsa.pub`中的公钥内容粘贴进去，或者直接把`.pub`上传上去也可以。

<img src="https://github.com/Tasle/InstallNET/blob/main/IMG/3.png?raw=true" alt="img" style="zoom:43%;" />

创建好后，选择菜单中的`复制Linux/Mac的VNC连接`，将复制出来的内容粘贴在文本编辑器中。

<img src="https://github.com/Tasle/InstallNET/blob/main/IMG/4.png?raw=true" alt="img" style="zoom:35%;" />

**## 三、开启VNC**

在编辑器中，将先前导出的VNC连接配置文件中的监听地址`localhost:5900`改为`10.0.8.7:9988`(`ip address`)，监听地址也可以是`ifconfig`获取到的本机网卡IP，如果提示未安装输入`apt install net-tools`。

`（注意：如果你是独立IP，（非NAT映射时）请使用 0.0.0.0 ，阿里云，腾讯云等均使用 NAT映射，因此监听为映射的内网IP，例如：10.0.8.7）`

<img src="https://github.com/Tasle/InstallNET/blob/main/IMG/5.png?raw=true" alt="img" style="zoom:45%;" />

随后你可以选择直接复制到ssh的console去执行，也可以放进一个`.sh`脚本中执行，效果是相同的；执行后可以看到由于是导出公钥的VPS，首次连接两次确认的询问直接输入`yes`即可，无需你指定私钥即可通过系统的私钥完成认证。

<img src="https://github.com/Tasle/InstallNET/blob/main/IMG/6.png?raw=true" alt="img" style="zoom:52%;" />

最后在安全组及VPS的防火墙上放行9988端口，检测到端口已被占用后即可。

**## 四、连接VNC**

前往RealVNC的网站上下载VNC Connect这个软件（[点击前往](https://www.realvnc.com/en/connect/download/viewer/windows/)），支持的平台很多，亦或者其他的VNC工具都是可以的。

在软件中直接输入你的Linux VPS的`IP:5900`，回车即可开始连接。

<img src="C:\Users\Athony\Desktop\萌咖重装\img\7.png" alt="img" style="zoom:50%;" />

其中的不安全报错直接忽略即可，随后可以看到VNC的窗口已正常打开。