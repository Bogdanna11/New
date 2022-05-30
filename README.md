hello
Commands for working with Github and pushing documents remotely to GitHub:

1) : Create a local directory ( MKDIR)
2) : CD into that directory
3) git init -- will inialize a local repository in that directory
4) git nano README.md - creates a README -file
5) this file I can edit and save with : ctl + x /y  + enter
6) cat README.md to check if the file was created
7) next I add everything from that folder to git : git add a .
8) git commit -m 'adding the content'
9) git branch -M main -- to make sure that we add to the main branch
10) I add the link which connects remotely to main repository : gir remote add origin https://github.com/Bogdanna11/New.git
11) Now push eveything to github : git push -u origin main 
12) 
IMPORTANT : when we open the git bash shell we need to run it as administrator

How to reload/recrete my VM :

1) create a local directory where to run the following command: vagrant init ubuntu/xenial64 -- this will create the vagrantfile which will be placed in your directory
2) vagrant up -- this will start the virtual machine
3) vagrant destroy - this will destroy the virtual machine
4) to enter the actual virtul machine we do : vagrant ssh
5) I can stop the machine by doing : vagrant halt
6) vagrant status : will show if the machine is running or not
7) if I do the command : ls in my directory it should show the following content : 
 ls
README.md  Vagrantfile  main  ubuntu-xenial-16.04-cloudimg-console.log
To delete a file : rm -rf name_of_file

HOW TO GO INSIDE OF THE MACHINE: my localhost will go inside of the machine with the following commang : vagrant ssh .
This command will give : vegrant@ubuntu-xenial:$

How to check if the virtual machine can use the internet from my local host through this virtual box?

How to update and upgrade commands
sudo apt-get update 
the machine will send the request to the local host and ask to use the internet

sudo apt-get upgrade ( to check that all the upgrades are loaded) 


How to install nginx -- is a web server--;

sudo apt-get install nginx -y 
now we need to check things inside of ubuntu : the status of the package which we have just installed.
systemctl status nginx
this is running inside of the ubuntu machine - the web server--
So how can we see it in the browser? we need to provide the information in the vagrant file which connects us to the network.
exit -- to go from the virtual machine to the local host--;
here we are going to make a change by editing the vagrantfile -
nano vagrantfile -enter 
we start editing  by adding : 
#add private network between localhost and VM
    config.vm.network " private_network", ip:"192.168.10.100"
We have made a change in the local host,but in the VM is not available.
We have to restart the machine -- after saving the changes.

The comand is : vagrant reload ( check for spelling in the vagrant file)
Every time we do a change in the vagrant file we need to reload or destroy and do vagrant up.
How to ensure that I see it in my browser?
To close the machine we do : vagrant destroy
Then--> vagrant up --> vagrant status --> vagrant ssh
Then rerun the commands : 
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install nginx -y 
systemstl status nginx

Go to the browser and type the IP -- that will load nginx !!
We created a private network which allowed us to see nginx.

We do this because we will need to deploy a node.js app and we will need to test it first.
Linux commands
-to update and upgrade UBUNTU : 'sudo apt-get update -y'

How to stop the server from running : sudo systemstl stop ngnix 
Check status : it will stop running in the browser.


From inside of the Linux machine we need to learn how to talk with the machine and get more info.

TO FIND THE NAME : uname  OR uname - a
WAHT IS THE LOCATION : pwd ( will tell us the default directory) 
 create a new directory : mkdir 
 check file/folder : ls 
 check for hidden folders: ls -a
 change directory : cd name -dir
 come back 1 step : cd ..
 come to home location : cd
 how to create a file : touch filename or nano filename ( goes inside of the file as well ) 
 to copy a file to another location : cp path_of_file  path_of_destination
 check if a file exists : ls
 to edit a file : nano name of the file
or  vi.test.txt
 moving the file from current location to devops : mv name of the file devops
 
 FILE PERMISSIONS : write ('w') read('r') 
 how to check permission : ll
 create a shell file : provision.sh
 change permission : chmod persmission file-name
 example to change to executable files : chmod +x provision.sh
 


What is Devops?
Why devops/benefits ?
Role of the devops
What is development Environments?Why is it needed?
What are the 4 pillars of Devops ?-- diagram presentation !
