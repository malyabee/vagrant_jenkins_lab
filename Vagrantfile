# -*- mode: ruby -*-
# vi: set ft=ruby :

$commonscript = <<-SCRIPT
sudo yum update -y
sudo yum install epel-release -y

sudo echo "LANG=en_US.utf-8" > /etc/environment
sudo echo "LC_ALL=en_US.utf-8" >> /etc/environment
SCRIPT


$jenkinsscript = <<-SCRIPT

sudo wget -O /etc/yum.repos.d/jenkins.repo http://pkg.jenkins-ci.org/redhat-stable/jenkins.repo

sudo rpm --import https://jenkins-ci.org/redhat/jenkins-ci.org.key

sudo yum install java-1.8.0-openjdk -y 

sudo yum install jenkins -y 

sudo service firewalld restart
sudo service jenkins start
sudo chkconfig jenkins on 

SCRIPT

##Firewall Exceptions
# sudo firewall-cmd --permanent --add-port=8080/tcp
# sudo firewall-cmd --zone=public --add-service=http --permanent
# sudo firewall-cmd --reload


Vagrant.configure("2") do |config|
    # Box
    config.vm.box = "centos/7"


    ## if you want difine disk size we need to install vagrant-disksize plugin 
    ## command to install disk-size pluging is 'vagrant plugin install vagrant-disksize'
    # config.disksize.size = '50GB'

    # Memory and CPU allocation
    config.vm.provider "virtualbox" do |v|
    v.memory = 1048
    v.cpus = 1
    end

    # IP allocation
    # config.vm.network "private_network", ip: "192.168.22.10", virtualbox__intnet: "mynetwork01"

    # port forwarding
    config.vm.network "forwarded_port", guest: 8080, host: 8000
    config.vm.network "forwarded_port", guest: 443, host: 4430
    config.vm.network "forwarded_port", guest: 22, host: 8022


    # Host name allocation
    config.vm.hostname = "jenkins.example.com"

    # Installing required packages for ansible controller node
    config.vm.provision "shell", inline: $commonscript
    config.vm.provision "shell", inline: $jenkinsscript
end