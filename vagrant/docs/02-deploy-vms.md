# Deploying the Virtual Machines

Do all the following from your favourite terminal application

1. Clone this repository

    ```bash
    git clone https://github.com/kodekloudhub/devops-bootcamp.git
    ```

1. Change to `vagrant` directory

    ```bash
    cd vagrant
    ```

1. Start the virtual machines.

    ```bash
    vagrant up
    ```

    Soon after the process starts, it will display a box like this. If you need to raise questions on our forums about the VM installation, you *must* copy this output from your system and include it with your message so we can help you better.

    ```text
    ┌─────────────────────────── EXAMPLE ─────────────────────────────────┐
    │ If raising a question on our forums, please include the contents    │
    │ of this box with your question. It will help us to identify issues  │
    │ with your system.                                                   │
    │                                                                     │
    │ Detecting your hardware...                                          │
    │ - System: Microsoft Windows 10 Enterprise                           │
    │ - CPU:    Intel(R) Core(TM) i7-7800X CPU @ 3.50GHz (12 cores)       │
    │ - RAM:    32 GB                                                     │
    └─────────────────────────────────────────────────────────────────────┘
    ```

    When the process completes successfully, it will display the names of the VMs and their IP addresses on the virtual network

    ```text
    192.168.56.11 virtualmachine-1
    192.168.56.12 virtualmachine-2
    ```

    Note that the login credentials for all these machines is

    ```
    Username: vagrant
    Password: vagrant
    ```

4. Test logging in.

    1. Log into the first VM

        ```
        vagrant ssh virtualmachine-1
        ```

        This login is password-less so you should get directly to the CentOS prompt.

    1. Test the first machine can connect to the second machine

        ```
        ssh virtualmachine-2
        ```

        You will be asked for the password this time, which is the password above.

    1. Enter `exit` command twice to retun to laptop command prompt.

## Changing the VM configuration

You can change the VM configuration, or even run ubuntu instead of CentOS with some simple edits to your local copy of the Vagrantfile. Make these changes before deploying the VMs, or after first deleting them (see below) if they are running.

It is all done by editing [this section](../Vagrantfile#L16-L30).

* To add a VM simply add a new VM definition to this list, e.g.

    ```ruby
    {
        name: "virtualmachine-3",
        cpu: 2,
        memory: 2048,
        box: Hypervisor.centos,
    },
    ```

* To remove a VM, simply delete the VM definition block.
* To change CPU or memory for a VM, edit the values at `cpu:` and `memory:` in the VM definition. Note that if the sum of `memory:` for all the machines you have added exceeds the total memory of your system minus 2GB (to allow space for Windows/MacOS to run), then you will get an error. You can overprovision virtual CPUs past the number of CPUs on your laptop although the VMs might run slowly. You cannot request more memory than the laptop has installed.
* To run Ubuntu, change the `box:` setting to `Hypervisor.ubuntu`
* To change the hostname of a VM, edit the `name:` setting to the new name.
* To add a port-forward so you can e.g. browse an nginx server you want to configure, simply add a `ports` property to the VM definition, so it might look like the following. This would allow you to browse `http://localhost:8080` to see the nginx page:

    ```ruby
    {
        name: "virtualmachine-3",
        cpu: 2,
        memory: 2048,
        box: Hypervisor.centos,
        ports: [
            "8080:80",
        ],
    },
    ```

    Multiple ports can be added in the list, e.g. you also have a MySQL

    ```ruby
    ports: [
        "8080:80",
        "3306:3306",
    ],
    ```

## Deleting the VMs

To erase all VMs, do

```
vagrant destroy -f
```

Next: [Install Ansible](./03-install-ansible.md)<br/>
Prev: [Prerequisites](./01-prerequisites.md)

