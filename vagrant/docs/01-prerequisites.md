# Prerequisites

# Prerequisites

Set up the required software.

## All systems

**Install Vagrant**

1. Go to the [download page](https://developer.hashicorp.com/vagrant/downloads)
1. For Macs:
    * If you have [homebrew](https://brew.sh/) installed (you really should :smile:), follow the **Package manager** instructions, *else*
        * For Intel Mac, download the AMD64 version
        * For Apple Silicon Mac, download the ARM64 version.
        * Both the above will download a DMG package which Finder should offer to install for you. If the installer doesn't start by itself, double click the downloaded DMG package.
1. For Windows
    * Download the AMD64 version which is a Windows Installer package. Open this file when it's downloaded and Windows Installer will install it.

## Windows/Intel Mac

**Install VirtualBox**

1. Go to the [download page](https://www.virtualbox.org/wiki/Downloads)
1. Click on the platform packages link for your system
    * For Macs, Finder should offer to install the downloaded DMG package for you
    * For Windows, open on the downloaded file to launch the installer.

## Apple Silicon Mac

**Install VMware Fusion**

This is quite fiddly due to the fact that the Broadcom site is like a maze (Broadcom acquired VMware at the end of 2023). They keep moving it around therefore it is not practical to have specific instructions here, however the general gist is -

1. Start at https://www.vmware.com/products/desktop-hypervisor/workstation-and-fusion
1. Select Download Fusion or Workstation - you will be redirected to a login page.
1. Register for a new account.
1. Once your account is activated, then find your way to the Fusion Pro download page.
1. Download it and Finder will install it for you

**Install the Vagrant provider for VMware**

* Follow the instructions [here](https://developer.hashicorp.com/vagrant/docs/providers/vmware/installation).

Next: [Deploy Virtual Machines](./02-deploy-vms.md)<br/>
Prev: [Introduction](../README.md)
