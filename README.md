# DD-OS

## 安装 DD 所需依赖：

Debian/Ubuntu:

apt install -y xz-utils openssl gawk file wget


CentOS:

yum install -y xz openssl gawk file wget


DD系统，root密码运行前有提示：

wget --no-check-certificate -O installos.sh https://starts.sh/cloud/docs/79installos.sh && bash installos.sh

PS：只测试过 Debian10 和 Ubuntu18.04，Ubuntu20.04 几个版本



#dd #linux #swap
Linux小硬盘分区，比如 VPS 上的分区

一般 VPS 上的硬盘也就20，30GB的大小，所以不用分多个分区。

1、根分区
根分区就是 / 分区，所有的东西都在这个分区内。

2、/boot分区
这个分区包含了操作系统的内核和在启动系统过程中所要用到的文件，建这个分区是有必要的，因为目前大多数的pc机要受到 BIOS 的限制，况且如果有了一个单独的/boot启动分区，即时主要的根分区出现了问题，计算机依然能够启动。这个分区的大小约在 60MB—200MB 之间。

3、/swap分区
swap分区是交换分区，是一定磁盘空间（分区或文件），用于将部分内存中的数据换下来，以腾出内存空间用于其他需求。在一个系统中，物理内存快使用完时，操作系统会使用交换分区。当系统内存紧张时，操作系统根据一定的算法规则，将一部分最近没使用的内存页面保存到交换分区，从而为需要内存的程序留出足够的内存空间；在 swap 中的内存页面被访问时，系统会将其重新载入到物理内存中去运行。

swap分区大小：
4GB以内的物理内存，swap 设置为内存的2倍
4-8G的物理内存，swap 等于内存大小
8-64G的物理内存，swap 设置为8G

VPS 由于磁盘限制只要分出这三个分区就够了，下面的 DD 脚本，姥爷分出 /boot 200MB、 swap分出的为内存2倍、 其他分配到根分区。

声明一下，下面的 DD 脚本作者不是俺，俺只不过做了小小修改，分出适合大多 VPS 的分区。

原版会分出一个主分区和一个和内存大小相同的 swap 分区，俺就是以为对于小内存 VPS 这样分 swap 很不合理，所以才改了改，另新增一个 /boot 分区。


PS：只测试过 Debian10 和 Ubuntu18.04，Ubuntu20.04 几个版本




另，下面这个是原作者的版本：

apt install -y xz-utils openssl gawk file wget

wget --no-check-certificate -O AutoReinstall.sh https://git.io/AutoReinstall.sh && bash AutoReinstall.sh
