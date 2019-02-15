# Ubuntu 16.04 Tensorflow Setup Guide
# Tensorflow GPU Linux Install
- Ubuntu 16.04 bootable usb stick
- Disable nouveau
`$sudo nano /etc/modprobe.d/blacklist-nouveau.conf`

With the text
```
blacklist nouveau
options nouveau modeset=0
```

Update ramfs
`sudo update-initramfs -u`

Check status with
`lsmod | grep nouveau` 

- Download and install Nvidia driver [Download Drivers | NVIDIA](https://www.nvidia.com/drivers)
	- change chmod +x of run file
	- `sudo init 3` to disable x server desktop
	- run and ignore warning
- Install python and pip and virtualenv
```
python3 --version
pip3 --version
virtualenv --version
```

```
sudo apt update
sudo apt install python3-pip
sudo pip3 install -U virtualenv  # system-wide install
```

```
virtualenv --system-site-packages -p python3 ./tfgpu
source ./tfgpu/bin/activate  # sh, bash, ksh, or zsh
pip install tensorflow-gpu
pip install keras
```
tensorflow-gpu                         1.1.0   
keras 2.0.8 
