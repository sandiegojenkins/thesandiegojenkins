---
title: "Tips"
date: 2022-04-16T11:54:49-07:00
draft: false
---

## Useful information

This post is mostly for me. These are some items that I find myself looking up a lot. It happens with those commands and task that I only use every 3 months or so. 

### SCP
As I am working with servers in the cloud or in a docker folder, I find myself needed to get files to or from the server I am working on. 

#### While on my laptop and getting a folder from a server on AWS 

Start with the scp command followed by a -i since I am using my personal key (mycer.cer)
Then the name of the server with the path and file name that you want
To finish it off add where you want it to go and what name it will have
```
scp -i mycer.cer root@someserver.tech:/home/ubuntu/backup1.zip \SCP_Root\backup1.zip
```

#### Sending a file from a local server to a local computer

I am already in the folder that holds the log.zip file in this example. I am sending my file to my computer with ip address 10.10.10.111
```
scp log.zip username@10.10.10.111:/logs.zip
``` 