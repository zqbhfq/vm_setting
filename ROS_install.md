[安装ROS系统](http://wiki.ros.org/noetic/Installation/Ubuntu)
## step1: 设置镜像仓库（清华源）

- 踩坑1  

![image](https://user-images.githubusercontent.com/82703975/142416900-cf6c2bc7-c51a-4e21-9b96-2233b4b81ba5.png)  
解决方法：将镜像源地址https 改为http  
```
# 默认注释了源码镜像以提高 apt update 速度，如有需要可自行取消注释
deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal main restricted universe multiverse
# deb-src http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal main restricted universe multiverse
deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-updates main restricted universe multiverse
# deb-src http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-updates main restricted universe multiverse
deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-backports main restricted universe multiverse
# deb-src http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-backports main restricted universe multiverse
deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-security main restricted universe multiverse
# deb-src http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-security main restricted universe multiverse

# 预发布软件源，不建议启用
# deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-proposed main restricted universe multiverse
# deb-src http://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-proposed main restricted universe multiverse
```
更新 `sudo apt-get update`  
## step2: 公钥
- 踩坑2： keyserver 不可用    
解决方法：使用清华镜像源帮助文档的keyserver
```
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
sudo apt-key adv --keyserver 'hkp://keyserver.ubuntu.com:80' --recv-key C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654
```
## step3: 安装ROS
前面没问题这边就没问题了
```
sudo apt update
sudo apt install ros-noetic-desktop-full
```
## step4: 设置环境
```
source /opt/ros/noetic/setup.bash
echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
source ~/.bashrc
```
## step5: 安装依赖包
`sudo apt install python3-rosdep python3-rosinstall python3-rosinstall-generator python3-wstool build-essential`  

