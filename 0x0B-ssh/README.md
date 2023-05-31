0x0B-ssh

STEP 1. HOW TO GENERATE YOUR SSH KEY
Get your sandbox (UBUNTU 20.04)


cd /root

ssh-keygen -t rsa -b 4096 -f ~/.ssh/school


Your PASSPHRASE shoud BE: betty


ls -a

cd .ssh

vi  school.pub

Copy the RSA and save on your `INTRANET PROFILE`

Click `Save your information`

Then, go back to the project and scroll down

Just before TASK 0, 

Request for a new server

Make sure your server's state is `RUNNING`
HERE IS AN EXAMPLE
---
Name		Username	IP		State	
---
160670-web-01	ubuntu		54.208.69.207	running
---
STEP 2. HOW TO LOGIN TO YOUR SERVER
cd /root

cd .ssh

eval $('ssh-agent')

ssh-add ~/.ssh/school

PLEASE REPLACE THE IP ADDRESS BELOW WITH YOUR OWN IP ADDRESS

ssh ubuntu@54.208.69.207

NOTE: IF YOUR SERVER SAYS "PERMISSION DENIED",PLEASE DON'T FORCE THINGS
THERE'S PROBABLY SOMETHING WRONG WITH THE PUBLIC KEY YOU PASTED ON YOUR INTRANET PROFILE


I WILL ADVICE YOU TO BE MORE CAREFULL,BUT DELETE THE .SSH DIRECTORY AND START ALL OVER AGAIN FROM STEP 1.


OR YOU WILL JUST BE GOING IN AN ENDLES CIRCLE OF "PERMISSION DENIED"


THE COMMAND BELLOW IS FOR THOSE WHOSE SERVER IS SAYING "PERMISSION DENIED"

rm -r .ssh

BUT IF YOU HAVE SUCCESSFULLY CONNECTED TO YOUR SERVER, THEN CONTINUE THE FOLLOWING COMMANDS:

ls -a

cd .ssh

ls -a

sudo vim authorised_keys

Add the RSA public key from your project TASK 3 to your authorized_keys file

Save and exit

THEN CHECK YOUR CODE FOR TASK 3

STEP 3. OPEN ANOTHER SANDBOX
cd  alx-system_engineering-devops

mkdir 0x0B-SSH

cd 0x0B-SSH

Create a README.md file with some content in it

