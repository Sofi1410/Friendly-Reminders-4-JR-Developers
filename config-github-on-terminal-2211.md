## Config your github account on a Linux machine

🐼 : _I know, there are many manuals to do this, and the day I am writing this I was not expecting to waste two hours in the process._

🐼 : _Hope this will save a few hours of your precious time_

Because I love helping and making instructions here is the link to the place that actually help me tyo configure my Github account on my Linux terminal:

[SOURCE](https://www.makeuseof.com/install-configure-git-on-linux/)

So I assume you already install github if not read the source since the beginning.

Now just run 

### FIRST STEP: config user and generate key
+ ``git config user.name "your_name"`` //here I used Sofi1410
+ `git config user.email "your_email_address" ` //the one connected to GIthub
+ `ssh-keygen -t rsa -b 4096 -C "your_email_address" `//same , just press enter if don+t want to complicate your life
+ `ssh-add ~/.ssh/id_rsa.pub  `  //if does not run checked the name of the key created

### SECOND STEP: Github account settings, add the SSH KEY
Then go to your github account and add the SSH key. 
+ To do that you have to copy your key. 
  You can use the command [pbcopy](https://ostechnix.com/how-to-use-pbcopy-and-pbpaste-commands-on-linux/) and  
  execute `pbcopy < ~/.ssh/id_rsa.pub`  //again here you might need to change the name

+ Now the ssh key is on yout clipboard.
+ Go to your github account on your browser > Settings > SSH and GPG keys > New ssh Key
+ Use a name related to the machine you are using (just a suggestion you can do whatever you want ) 
+ Paste what is on your clipboard, is going to be nasty and it should end with your email

### THIRD STEP: Check
+ run `ssh -T git@github.com` to check tif it worked
+ If you read: "Hi Sofi1410! You've successfully authenticated, but GitHub does not provide shell access." everything is fine
+ else ... cry.


🐼 :_Best, [Sofi](https://github.com/Sofi1410)_
