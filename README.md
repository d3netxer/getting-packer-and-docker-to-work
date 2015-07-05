# getting-packer-and-docker-to-work
just notes : )

This is for my Ubuntu 14.04 machine

#Installation

##install packer
https://www.packer.io/docs/installation.html

##install docker
https://docs.docker.com/installation/ubuntulinux/
Except don't install the latest version of docker. As referenced in this issue (https://github.com/mitchellh/packer/issues/1752), the 1.4x version of docker does not allow in-line shell scripts in packer to work.

I had to uninstall docker the first time and install the 1.3.2 version (http://www.luiselizondo.net/how-to-completely-remove-packages-with-apt-get-on-ubuntu-linux/):

[code]sudo apt-get remove --purge lxc-docker[/code]

[code]sudo apt-get autoremove --purge[/code]

[code]sudo apt-get install lxc-docker-1.3.2[/code]

###also:

You need to enable your ubuntu user to have permissions to docker so packer can run docker commands and work:

so don't skip this step in the docker installation docs. ex: $ sudo usermod -aG docker ubuntu

###packer scripts:

Finally, this is a good repo to get started on you packer scripts:

https://github.com/eggsby/docker-ansible-packer

#To Read:

Packaging Django applications into Docker container images
http://michal.karzynski.pl/blog/2015/04/19/packaging-django-applications-as-docker-container-images/



