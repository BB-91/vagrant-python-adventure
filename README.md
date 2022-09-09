### Requirements
- Vagrant - https://www.vagrantup.com/downloads
- VirtualBox - https://www.virtualbox.org/wiki/Downloads

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