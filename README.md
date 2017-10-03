# Suport project for Health services waiting times
This support project allows to completly automatize the process of installation and setting to use the ["Health service waiting times"](https://github.com/abonte/southtyrolean-healthservices-waitingtimes). Moreover the script included, will set a complete environment that will give the possibility to lunch and debug the project locally (host machine) because is activated a port-forwarding (port 8000) on the default port used by the gunicorn server (guest machine). 

## Prerequisites

In order to use the Vagrant file is needed to create:
* the folder projects in the host machine
* the folder projects in the guest machine with this path vagrant/projects as specified in the Vagrant file.

```
# Share an additional folder to the guest VM. The first argument is
# the path on the host to the actual folder. The second argument is
# the path on the guest to mount the folder. And the optional third
# argument is a set of non-required options.
config.vm.synced_folder "projects", "/vagrant/projects"
```
In this way will be possible to work mantaining the folders syncronized.


### Vagrant script
Download the [Vagrant](https://github.com/carlonicolo/vagrant-healthservices-waitingtimes/blob/master/Vagrantfile) file and the [deploySouth.sh](https://github.com/carlonicolo/vagrant-healthservices-waitingtimes/blob/master/deploySouth.sh) in the main folder of Vagrant machine and then reload the machine.


Automatically:
* download and install OS dependencies;
* set python3 as default environment;
* clone the project;
* open the port 8000;
* create a running script for the project.

### Start the project

Simply run the file deployment.run (as normal user) generated in vagrant/projects/healthservices-waitingtimes/:

```
vagrant@vagrant$pwd
vagrant/projects/healthservices-waitingtimes
vagrant@vagrant$./deployment.run
```

At this point the server will be recheable from the host machine typing in the browser the following address:
```
http://locahost:8080
```