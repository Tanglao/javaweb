j
ava线上问题排查常见命令

1、top命令：Linux命令。可以查看实时的内存使用情况。

2、jmap -histo:live [pid]，然后分析具体的对象数目和占用内存大小，从而定位代码。

3、jmap -dump:live,format=b,file=xxx.hprof [pid]，然后利用MAT工具分析是否存在内存泄漏等等。

java进程 cpu100% 内存泄露分析

进入服务器，top 命令看一下，发现进程6633占用了800%

   \[root@3server ~\]\# top  java应用直接 ps -ef \| grep java

   2.把进程的栈dump到文件里，以便后面的分析

   \[root@3server ~\]\# jstack 6633 &gt; cpu1128.log 

   3.看看这个进程里面哪些线程在占用cpu 

   \[root@3server ~\]\# top -p 6633 -H 

   一大片占用cpu很高的线程，选一个最高的吧，PID=5159 

   4.接着要看刚才dump出来的cpu日志了，里面会有6633这个进程下面每个线程的栈信息，但是是十六进制显示的，所以先把5159转换成16进制 

   \[root@3server ~\]\# printf %0x 5159 

   \[root@3server ~\]\# 1427 

   5.在cpu日志里找PID=1427的线程 

   \[root@3server ~\]\# vi cpu1128.log
find . -mtime +30 -name "portal.log*" -exec mv {} ~/bi-portal-logs/logtemp \;

{} 即找到的文件

du -sh * 查看当前目录文件大小

df -lh 查看磁盘空间大小

次数统计grep -o 'item general' | wc -l打印jvm 参数

sudo -iu appops

jinfo -flags pid

如果报jvm版本不一致，则修改当前java_home为对应pid的java_home

当前用户目录创建.bash_profile

export JAVA_HOME = 路径

export PATH = $JAVA_HOME/bin:$PATH

export CLASSPATH=.:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar

source .bash_profile

查看端tcp口使用情况netstat -tln | grep 8186

grep -A 5 可以显示匹配内容以及后面的5行内容

grep -B 5 可以显示匹配内容以及前面的5行内容

grep -C 5 可以显示匹配内容以及前后面的5行内容

mvn:

mvn dependency:tree -Dverbose -Dincludes=asm:asm

scp hztangzhilong@hzaxs-haitao-pre2:/home/appops/kaola-jxc-pre/pre2/tomcat-haitao-dw-Ins1/logs/catalina_2017-05-24.log ~/dwpre.log

tar zxvf file.tgz -C /folder

pssh -h ~/.ssh/pssh/jstorm2ip_port -i command ls /home/appops/jstorm/conf | grep -B 10 'config.properties'

pssh -P -h ip.txt 'chmod u+x /usr/local/shell/passlog.sh'