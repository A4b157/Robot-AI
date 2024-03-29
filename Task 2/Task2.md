# General
**Task: (Download ROS 2 “Robot Operating System” in Jetson Nano)**

# Algorithm to solve it: 
1-	Download and install [Xubuntu]( Xubuntu-20.04-l4t-32.3.1.tar.tbz2) which is combine of (XFCE and Ubuntu)
>“More information about difference between them in the [link](https://www.geeksforgeeks.org/difference-between-ubuntu-and-xubuntu/”)
 
2-	Download [Balena](https://www.balena.io/etcher/) or any software (to Flash Xubuntu image to SD card or USB)

3-	Download and install [ROS 2](https://docs.ros.org/en/foxy/Installation/Ubuntu-Install-Debians.html) 

**To download ROS, open the terminal and write some instruction found on the ROS website as follow:**

## Install Ros2 
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
### Setup Sources
You will need to add the ROS 2 apt repositories to your system. First, make sure that the Ubuntu Universe repository is enabled by checking the output of this command.
```
apt-cache policy | grep universe
```

This should output a line like the one below:
```
500 http://us.archive.ubuntu.com/ubuntu focal/universe amd64 Packages
    release v=20.04,o=Ubuntu,a=focal,n=focal,l=Ubuntu,c=universe,b=amd64
```

If you don’t see an output line like the one above, then enable the Universe repository with these instructions.
```
sudo apt install software-properties-common
sudo add-apt-repository universe
```

Now add the ROS 2 apt repository to your system.
```
sudo apt update && sudo apt install curl gnupg2 lsb-release
sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key  -o /usr/share/keyrings/ros-archive-keyring.gpg
```

Then add the repository to your sources list.
```
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(source /etc/os-release && echo $UBUNTU_CODENAME) main" | sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null
```

### Install ROS 2 packages

Update your apt repository caches after setting up the repositories.
```
sudo apt update
```

ROS 2 packages are built on frequently updated Ubuntu systems. It is always recommended that you ensure your system is up to date before installing new packages.
```
sudo apt upgrade
```

Desktop Install (Recommended): ROS, RViz, demos, tutorials.
```
sudo apt install ros-foxy-desktop
```

ROS-Base Install (Bare Bones): Communication libraries, message packages, command line tools. No GUI tools.
```
sudo apt install ros-foxy-ros-base
```



### Environment setup
Set up your environment by sourcing the following file.
```
source /opt/ros/foxy/setup.bash
```

### Try some examples 
In one terminal, source the setup file and then run a C++ talker:
```
source /opt/ros/foxy/setup.bash
ros2 run demo_nodes_cpp talker
```

In another terminal source the setup file and then run a Python listener:
```
source /opt/ros/foxy/setup.bash
ros2 run demo_nodes_py listener
```
you should see the talker saying that it’s Publishing messages and the listener saying I heard those messages. This verifies both the C++ and Python APIs are working properly. 


