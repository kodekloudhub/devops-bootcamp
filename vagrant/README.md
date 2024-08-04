# Build your own lab

If your laptop is Windows or Intel Mac, then you can also follow the videos in these lectures, but with caveats! You *cannot* follow the videos if you have an Apple Silicon Mac (M1/M2/M3), as VirtualBox does not work on these laptops. Read on in this document as we can still deploy a lab.

The guest operating system discussed in the videos is CentOS 7. That version is now retired by Red Hat and no longer works therefore where the lecture asks you to find a `CentOS/7` box, you need instead a `CentOS/9` version.

In this lab we will go directly to Vagrant to automate the deployment of VMs in a host platform independent manner, that is, the code here will work for all types of laptops in exactly the same way once the correct prerequisites have been installed.

Note that the [Vagrantfile](./Vagrantfile) we will use is quite different to what is discussed in the video. Vagrantfiles are written in the Ruby programming language, therefore any valid Ruby syntax can be used and we take advantage of this fact to make a Vagrantfile that is compatible with all the different types of laptop, and the fact that the laptops can't all use VirtualBox - we must use VMware on Apple Silicon because VirtualBox doesn't work.

Next: [Prerequisites](./docs/01-prerequisites.md)
