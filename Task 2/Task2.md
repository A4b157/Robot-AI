# General
**Task: (Download ROS 2 “Robot Operating System” in Jetson Nano)**

# Algorithm to solve it: 
1-	Download and install [Xubuntu]( Xubuntu-20.04-l4t-32.3.1.tar.tbz2) which is combine of (XFCE and Ubuntu)
>“More information about difference between them in the [link](https://www.geeksforgeeks.org/difference-between-ubuntu-and-xubuntu/”)
 
2-	Download [Balena](https://www.balena.io/etcher/) or any software (to Flash Xubuntu image to SD card or USB)

3-	Download and install [ROS 2](https://docs.ros.org/en/dashing/Installation/Ubuntu-Development-Setup.html) 

**To download ROS, open the terminal and write some instruction found on the ROS website as follow:**

## System setup
### Set locale
Make sure you have a locale which supports UTF-8. If you are in a minimal environment (such as a docker container), the locale may be something minimal like POSIX. We test with the following settings. However, it should be fine if you’re using a different UTF-8 supported locale. 
```
locale  # check for UTF-8

sudo apt update && sudo apt install locales
sudo locale-gen en_US en_US.UTF-8
sudo update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8
export LANG=en_US.UTF-8

locale  # verify settings
```

### Add the ROS 2 apt repository
You will need to add the ROS 2 apt repositories to your system. To do so, first authorize our GPG key with apt like this:
```
sudo apt update && sudo apt install curl gnupg2 lsb-release
sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key  -o /usr/share/keyrings/ros-archive-keyring.gpg
```
