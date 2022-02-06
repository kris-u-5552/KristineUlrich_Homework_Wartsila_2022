# KristineUlrich_Homework_Wartsila_2022


 Description:

 This project will use vagrant to start a Centos 7 virtual machine running a Nginx webserver with a static website. Ansible playbooks and linux commands will be used for setup. 

 A completed project will show a static website in a browser at:

 <server IP or hostname>:8085


 Dependencies:

 This project is meant to run on a Ubuntu linux host with virtualization/nested virtualization enabled. The host will need to be able to access the internet (port 443 and/or port 80). You will need to access the Ubuntu host through ssh port 22 if it is not installed on your local machine. The host will need port 8085 open to incoming traffic and ports 2225 and 2222 to access the vangrant host via ssh. A root user or user with sudo privileges is required.

 	Packages and versions used for testing:

 		-Ubuntu 20.04.3 LTS (Focal Fossa) - server install image running on a cloud platform with nested virtualization enabled
 		-Ansible 2.9.6
 		-Virtualbox 6.1.26
 		-Vagrant 2.2.9
 		-Google Chrome Version 97.0.4692.99 (64-bit) - on the user's laptop


 Project Setup:

 	1. Login to the Ubuntu host command line with a user with sudo privileges
 	2. You will need Ansible installed locally if it is not already installed:

 		apt-get install ansible

 	3. Go to the directory you intend to house the project files in (I used the /opt directory /home/<username> is also a good option)
 			Example command:

 			cd /opt
 	3. Clone the repository for this project into the directory:

 		git clone https://github.com/kris-u-5552/KristineUlrich_Homework_Wartsila_2022.git

 	4. cd into the new directory:

 		cd KristineUlrich_Homework_Wartsila_2022/

 	5. You will need to install Virtualbox and Vagrant if they are not already installed. It is also a good idea to update all of the packages on the operating system before proceeding. The Ansible playbook included in this project "setup_ubuntu_host.yml" will accomplish these tasks - read the playbook for more details. It is optional if you already have Virtualbox and Vagrant on the localhost.

 		Command to run playbook as is with verbose output:

 			ansible-playbook --verbose -K setup_ubuntu_host.yml

 		Command if you don't want to install Virtualbox and Vagrant but want to update Ubuntu packages for example:

 			ansible-playbook --verbose -K -e '{"install_virtualbox": false, "install_vagrant": false}' setup_ubuntu_host.yml

 	6. Make sure you are still in the KristineUlrich_Homework_Wartsila_2022/ directory - the Vagrantfile is here. You will now provision the Centos 7 virtual machine with Vagrant with the command:

 		vagrant up

 	7. If everything has been setup with no errors you should be able to open your browser of choice and go to the hostname or IP of the Ubuntu server localhost on port 8085 and access the content:

 		<server IP or hostname>:8085












