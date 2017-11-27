---
layout: post
title: "Getting started with OpenVX!"
published: true
comments: true
---


 
I will try to get you set up with OpenVX sample implementation in your system. The following goes on for Ubuntu(14.04). (Though it should work for any unix based system.)

- Go to [official Khronos OpenVX page](https://www.khronos.org/registry/vx/) and download the latest Sample Implementation source code. As of now, it is of the name _OpenVX 1.0.1 Sample Implementation_.

- Untar it. Go to the project's root directory. 
Run 

```bash 
$ python Build.py --os=Linux 
```

For this step to be successful, your system must have the build essentials installed (things like make, g++, gcc etc) along with cmake. You can get them using 

```bash 
$ sudo apt-get install build-essential cmake 
``` 

- Now you must be having a `install/` folder in which the generated shared libraries gets stored. Exact path for the OpenVX headers path and the shared libraries for my system are shown below:

```sh
$ /home/.../openvx_sample/install/Linux/x64/Release/include
$ /home/.../openvx_sample/install/Linux/x64/Release/bin
```

This whole address will be different for your system but still, it should be located in the install folder.

## Running built in Tests

To see that this sample implementation has been configured properly, go to project_directory/raw folder. In there run in terminal 

```sh
$ cd raw/
$ ./../install/Linux/x64/Release/bin/vx_test
```

Most of the tests should pass without any problems! Yayy, you are now ready to develop code using the OpenVX API. 
In my next posts, I will show you how to write a sample code there.
