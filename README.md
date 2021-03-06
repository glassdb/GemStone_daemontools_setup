## daemontools setup scripts for GemStone/S on Ubuntu or other Debian systems

### Prerequisites

* Install and set up GemStone/S 2.4.4.1 or later
* Install daemontools (sudo apt-get install daemontools daemontools-run svtools)
Note: It's OK to install daemontools after running the setup, but /etc/init.d/topaz
and /etc/init.d/statmon won't work until you do.

### Running the setup scripts

Make sure that the config file in this directory is appropriate for your setup.
Make sure you have root access so the setup can execute properly. Then execute:
  sudo bash ./setupAll.sh

It is recommended that you follow the [gsDevKitHome intallation instructions][1] to 
install GemStone on your system.

There are some utility scripts not run by setupAll.sh that can be useful when
testing.  Even though they prompt you before executing, you should read them and
understand what they do before using them -- particularly any 'destroy_' scripts.

### Setting up your user account

The scripts in bin/ that start and stop GemStone use sudo. You may find it
convenient to setup your sudoers file so you don't have to supply a password to
run them. There is an example sudoers file in etc/. Add the appropriate lines to
your system sudoers file using "visudo".

You should add the daemontools control scripts to your path by adding the following 
line to your .bashrc:

```Shell
export PATH=$PATH:~/GemStone_daemontools_setup/bin
```

[1]: https://github.com/GsDevKit/gsDevKitHome#open-source-development-kit-for-gemstones-64-bit-
