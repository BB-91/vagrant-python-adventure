### Requirements
- Vagrant - https://www.vagrantup.com/downloads
#### Windows
- VirtualBox - https://www.virtualbox.org/wiki/Downloads

#### Mac
- VMWare - https://www.vmware.com/
    #### (If you have an M1 chip, you must also do the following):

    - Inside the Vagrantfile, comment out all the code inside the block labeled:
    
            --- Windows (and Mac without M1 Chip) ---

    - and uncomment all the code inside the block labeled:

            -- Mac OS M1 Chip Only ---
#### Mac with M1 chip
```
If you are using M1 chip machines here are some extra instructions to follow for Vagrant setup:

Vagrant and VMWare Tech Preview on Apple M1 Pro

This document summarizes notes taken while to make the VMWare Tech preview work on Apple M1 Pro, it originated from discussions in https://github.com/hashicorp/vagrant-vmware-desktop/issues/22

Installing Rosetta

First install Rosetta if not already done, this is needed to run x86 code:

/usr/sbin/softwareupdate --install-rosetta --agree-to-license

Installing Vagrant
Install Vagrant via brew or install it manually. Note that I use [2.2.18] (https://releases.hashicorp.com/vagrant/2.2.18/vagrant_2.2.18_x86_64.dmg) as 2.2.19 did not work for me. (YMMV)

brew install vagrant@2.2.18

Installing VMWare Fusion Tech Preview

You will need to create an account on vmware as it needs user and key information that are user specific.
The registration process is kinda convoluted. Be careful about passwords as the password needs to be less than 20 characters and there are no error messages for this.

You can download the tech preview via the - https://customerconnect.vmware.com/downloads/get-download?downloadGroup=FUS-PUBTP-2021H1

Once this is installed you will *NEED* to create a symlink as the vagrant vmware utility etc.. assumes that vmware is installed in a specific directory and the tech preview is installed in a different one.

ln -s /Applications/VMWare\ Fusion\ Tech\ Preview.app /Applications/VMWare\ Fusion.app

Installing Vagrant VMWare provider
It requires two steps. This is detailed in the - https://www.vagrantup.com/docs/providers/vmware/installation but follow the steps below:

First go to - https://www.vagrantup.com/vmware/downloads and download the binary and install it. It says x86_64 but it is fine.The direct link is:

https://releases.hashicorp.com/vagrant-vmware-utility/1.0.21/vagrant-vmware-utility_1.0.21_x86_64.dmg

It needs to be version 1.0.21Next install the provider:
vagrant plugin install vagrant-vmware-desktop
```

### Instructions
- Open a terminal at this folder location.
- Run the following command to initialize an Ubuntu virtual machine:
        
        vagrant up

- Wait until  ```--- Initialization Complete ---``` is printed to the terminal.
- To enter the virtual machine:
        
        vagrant ssh

- Wait until the terminal displays path ```vagrant@ubuntu2010:~$```
- Move into the ```app``` directory:

        cd app/

- The terminal path should now be ```vagrant@ubuntu2010:~/app$```
- The following command will start the game:

        python3 adventure.py

- The terminal will now prompt you to select between 2 choices.
- You can select a choice by typing `1`, `2`, or the associated phrase, such as `Go East`, and then hitting the `Enter` key.
- You can exit the game by choosing the `Quit` option when it is shown, or you can force quit with `Control+C` (on Windows).

- Once you've quit the Python program, you can exit the virtual machine with the following command:
        
        exit

- If you were inside ```vagrant@ubuntu2010:~/app$``` when running the Python script, you'll see that ```logfile.txt``` was created in your local ```app``` folder. This file will display the prompts and choices you made during your previous playthrough.

- When you're done, you can destroy the VM with:
    
        vagrant destroy -y