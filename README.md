## IaaC project : jenkins_lab  
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


### accessing jenkins web UI
  open "http://localhost:8000/" url in  your browser to see jenkins environment.

 in webUI you need to enter password which is stored at  /var/lib/jenkins/secrets/initialAdminPassword 



 This Vagrant based jenkins lab created based on 
 https://www.vultr.com/docs/how-to-install-jenkins-on-centos-7 

 For other installations refer
https://jenkins.io/doc/book/installing/


 ### Example projects  
 
 We can use following example code base to learn jenkings
 https://github.com/ravikiran-srini/springExample
 
 
 Jenkins :
   -- Installation : https://www.youtube.com/watch?v=-0dkiteJEuE
      UserManagement and  Roles : https://www.youtube.com/watch?v=jZOqcB32dYM
      
 
 
 GitHub Tutorials : 
 https://github.com/miztiik/DevOps-Demos/tree/master/setup-jenkins
 
 https://github.com/miztiik/DevOps-Demos/tree/master/setup-jenkins-slave
 
 
 
 
Continuous Delivery
   –involves a manual trigger to production.

Continuous Deployment
    –involves automatic releases to production.

Continuous Integration
    – is usually the initial part of both Continuous Delivery and Deployment, involving the testing and building of any new or updated source code. 
    
   
## Pyhton projects    
   
Python sample project :

Python References 
     https://github.com/pypa/sampleproject

Build "Execute shell" commands 

    PYENV_HOME=$WORKSPACE/.sample1/

    # Delete previously build virtualenv
    if [ –d $PYENV_HOME ]; then
      rm –rf $PYENV_HOME
    fi

    # Create and install necessary packages
    python3 -m venv $PYENV_HOME
    source $PYENV_HOME/bin/activate
    # pip install –r envs/req.txt
    pip install --quiet nosexcover
    pip install --quiet pylint
    pip install --upgrade pip
    pip install --quiet pytest
    pip install --quiet wheel

     pip install --quiet $WORKSPACE/  # where your setup.py lives

    python $WORKSPACE/setup.py sdist bdist_wheel
    pytest -p no:cacheprovider

    # nosetests --with-xcoverage --with-xunit --cover-package=myapp --cover-erase
    # pylint -f parseable myapp/ | tee pylint.out


 

  
 Notes to build python based jobs

    http://www.alexconrad.org/2011/10/jenkins-and-python.html
    
    
    https://chrigl.de/posts/2013/08/14/integration-of-pylint-into-jenkins.html
