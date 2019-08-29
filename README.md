## IaaC project : git_lab  
 A Vagrantfile to build signle node virtual envirnment to learn about jenkins adminstration for  CI/CD projects  
 vagrant_jenkins_lab/Vagrantfile  : This Vagrantfile contains the information needed to create a centOS/7 virtual machine and install git_lab


### Steps :  
  Step 1 :  Install virtual box (https://www.virtualbox.org)

  Step 2 :  Install vagrant  (https://www.vagrantup.com)

  Step 3 :  Download and  Vagrant file  
       git clone https://github.com/malyabee/vagrant_jenkins_lab.git
          or 
       Downlaod https://github.com/malyabee/vagrant_jenkins_lab/archive/master.zip and unzip master file 
       

  Step 4  : starting virtual machines 

       $ cd vagrant_jenkins_lab
 
       $ vagrant up

### commands to login three virtual machines
     cd vagrant_jenkins_lab

     vagrant ssh 

#### Host compatability :

    This Vagrant verified on Mac and Windows


### accessing gitlab web UI
  open "http://localhost:8000/" url in  your browser to see jenkins environment.

  
