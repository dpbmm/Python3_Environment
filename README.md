## Vagrant environment for Python 3 development

This README is dated 20150421.

This repository contains a Vagrantfile and other content sufficient to set up Ubuntu "Trusty:" (64bit), v. 13.4.0 and a `pyvenv` virtual environment for Python v. 3.4.

The working Vagrantfile (the configuration file for a Vagrant environment) is in the top-level directory of the repository. To use:

 1. Clone this entire repository.
 1. Install Vagrant on your host operating system, following instructions beginning [here](http://docs.vagrantup.com/v2/installation/). What follows assumes your "host" operating system is Mac OS 10.9.5; your "guest" operating system is the one being provisioned by Vagrant. I am using VirtualBox as my virtual machine, but other choices are possible.
 1. Initialize, run, and log in to the Vagrant environment as described in the sections below. Note:

    > If you run vagrant by itself, help will be displayed showing all available subcommands. In addition to this, you can run any Vagrant command with the -h flag to output help about that specific command.
      
    Further instructions will be found at the Vagrant site.

### Launching

After cloning, enter the top-level directory, and do set-up and log-in with these two steps:

    vagrant up

The first time you do this, a virtual machine will be provisioned and launched; after the first time, the existing virtual machine will simply be launched without reprovisioning. On a recent MacBook Pro running OS 10.9.5, provisioning takes about two or three minutes; launching without re-provisioning takes about twenty seconds.

### Logging in to a running virtual machine

    vagrant ssh

You will be logged in as the user `vagrant` with administrative privileges and the password `vagrant`. The prompt should look like this:

    (v_env34) vagrant@vagrant-ubuntu-trusty-64:/vagrant$

The element `(v_env34)` at left indicates that you are using the `pyvenv` virtual environment "v_env34". You can leave the environment by typing

    deactivate

After deactivating, you can reactivate it with:

    cd /vagrant
    source v_env34/bin/activate

The element `/vagrant` (note the backslash) is the name of your present working directory in the guest OS. It corresponds to the top-level directory on your host operating system. 

I suggest that you edit files using an editor on your host operating system, and use the virtual machine only to run code in the guest operating system.

### Logging out and shutting down

To log out, use

    exit

Note that this will leave the virtual machine running. To fully shut down the virtual machine, use

    sudo shutdown -h 0

[end]
