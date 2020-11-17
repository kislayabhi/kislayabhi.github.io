---
layout: post
title: Installing CUDA 7.5 with Ubuntu 16.04 or Ubuntu 14.04
published: true
comments: true
categories: Tech
---

Hey Guys. I have spent days if not months installing CUDA 7.0 and CUDA 7.5 in Ubuntu 14.04 and Ubuntu 16.04 over different laptops(Dell and Asus). I finally got them working. While there are numerous tutorials present over the web, most are incomplete and error prone. The difficulty comes in installing the Nvidia drivers. If one does a mistake then the system crashes(since you need Nvidia drivers for Cuda only but not for graphics display. The default settings messes the OpenGL display drivers) and you need to do a fresh install (again there are many messy ways to escape without a fresh install but lets try to make it correct from the start anyways).

Instructions on Ubuntu 16.04/14.04 after a fresh install

(1.) Install build essentials.

```sh
$ sudo apt-get install build-essential
```

(2.) Go to <https://developer.nvidia.com/cuda-downloads> and download CUDA toolkit 7.5 for Ubuntu 15.04 (No Version supports 16.04 yet) or if you are on Ubuntu 14.04, just choose that. I have tested the 64 bit version but I think the 32 bit will work too if your machine is 32 bit.

(3.) Open up a terminal and extract the separate installers via:

```sh
$ mkdir ~/Downloads/nvidia_installers;
$ cd ~/Downloads
$ ./cuda_7.5.18_linux.run -extract=~/Downloads/nvidia_installers;
```

(4.) Completely uninstall anything in the ubuntu repositories with `nvidia-*`. I used synaptic and did a purge, AKA completely uninstall programs and configuration.

```sh
$ sudo apt-get --purge remove nvidia-*
```

(5.) No need to create an xorg.conf file. If you have one, remove it (assuming you have a fresh OS install).

```sh
$ sudo rm /etc/X11/xorg.conf
```

(6.) Create the `/etc/modprobe.d/blacklist-nouveau.conf` file with the 2 following lines:

```
blacklist nouveau
options nouveau modeset=0
```

Then do a

```sh
$ sudo update-initramfs -u
```

(7.) Reboot computer. Nothing should have changed in loading up menu. You should be taken to the login screen. Once there type: Ctrl + Alt + F1, and login to your user. Keep the next commands handy in another machine since now you are in tty.

(8.) In tty:

```sh
cd ~/Downloads/nvidia_installers;
sudo service lightdm stop
```

The top line is a necessary step for installing the driver.

(9.) [For Ubuntu 14.04]

```sh
sudo ./NVIDIA-Linux-x86_64-352.39.run --no-opengl-files
```

[For Ubuntu 16.04] --> Download nvidia-367 instead of the default nvidia-352 that comes with the toolkit from here: <http://in.download.nvidia.com/XFree86/Linux-x86_64/367.27/NVIDIA-Linux-x86_64-367.27.run> then do

```
sudo ./NVIDIA-Linux-x86_64-367.27.run --no-opengl-files
```

I cannot stress how important is the opengl flag in the above command. If you miss that, either you will get stuck in "login loop" or your computer would boot with a black screen at all times.

(10.) Now install the toolkit also

```sh
sudo ./cuda-linux64-rel-6.0.37-18176142.run
sudo ./cuda-samples-linux-6.0.37-18176142.run
```

(11.) Set Environment path variables in .bashrc:

```sh
$ export PATH=/usr/local/cuda-7.5/bin:$PATH
$ export LD_LIBRARY_PATH=/usr/local/cuda-7.5/lib64:$LD_LIBRARY_PATH
```

(12.) Verify the driver version:

```sh
$ cat /proc/driver/nvidia/version
My current resutls are:
NVRM version: NVIDIA UNIX x86_64 Kernel Module  367.27  Thu Jun  9 18:53:27 PDT 2016
GCC version:  gcc version 5.3.1 20160413 (Ubuntu 5.3.1-14ubuntu2.1)
```

(13.) Check CUDA driver version:

```sh
$ nvcc -V
```

(14.) At this point you can switch the lightdm back on again by doing:

```sh
$ sudo service lightdm start.
```

You are done if on Ubuntu 14.04 & go to step 17\. If on Ubuntu 16.04, the gcc version is higher than what is supported by any CUDA toolkit right now.

