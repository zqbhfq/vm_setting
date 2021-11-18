# 虚拟机初始配置
- 设置root密码   
`sudo passwd root`
- 修改登陆名  
`sudo vim /etc/passwd`  
![image](https://user-images.githubusercontent.com/82703975/142400976-7d9ec26b-3c90-4a17-9caa-3cf3dd9f14c5.png)
- 安装openssh-server ; sshd服务默认启动，查看  
`apt install openssh-server`  
`ps -ef |grep sshd`  
- 更改镜像源  
https://blog.csdn.net/laoluobo76/article/details/108302191

