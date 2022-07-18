# General
**Task: (Download ROS “Robot Operating System” in your device)**

**Problem:**  *My Operating System is Windows 10 and from ROS organization website found that “ROS is currently not supported on Windows, but it is possible to run parts of ROS on Windows.”*

# Algorithm to solve it:

1-	Download and install Virtual box to use Lennix operating system 

2-	Download and install [Ubuntu 20.04.4 LTS (Focal Fossa)](https://releases.ubuntu.com/20.04/)

3-	Download and install [ROS 1 (Noetic Ninjemys)](http://wiki.ros.org/Installation/Ubuntu) 


 **To download ROS, firstly setup ubuntu, then open the terminal and write some instruction found on the ROS website as follow:**
 
 ## Install Ros 1 
 ### 1-	Setup your computer to accept software from packages.ros.org.
 
 ``` 
 sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
```

### 2-	Set up your keys

```
• sudo apt install curl # if you haven't already installed curl
• curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
```

### 3-	make sure Debian package index is up-to-date:

```
sudo apt update
```

### 4-	Desktop-Full Install: (Recommended) : Everything in Desktop plus 2D/3D simulators and 2D/3D perception packages 

```
sudo apt install ros-noetic-desktop-full
```

### 5-	Environment setup
You must source this script in every bash terminal you use ROS in.
```
source /opt/ros/noetic/setup.bash
```
Write the following code once to avoid repeating the previous step in every terminal
```
echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
source ~/.bashrc
```

### 6-	Install package 
There are even more packages available in ROS. You can always install a specific package directly
```
sudo apt install ros-noetic-PACKAGE
```
To find available packages
```
apt search ros-noetic
```