**READ ON FOR UBUNTU 16.04 ONLY**

(15.) Fix/break the header file that doesn't want to let us use gcc > 4.8\. All we are going to do is comment out (//) the error line that drops you out of a build.

```sh
$ sudo vim /usr/local/cuda/include/host_config.h
```

line: 115 comment out error //#error -- unsupported GNU version! gcc versions later than 4.9 are not supported!

(16.) To see if we are properly done with the installation, we need to run the samples that came along the downloaded toolkit runfile. By default it is installed in /usr/local/cuda/samples. Go there.

```sh
$ cd /usr/local/cuda/samples
$ grep -r nvidia-352 -l --null . | sudo xargs -0 sed -i 's#nvidia-352#nvidia-367#g'
```

The above command replaces all the places where sample's default nvidia-352 driver was used with nvidia-367

(17.) **BOTH 16.04 and 14.04**

```sh
$ cd /usr/local/cuda/samples/1_Utilities/deviceQuery
$ sudo make
$ ./deviceQuery
```

Something like this should show up

```sh
magneto@magneto-dell:/usr/local/cuda/samples/1_Utilities/deviceQuery$ ./deviceQuery
./deviceQuery Starting...

 CUDA Device Query (Runtime API) version (CUDART static linking)

Detected 1 CUDA Capable device(s)

Device 0: "Quadro M1000M"
  CUDA Driver Version / Runtime Version          8.0 / 7.5
  CUDA Capability Major/Minor version number:    5.0
  Total amount of global memory:                 2002 MBytes (2099642368 bytes)
  ( 4) Multiprocessors, (128) CUDA Cores/MP:     512 CUDA Cores
  GPU Max Clock rate:                            1072 MHz (1.07 GHz)
  Memory Clock rate:                             2505 Mhz
  Memory Bus Width:                              128-bit
  L2 Cache Size:                                 2097152 bytes
  Maximum Texture Dimension Size (x,y,z)         1D=(65536), 2D=(65536, 65536), 3D=(4096, 4096, 4096)
  Maximum Layered 1D Texture Size, (num) layers  1D=(16384), 2048 layers
  Maximum Layered 2D Texture Size, (num) layers  2D=(16384, 16384), 2048 layers
  Total amount of constant memory:               65536 bytes
  Total amount of shared memory per block:       49152 bytes
  Total number of registers available per block: 65536
  Warp size:                                     32
  Maximum number of threads per multiprocessor:  2048
  Maximum number of threads per block:           1024
  Max dimension size of a thread block (x,y,z): (1024, 1024, 64)
  Max dimension size of a grid size    (x,y,z): (2147483647, 65535, 65535)
  Maximum memory pitch:                          2147483647 bytes
  Texture alignment:                             512 bytes
  Concurrent copy and kernel execution:          Yes with 1 copy engine(s)
  Run time limit on kernels:                     No
  Integrated GPU sharing Host Memory:            No
  Support host page-locked memory mapping:       Yes
  Alignment requirement for Surfaces:            Yes
  Device has ECC support:                        Disabled
  Device supports Unified Addressing (UVA):      Yes
  Device PCI Domain ID / Bus ID / location ID:   0 / 1 / 0
  Compute Mode:
     < Default (multiple host threads can use ::cudaSetDevice() with device simultaneously) >

deviceQuery, CUDA Driver = CUDART, CUDA Driver Version = 8.0, CUDA Runtime Version = 7.5, NumDevs = 1, Device0 = Quadro M1000M
Result = PASS
```

Done!!

References:

1. <https://www.pugetsystems.com/labs/hpc/NVIDIA-CUDA-with-Ubuntu-16-04-beta-on-a-laptop-if-you-just-cannot-wait-775/>
2. <https://devtalk.nvidia.com/default/topic/878117/cuda-setup-and-installation/-solved-titan-x-for-cuda-7-5-login-loop-error-ubuntu-14-04-/>
3. <http://askubuntu.com/questions/451672/installing-and-testing-cuda-in-ubuntu-14-04>
4. [Step-by-Step Nvidia Passthrough To Ubuntu Tutorial in Russian](https://vk.com/@lord.alfred-nvidia-passthrough-to-ubuntu-in-vmware-esxi)
