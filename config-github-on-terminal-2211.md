## Config your GitHub account on a Linux machine

🐼 : _I know there are many manuals to do this, and the day I am writing this, I was not expecting to waste two hours in the process._

🐼 : _Hope this will save a few hours of your precious time_

Because I love helping and making instructions, here is the link to the place that actually helps me to configure my Github account on my Linux terminal:

[SOURCE](https://www.makeuseof.com/install-configure-git-on-linux/)

So I assume you already install GitHub. If not,  read the source from the beginning.

Now just run 

### FIRST STEP: config user and generate key
+ ``git config user.name "your_name"`` //here I used Sofi1410
+ `git config user.email "your_email_address" ` //the one connected to GitHub
+ `ssh-keygen -t rsa -b 4096 -C "your_email_address" `//same , just press enter if don+t want to complicate your life
+ `ssh-add ~/.ssh/id_rsa.pub  `  //if it does not run, check the name of the key created

### SECOND STEP: GitHub account settings, add the SSH KEY
Then go to your GitHub account and add the SSH key. 
+ To do that, you have to copy your key. 
  You can use the command [pbcopy](https://ostechnix.com/how-to-use-pbcopy-and-pbpaste-commands-on-linux/) and  
  execute `pbcopy < ~/.ssh/id_rsa.pub`  //again here you might need to change the name

+ Now the ssh key is on your clipboard.
+ Go to your GitHub account on your browser > Settings > SSH and GPG keys > New ssh Key
+ Use a name related to the machine you are using (just a suggestion. You can do whatever you want ) 
+ Paste what is on your clipboard, it is going to be nasty, and it should end with your email

### THIRD STEP: Check
+ run `ssh -T git@github.com` to check if it worked
+ If you read: "Hi Sofi1410! You've successfully authenticated, but GitHub does not provide shell access." everything is fine
+ else ... cry.


### UPDATE: Problem when keeps asking for credentials while cloning
If keeps asking for your username and password (even if you enter the right information won+t work) is because youa re clonning the repo using th HTTP instead use the SSH options and all problems should be fix :) 

`git clone git@github.com:user/repo.git`





🐼 :_Best, [Sofi](https://github.com/Sofi1410)_
