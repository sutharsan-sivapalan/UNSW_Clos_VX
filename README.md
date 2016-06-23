# UNSW_Clos_VX

2-spine, 3-leaf & 4 server environment using Cumulus VX, Vagrant, VirtualBox & Ansible.


Prerequisites

The following tools are required to run this demo. Details about how each of the tools are being used can be found here.

Download the Cumulus VX version 3.0.0 file for Vagrant Box.
https://cumulusnetworks.com/cumulus-vx/download/
VirtualBox must be installed.
https://www.virtualbox.org/
Vagrant must be installed.
https://www.vagrantup.com/
Ansible must be installed using PIP or APT.
http://www.ansible.com/
The Cumulus Linux module for Ansible must be installed.
Once Ansible is installed, this is achieved with the command ansible-galaxy install cumulus.CumulusLinux
The Cumulux VX Vagrant Plugin must be installed.
Once Vagrant is installed, this is achieved with the command vagrant plugin install vagrant-cumulus


![Topology](./Topology.png)
