# Ubuntu

eclipse离线安装步骤

1、安装对应的JRE环境  
(1) 下载jdk文件压缩包：  
解压文件到对应的目录：tar zxvf jdk-8u121-linux-x64.tar.gz -C /opt  

(2) 打开 /etc/profile,打开指令：sudo vi /etc/profile，在文件的最后一行添加如下语句：  
export JAVA_HOME=/opt/jvm/jdk1.8.0_121  
export JRE_HOME=${JAVA_HOME}/jre  
export CLASSPATH=.:${JAVA_HOME}/lib:${JRE_HOME}/lib  
export PATH=${JAVA_HOME}/bin/:$PATH   

(3) 查看JDK是否安装成功   
先输入 source /etc/profile   
然后输入 java -version   
安装成功后会显示jdk版本   

2、安装eclipse  
（0）去eclipse官网下载合适的版本（Linux64位C/C++）：  
http://www.eclipse.org/downloads/eclipse-packages/  


(1) 解压eclipse到/opt文件夹下，指令为：  
sudo tar zxvf eclipse-inst-linux64.tar.gz -C /opt/  

(2) 创建eclipse桌面快捷图标  
首先输入指令： cd /usr/share/applications  
然后输入指令： sudo vim eclipse.desktop   
最后将下面的代码复制到文件中：   
[Desktop Entry]   
Encoding=UTF-8   
Name=Eclipse   
Comment=Eclipse   
Exec=/opt/eclipse/eclipse   
Icon=/opt/eclipse/icon.xpm   
Terminal=false   
StartupNotify=true    
Type=Application    
Categories=Application;Development;   
其中“Exec=”后面为eclipse安装目录下的eclipse程序的位置路径，“Icon=”后面为eclipse安装目录下的图标图片的路径 

(3) 将eclipse变为可执行文件  
指令为：sudo chmod u+x eclipse.desktop 

3、问题如下：
(1) 、打开eclipse出现A Java Runtime Environment (JRE) or Java Development Kit (JDK) must be ...会显示错误：  
解决方法：  
在终端进入你的eclipse目录，然后输入：  
mkdir jre  
cd jre  
ln -s /opt/jvm/jdk1.8.0_121/bin bin  
