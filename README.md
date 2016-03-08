Building Custom CentOS 6.4 LiveCD With Ansible
==============================================

## Requirements:
1. CentOS 6.X machine.
2. livecd-tools, git, python-argparse, screen and ansible – all packages available in EPEL repository.

Install EPEL repository if not already installed:

    # yum -y install http://ftp.nluug.nl/pub/os/Linux/distr/fedora-epel/6/i386/epel-release-6-8.noarch.rpm

Install required packages:

    # yum -y install livecd-tools git ansible python-argparse screen

Clone livecd-ansible repository:

    $ git clone https://github.com/joseba/livecd-ansible.git
    
Add your custom ansible roles, modify centos6-mini.yml and generate the CD:

    $ cd livecd-ansible
    $ ./generate_config.py centos6-hpe.yml
    $ sudo -s
    # livecd-creator -c centos6-hpe.ks --cache=cache -f centos6-hpe


