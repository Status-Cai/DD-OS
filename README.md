## DD-Linux OS
支持 CentOS、Ubuntu、Debian 几种发行版。

DD系统，root密码运行前有提示：

`wget --no-check-certificate https://git.io/installos.sh && bash installos.sh`

***

VPS 由于磁盘限制，分出了 /boot， /swap，和根分区，三个分区。分出 /boot 200MB、 swap 分出的为内存2倍、 其它分配到根分区。

脚本是根据下面项目小小修改的，分出适合大多 VPS 的分区。

下面项目会分出一个主分区和一个和内存大小相同的 swap 分区，俺就是以为对于小内存 VPS 这样分 swap 很不合理，所以才改了改，另新增一个 /boot 分区。

另，下面这个是原作者地址：

https://github.com/hiCasper/Shell
