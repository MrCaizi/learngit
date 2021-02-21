# learngit
用于学习GIT的使用

ubuntu 搭建samba共享方案
1.samba服务安装搭建
sudo apt-get install samba
sudo vim /etc/samba/smb.conf
workgroup = szsoft
设置用户密码登陆方式security=user
 
2.不需要用户密码登陆配置
[share]
path = /home/username/share
available=yes
browseable=yes
public=yes
writable=yes
create mask=0777
directory mask=0777
 
3.需要用户名密码登陆
[share]
path = /home/username/share
available=yes
browseable=yes
public=no
writable=yes
create mask=0777
directory mask=0777
valid users=username
保存，退出
sudo smbpasswd -a username 设置samba用户密码

5、启动、停止、重启Samba服务：

启动Samba服务器只需执行如下命令：
sudo /etc/init.d/samba start

关闭Samba服务器：
sudo /etc/init.d/samba stop

重启Samba服务

sudo /etc/init.d/smbd restart   或者  sudo service smbd restart 

注：修改了smb.conf配置文件，需要重启Samba服务才生效










