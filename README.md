##  N32905编译教程
<p align="right">Author:GGZ</p>

### 交叉编译工具
  使用工具为4.4.3的arm-linux-工具(非必须)
  
1. 解压工具压缩包：tar xvf toolschain.tar
2. 设置环境变量：. set_toolschain.sh
3. 检查是否可以使用交叉工具

### 编译内核
  进入路径$(path)/N32905_Linux_BSP
  
1. 解压文件系统：tar zxvf rootfs-2.6.35.tar.gz
2. cd linux-2.6.35.4_fa93
3. make w55fa93_defconfig
4. ./build (cd/spi/nand) 选择内核的启动方式

### 遇到的问题
1.运行./build时报错：<u>kernel/Makefile:138：kernel/timeconst.h] 错误 255</u>

**解决方法：修改kernel/timeconst.pl**
~~~
373：---if (!defined(@val)) {
373：+++if(defined(@val)) {
~~~
