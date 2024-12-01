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
add install steps and pictures for virtualbox setup

## Initial Virtual Machine Boot
add picture of initial boot
do ahcpi shutdown



