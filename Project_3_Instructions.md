# Lance Blackwood's Development Environment  

This procedure will create a development environment suitable to run in a virtual machine.
The environment will focus on an environment using Microsoft Visual Studio Code, a free integrated development environment running on Ubuntu Linux.
There is also an eye on memory footprint, so older tools such as Midnight Commander, Window Maker, and XTerm are used.
Database work will be done with Oracle MySQL Community, and Perl will round out the LAMP stack.
While sonme of these tools are crude, they are available on almost every production server from cloud to telecommunications so learning them is a good idea.
Combining these tools makes for a development environment that matches the production environment.

| Application | Use | Link |
|-------------|-----|------|
| VirtualBox | virtual machine | https://www.virtualbox.org/ |
| Ubuntu | operating system | https://ubuntu.com/ |
| Window Maker | window manager | https://www.windowmaker.org/ |
| XTerm | terminal emulator| https://invisible-island.net/xterm/ |
| Midnight Commander | file manager | https://midnight-commander.org/ |
| Vim | text editor| https://www.vim.org/ |
| MySQL | database | https://www.mysql.com/ |
| Perl | scripting | https://www.perl.org/ |

## Install Oracle VirtualBox

This is the virtual development that will host the virtual machine. The initial steps will be to download the latest install package for your host operating system. 
This example is using Windows 11 as the host and will be installing Ubuntu as the guest operating system.  

Download the latest version from the [VirtualBox downloads](https://www.virtualbox.org/wiki/Downloads) page, which is 7.1.4 at the time of this writing, for your host operating system.
Once downloaded double click the executable to launch the installer, the default choices will leave a sane VirtualBox install.

## Install Ubuntu Server LTS

The guest operating system is Ubuntu Server LTS, or long-term support. Versions designed with long support in mind are easier to develop for as programming interfaces are changed much less over time that regular versions. The virtual machine will need a disk image to boot from, [Ubuntu Server downloads](https://ubuntu.com/download/server), get the 24.04.1 LTS version.

## Create Virtual Machine in VirtualBox
Click on the blue New button to create a new virtual machine.
![Initial VirtualBox screen](screenshots/01-virtualbox%20start.png)  
  
From the Name and Operating System section set the name field to the preferred hostname, this example used "devenv", the the operating system type to Linux, subtype to Ubuntu, and the Version to Ubuntu (64-bit). Use the ISO Image field chooser to select the disk image downloaded earlier.
![Set name and operating system](screenshots/02-vm%20name%20and%20os.png)  

From the Hardware section set the number of CPU and amount of memory, in this case 4 CPU and 8192 megabytes of memory. 
![Set number of CPU and memory](screenshots/03-vm%20hardware.png)  

Finally from the Hard Disk set the location of the virtual disk. The size can be left at the defaults which will provide a 25 gigabyte disk. Check the Pre-allocate Full Size checkbox to speed up disk operations.
![Set disk partition](screenshots/04-vm%20disk.png)

Now all the setting are set so click the Finish button which will provision the disk, and start the operating system from the image.

## Initial Virtual Machine Boot
You will be presented with a boot screen after the virtual machine is created. Choose all the defaults during install. When presented with the choice for machine name this documents chose "DevEnv". Set a username and password, when presented with the choice, and remember the choices.
Choose Machine/ACPI Shutdown to shut the virtual machine down in order to do more virtual machine configuration.
![The initial boot screen.](screenshots/05-initial_boot.png)

## Configure Video RAM
From the main VirtualBox screen, make sure the DevEnv is selected and click the orange settings button. 128 megabytes of video RAM ensures the Linux virtual machine runs smoothly.
![The display settings screen.](screenshots/06-detail_settings.png)

## Initial Login
After starting the virtual Machine again and logging in, you should be presented with a screen similar to this one.
![The display settings screen.](screenshots/07-after_login.png)

Update the system to the latest versions of everything at the command prompt.
```
sudo apt update
sudo apt upgrade
```

## Install Window Maker, Xterm and WDM
Ubuntu server does not have a graphical user interface (GUI) so we need to install one. This will install a lot of other packages, so choose yes "Y" when asked. 
```
sudo apt install wmaker xterm wdm
```

## X-Windows Login
Once wdm, the Wings Display Manager, is installed Ubuntu will switch to a graphical login. Login again.
![The display settings screen.](screenshots/08-wdm.png)

This should get you to the default Window Maker desktop.
![The display settings screen.](screenshots/09-windowmaker_default.png

Double click the terminal icon to start XTerm.

## Shared Clipboard and Mouse Integration
From the Devices menu, choose Insert Guest Additions CD Image... In the XTerm window mound the disk and install the additions.
```
sudo mount /dev/cdrom /media
sudo apt install bzip2
sudo /media/VBoxLinuxAdditions.run
```
Once the additions are complete, choose Machine/ACPI Reboot to restart the machine with mouse and clipboard integration.
^^ clipboard still broken, hmm

## Install the applications we need
```
sudo apt install mc
sudo apt install firefox
```

## Install Microsoft Visual Studio Code
Start firefox from the command prompt.
```
firefox &
```
Navigate to the Visual Studio Code Website and download the deb package.
https://code.visualstudio.com/

Install Code from the downloaded package
```
sudo apt install ~/snap/firefox/common/Downloads/code_1.96.3-1731523102_amd64.deb
```

## Install Oracle MySQL Workbench
Navigate to the Oracle MySQL website and download the deb package for Workbench.
[https://code.visualstudio.com/](https://dev.mysql.com/downloads/workbench/)

Install Workbench from the downloaded package
```
sudo apt install ~/snap/firefox/common/Downloads/mysql-workbench-community_8.0.40-1ubuntu24.04_amd64.deb
```
## Theme XTerm so it is not garishly ugly

## Theme Window Maker to make even better







