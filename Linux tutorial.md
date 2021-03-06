[TOC]

#Linux 常用命令#

##(1)linux命令。

###1)启动Shell。
Ctrl+Alt+t
普通用户“$”，root用户是“#”。

###2)命令的格式。
命令名 [-选项]...[参数]...


##(2)目录操作基本命令。

###1)ls命令。
列出当前目录下的所有内容。  
ls [选项] [文件名或目录名]  
选项：  

* -s：显示每个文件的大小。
* -S：按文件的大小排序。
* -a：显示目录中所有文件，包括隐藏文件。
* -l：使用长列表格式，显示文件详细信息。
* -t：按文件修改的时间排序。
* -F：显示文件类型描述符。

不同的颜色代表的含义：  

* 默认色：普通文件。
* 绿色：可执行文件。
* 红色：tar包文件。
* 蓝色：目录。
* 水红色：图像。
* 青色：链接文件。
* 黄色：设备文件。

ls -l的解读：  

* 第一部分：d代表目录，l代表链接文件，b代表设备文件。后面是文件所有者/文件所有
者所在的用户组/其他用户的权限。
* 第二部分：当前目录下的隐藏文件+普通文件的数目的和。
* 第三部分：文件所有者。
* 第四部分：文件所有者所在的用户组。
* 第五部分：文件的大小，单位是B（字节）。
* 第六部分：修改日期。
* 第七部分：文件（目录）名。

###2)cd命令。
转换用户所在的目录。  
cd [路径名]  
没个文件都存在一条从跟目录（/）开始的路径。特殊用法举例：  

* .：代表当前目录。
* ..：代表上层目录。
* ~：代表当前用户的宿主目录。
* ~用户名：代表进入~后用户的宿主目录。
* -：代表前一目录。

###3)pwd命令。
显示当前工作目录的绝对路径。  
pwd

###4)mkdir命令。
创建一个新目录。make directory。  
mkdir [选项] 目录名  
选项：  

* -m权限：设置存取权限。如777,744,755等。
* -p：递归创建目录。

###5)rmdir命令。
删除一个空目录。  
rmdir [选项] 目录名  
-p代表递归删除多级目录。


##(3)文件操作基本命令。

###1)touch命令。
创建文件。存在则保留原先的，不存在则创建一个空文件，无格式，大小为0。  
touch 文件名

###2)cat命令。
**用法一：显示某文件的内容。**  
cat [选项] [文件名]...  
选项：  

* -a：显示所有字符。
* -n：编号。
* -b：编号除了空行。
* -s：压缩多行空行为一行。  

