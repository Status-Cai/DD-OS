## DD-Linux OS

安装 DD 所需依赖：

Debian/Ubuntu:

`apt install -y xz-utils openssl gawk file wget`

CentOS:

`yum install -y xz openssl gawk file wget`

DD系统，root密码运行前有提示：

`wget --no-check-certificate -O installos.sh https://raw.githubusercontent.com/yang12me/DD-OS/main/installos.sh && bash installos.sh`

PS：只测试过 Debian10 和 Ubuntu18.04，Ubuntu20.04 几个版本

***

VPS 由于磁盘限制只要分出这三个分区就够了，下面的 DD 脚本，姥爷分出 /boot 200MB、 swap分出的为内存2倍、 其他分配到根分区。

声明一下，上面的 DD 脚本作者不是俺，俺只不过做了小小修改，分出适合大多 VPS 的分区。

原版会分出一个主分区和一个和内存大小相同的 swap 分区，俺就是以为对于小内存 VPS 这样分 swap 很不合理，所以才改了改，另新增一个 /boot 分区。

另，下面这个是原作者地址：

https://github.com/hiCasper/Shell