**用法二：重复刚刚输入的内容，即显示标准输入。**  
cat  
按Ctrl+D结束。  
**用法三：制作一个新文件。使用重导向。**  
cat > 新文件  
把键盘输入的内容重导向输入到新文件中(并覆盖原有内容）。按Ctrl+D结束输入。  
**用法四：合并文件。**  
cat 文件名1 文件名2 ... > 文件名3  
文件名3中按文件名1到文件名2的顺序排列。  
**用法五：给文件追加内容。**  
cat 文件名2 ... >> 文件名1

###3)cp命令。
实现文件的复制。  
cp [选项] <源文件> <目标>  
选项：-i表示安全询问的方式复制。  
目标可以是目标路径，也可以是目标路径下的文件名。

###4)rm命令。
删除指定的文件。  
rm [选项] [文件名或目录名] ...  
选项：  

* -i：安全询问。
* -r或-R：递归处理。
* -f：强制删除文件或目录。
* -v：显示指令执行过程。
* -d：直接把欲删除的目录的硬连接数据删成0,删除该目录。

###5)mv命令。
move，移动文件，“剪切+复制”。  
mv [文件名] [路径名]  
路径名可以包含新的文件名，实现重命名。

###6)chmod命令。
change modify修改文件的权限和文件的属性。  
chomd [<文件使用者>+/-/=/<权限类型>] 文件名1 文件名2...  
**文件使用者有4种类型，可以采用其中一个或者它们的组合。**  

* u：user（文件主）。
* g：group，文件主所在的用户组。
* o：other。
* a：all。

**操作符包括3种类型。**  

* +：增加权限。
* -：删除权限，取消权限。
* =：赋予给定的权限并取消其他权限。

**权限类型包括3种基本类型。**  

* r：只读权限。
* w：写权限。
* x：可执行权限。

**chomd命令中选项的几种常用组合。**  

* a+rw：为所有用户增加读写权限。
* a-rwx：
* g+w：
* o+rwx：
* ug+r：
* g=rx：

##(4)文件处理命令。

###1)grep命令。
在指定的文件中查找某个字符串。  
grep [选项] 关键字 文件名  
选项：-i表示不区分大小写。  
grep命令的执行结果是显示含有要查找的字符串的每一行原文。

###2)head命令。
查看文件的开头部分的内容。  
head [number] 文件名  
选项指定要显示的行数，默认显示10行。

###3)tail命令。
查看文件的结尾部分。  
tail [number] 文件名  
与head类似。

###4)wc命令。
对文件的行数/单词数/字符数进行统计。  
wc [选项] 文件名  
选项：  

* -l：line，行数。
* -w：word，单词数。
* -m：字符数。

###5)sort命令。
对文件或者查询结果进行排序。  
sort [选项] 文件名  
选项：  

* -f：忽略大小写。
* -t：指定分隔符。
* -r：反向排序。
* -i：只考虑可以打印的字符，忽略任何非显示字符。

默认从小到大排序。

###6)find命令。
查找文件或目录。  
find 文件名（或目录名）  
find查找目录时，会把目录下的内容也显示出来。

###7)which命令。
在PATH变量所规定的路径查找相应的命令，并现实和绝对路径。  
which 命令名  
选项：-a表示显示所有匹配结果，默认只显示第一个匹配结果。  
echo "$PATH"可以用来显示PATH变量。

###8)whereis命令。
可以查询命令，还能查出ubuntu数据库里记载的文件，而且数度很快。  
whereis [选项] 文件名或命令名  
选项：  

* -b：只查找二进制文件。
* -w：只查找说明文件在manual路径下的文件。

###9)locate命令。
找出所有与被查询文件名相同的文件。  
locate 文件名  
也是从数据库里查找。


##(5)压缩备份基本命令。

###1)bzip2命令和bunzip2命令。
bzip2是压缩命令。  
bzip2 文件名1 [文件名2] ...  
压缩完成后原文件消失，生成.bz2后缀的文件，且只能用bunzip2命令才能解压。  
bunzip2是解压命令。  
bunzip2 文件名1 [文件名2] ...

###2)gzip命令。
压缩解压。  
gzip [选项] 文件名 ...  
选项：  

* -d：解压。
* -n：指定压缩级别。n的范围时候1~9。

默认是压缩文件，只能对.gz后缀的文件进行解压。

###3)unzip命令。
解压.zip文件。  
upzip [选项] 文件名.zip  
选项：  

* -d：将文件解压到指定目录。
* -n：不覆盖原文件。
* -v：查看文件目录列表但不解压。
* -o：以默认方式覆盖已经存在的文件。

举例：  

* unzip file.zip
* unzip -v file.zip
* unzip -n file.zip -d /home/ubuntu/yasuo

###4)zcat命令和bzcat命令
都是用于查看压缩文件内容的。  
zcat 文件名  
bzcat 文件名  
zcat用于.gz后缀的压缩文件，而bzcat用于.bz2后缀的压缩文件。

###5)tar命令。
对文件或目录进行打包或解包。  
tar [选项] [备份包的文件名] [要打包的（或解包）的文件或目录名]  
选项：  

* -c：create，创建新的打包文件。
* -x：抽取.tar文件里的内容。文件不会消失。
* -z：打包后直接用gzip命令进行压缩，或者进行解压。
* -j：打包后直接用bzip2命令进行压缩，或者进行解压。
* -t：查看一个打包文件里的文件目录。
* -f：使用文件或设备。
* -v：在打包压缩或解包解压后将文件的详细清单列出来。

举例：  

* tar -cf filename.tar file1 file2 file3
* tar -tf filename.tar
* tar -xf filename.tar

***无论如何，似乎必须要有-f参数后跟一个.tar后缀名的文件才能执行。***

##(6)磁盘操作命令。

###1)mount命令。
挂载。  
mount [-t vfstype] [-o 选项] device dir  
选项：  

* [-t vfstype]：用于指定文件系统类型，通常不用指定。vfstype中的哥哥选项：
    * -iso9660：光盘或光盘镜像。
    * -ntfs：Windows NT NTFS文件系统。
    * -msdoc：DOS FAT16文件系统。
    * -smbfs：Mount Windows文件网络共享。
    * -vfat：Windows 9x FAT32文件系统。
    * -nfs：UNIX(Linux)文件网络共享。
* [-o 选项]：主要用来描述设备或文档的挂接方式。常用的选项有：
    * -loop：用来把一个文件当成硬盘分区挂接到系统上。
    * -iocharset：指定访问文件系统所用的字符集。
    * -ro：采用只读方式挂接设备。
    * -device：要挂接的设备。
    * -rw：采用读写方式挂接设备。
    * -dir：设备在系统上的挂接点。
 
 
举例：  

*挂接U盘。
    * fdisk -l
    * mkdir -p /mnt/usb
    * mount -t vfat /dev/sdd1 /mnt/usb
* 挂载光盘镜像文件。
    * cp /dev/cdrom /home/sunky/mydisk.iso || dd if=/dev/cdrom of=/home/sunky/mydisk.iso
    * mkisofs -r -J -V mydisk -o /home/sunky/mydisk/mydisk.iso /home/sunky/mydir
    * mkdir /mnt/vcdrom
    * mount -o loop -t iso9660 /home/sunky/mydisk.iso /mnt/vcdrom
* 挂接移动硬盘(Linux中，USB接口的移动硬盘也被当作SCSI设备对待）。
    * fdisk -l || more /proc/partitions
    * 接好移动硬盘
    * fdisk -l || more /proc/partitions
    * mkdir -p /mnt/usbhd1 && mkdir -p /mnt/usbhd2
    * mount -t ntfs /dev/sdc1/ /mnt/usbhd1 && mount -t vfat /dev/sdc5 /mnt/usbhd2

***NTFS格式的磁盘分区用-t ntfs，fat32格式的磁盘分区用-t vfat。***
***如果汉字显示乱码，可以加上-o iocharset=cp936选项。***

###2)umount命令。
卸载一个文件系统。它的使用权限是超级用户或/etc/fstab中允许的使用者。  
umount <挂载点|设备>  
umount是mount的逆操作，参数和使用方法与mount类似。

###3)df命令。
查看当前硬盘的分区信息。  
df [选项]  
选项：  

* -a：列出所有情况。
* -i：列出i-nodes的使用量
* -k：分区大小以KB显示。
* -h：以MB或GB显示。
* -t：列出某一个文件系统的所有分区的磁盘使用量。
* -x：某个分区以外的其他分区的所有分区的磁盘使用量。
* -t：列出每个分区所属的文件系统的名称。

举例：  

* df -ah

###4)du命令。
查看当前目录下所有文件和目录的信息。  
du [选项]  
选项：  

* -a：列出所有文件及目录的大小。
* -h：以MB或GB显示。
* -b：以B为单位。
* -c：加上总计。
* -s：只列出各文件大小的总和。
* -x：只计算同一个文件系统中的文件。

举例：  

* du -ab

###5)fsck命令。
硬盘检测，仅root用户执行。  
fsck 分区名  
举例：  

* fsck /dev/sda1


##（7)关机重启命令。

###1)shutdown命令。
安全关机。  
shutdown [选项] [time] [警告信息]  
选项：  

* -h：将系统服务停掉后安全关机。
* -k：不真正关机，只是发出警告信息。
* -r：将系统服务停掉然后重启。
* -t：在规定的时间后关机。

举例：  

* 两分钟后关机
  shutdown -h +2
* 22:00准时关机
  shutdown -h 22:00
* 让系统1分钟后重启，并发出通知
  shutdown -r +1 "system will be reboot after 1 minuter."

###2)halt命令。
停掉系统服务然后关机。相当于shutdown -h 。  
halt [选项]  
选项：  

* -f：强制关机。

###3)poweroff命令。
关机。  
poweroff

###4)reboot命令。
重启。  
reboot

###5)init命令。
切换Ubuntu的运行级别。  
init [运行级别]  
选项：  

* -0：关机。
* -1：
* -2：
* -3：
* -4：
* -5：
* -6：重启。


##(8)其他常用命令

###1)echo命令。
显示命令行中的字符串。主要用于输出提示信息。  
echo [选项] [字符串]  
选项：  

* -n：不换行。

###2)more命令和less命令。
对文件内容或查询结果分屏显示。  
more [options] 文件名  
less [options] 文件名  
more命令选项：  

* -p：不滚屏，清屏。
* +n：从第n行开始显示。
* -s：压缩连续空行为一行。

举例：
* more 文件名
* cat 文件名 | more
* less 文件名

###3)help命令和man命令
显示某个命令的格式用法。  
help 命令名（似乎应该改为 命令名 --help）  
man 命令名

###4)cal命令。
显示日历。  
cal [选项 [月份 [年份]]]  
选项：  

* -m：monday，以星期一为每周的第一天的方式显示。
* -y：显示今年年历。
* -j：以凯撒历显示，即以一月一日起的天数显示。

举例：  

* cal 5 2000
* ncal -My
* cal -jy

不带参数则显示当月的月历。

###5)date命令。
显示及设定系统的日期和时间。



#进程管理与系统监控

##(1)进程管理

###1)什么是进程

**1. 进程的概念**
进程就是程序的一次运行过程。

**2. 进程的特征**  

* 动态性
* 并发性
* 独立性
* 异步性
* 结构性

**3. 进程的基本状态及其转换**  

* 就绪状态。
* 执行状态。
* 阻塞状态。

**4. 进程控制块**
* 进程控制块的作用。进程控制块是为了描述和控制进程而定义的一个数据结构。系统创建进程实际上就是给程序设置一个PCB，用于对进程进行控制和管理。进程任务结束时，系统收回PCB，进程消亡。系统将根据某PCB而感知相应进程的存在，故说PCB是进程存在的唯一标识。  

* 进程控制块中的内容。
    * 描述信息。
        * 进程标识符
        * 家族关系
    * 现场信息。
        * 现行状态
        * 现场保留区
        * 程序和数据地址
    * 控制及资源管理信息。
        * 进程的优先级
        * 互斥与同步机制
        * 资源清单
        * 链接字

###2)进程的启动
前台启动和后台启动。  

**1. 前台方式启动**  
终端输入Linux命令，回车执行启动进程。按Ctrl+Z挂起，ps命令查看进程。  
下面是ps命令的用法  
【功能】查看进程的信息。  
【格式】  
ps [选项]  
【选项】  

* -e：显示所有进程。
* -a：显示所有终端下的所有进程。
* -f：以全格式显示。
* -u：以用户格式显示。
* -r：只显示正在运行的进程。
* -x：显示所有不控制终端的进程。
* -o：以用户定义的格式显示。

【说明】  
(1)默认只显示本终端上运行的进程。  
(2)没有指定格式则采用默认格式：PID/TTY/TIME/CMD。  

* PID：进程标识号。
* TTY：进程对应的终端，表示该进程不占用终端。
* TIME：进程累计使用的CPU的时间。
* CMD：执行进程的命令名。

(3)指定-f选项时，以全格式显示。  

* UID：进程属主的用户名。
* PPID：父进程的标识号。
* C：进程最近使用的CPU时间。
* STIME：进程开始时间。

(4)指定u选项时，以用户格式显示。  

* USER：同UID。
* %CPU：进程占用CPU的时间与进程总运行时间的比。
* %MEM：进程占用的内存与总内存之比。
* VSZ：进程虚拟内存大小，以KB为单位。
* RSS：进程占用实际内存大小，以KB为单位。
* STAT：进程的状态。
* START：同STIME。
* COMMAND：同CMD。

其余同上。  
【举例】
* vi story
* ps
* ps -f

**2. 后台启动**  
【举例】  

* vi story&
* ps

###3)进程的调度

**1. 改变进程优先级**
通常，用户进程的优先级是相同的，但是可以通过命令来改变某些进程的优先级。  
(1)查看进程优先级的命令。  
ps -l  
PRI和NI两个字段与进程优先级有关。PRI是实际的进程优先级，NI会影响到实际的进程  
先级。  
(2)改变进程优先级的命令。  
【功能】在启动时指定请求执行进程优先级。  
【格式】  
nice [选项] 命令  
【选项】常用的是-n，n值就是NI的值，n值的范围为-20~19。n值越大优先级越高。  
【说明】默认情况下，只有root用户才能提高请求进程的优先级，普通用户只能降低。  
【举例】  

* nice -13 vi&

(3)renice命令。  
【功能】在进程执行时改变NI值。  
【格式】  
renice [+/-n] [-g 命令名...] [-p 进程标识码...] [-u 进程所有者...]  
【说明】可以通过命令名/进程标识码/进程所有者指定要该变的进程的NI值。  
【举例】  

* renice +10 -p 1769
* renice -6 -p 1769
* ps -l

**2. 挂起和激活进程**  
挂起前台进程可用Ctrl+Z来实现。激活被挂起的进程，可才有两种方式。  
(1)fg命令。  
【功能】使挂起的进程返回前台运行。  
【格式】  
fg [参数]  
【参数】n，数字n代表进程序号。可通过jobs命令查看程序号。  
【举例】  

* vi one&
* vi two&
* vi three&
* fg
* fg 2
* jobs
* fg 1

fg默认打开最新挂起的jobs，如果加了程序号则打开相应的job。  
(2)bg命令。  
【功能】激活被挂起的进程，使其在后台运行。  
【格式】  
bg [参数]  
【参数】n，数字n代表进程号。  
【举例】  

* find / -name hello.c
* Ctrl+Z
* vi story
* bg 1
* fg 2

**3. 终止进程**  
(1)Ctrl+C 。  
(2)kill命令。  
【功能】中止进程。  
【格式】  
kill [-信号] PID  
【说明】  
可以用kill -l查看信号。  
【举例】
* kill -9 1965

【说明】9信号码对应的信号是SIGKILL，杀死进程。

###4)进程的监视
top会定期更新显示内容，默认根据CPU的负载多少进行排序。  
top命令。  
【功能】监视系统进程。  
【格式】  
top [-选项]  
【选项】  

* c：显示整个命令行。
* d：指定时间间隔。默认3s。
* i：不显示僵死或闲置进程。
* n：指定每秒内监控信息的更新次数。
* p：进程标识码列表。
* s：使top命令在安全模式下运行。
* S：使用累计模式。

进程交互说明：  
s
* h或者?：


##(2)系统日志

###1)日志文件简介。
通常情况下，只有管理员才拥有读取和修改日志文件的权限。

###2)常用的日志文件。

