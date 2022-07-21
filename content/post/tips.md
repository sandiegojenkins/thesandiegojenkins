---
title: "Tips"
date: 2022-05-19T11:54:49-07:00
draft: false
---

## Useful information

This post is mostly for me. These are some items that I find myself looking up. It happens with those commands and task that I only use every 3 months or so. 

## Docker
I often pull down new images and don't want the old ones taking up space. To remove them I prune them with a -a to get rid of all stopped containers, all networks that aren't used, all images that aren't used and the cache. 
```
docker system prune -a
```
Run docker images to see all of the images before and after you prune. 
```
docker images
```
```
REPOSITORY                                 TAG                  IMAGE ID       CREATED         SIZE
crestsystems/netskope                      core-3.3.1           8e2258a3198f   7 days ago      584MB
netskopetechnicalalliances/cloudexchange   core3-beta           8e2258a3198f   7 days ago      584MB
crestsystems/netskope                      ui-3.3.1             eb6d0f317c07   7 days ago      29.5MB
netskopetechnicalalliances/cloudexchange   ui3-beta             eb6d0f317c07   7 days ago      29.5MB
bitnami/mongodb                            4.4                  0c082ae84907   7 days ago      583MB
bitnami/rabbitmq                           3.8                  ac5fd3c269bf   7 days ago      221MB
bitnami/rabbitmq                           <none>               6e4eacceaf9d   2 weeks ago     221MB
bitnami/mongodb                            <none>               a4fced1850f0   2 weeks ago     583MB
bitnami/rabbitmq                           <none>               7bea80a275ad   3 weeks ago     221MB
bitnami/rabbitmq                           <none>               01e320b0399e   4 weeks ago     221MB
bitnami/mongodb                            <none>               1fc49bc75137   4 weeks ago     432MB
netskopetechnicalalliances/cloudexchange   core3-latest         6dc9f86f827a   4 weeks ago     564MB
bitnami/rabbitmq                           3.9                  bee9fff5a877   4 weeks ago     231MB
crestsystems/netskope                      core-s36-3.2.0_292   0007384e64c1   5 weeks ago     564MB
netskopetechnicalalliances/cloudexchange   <none>               af2cbfab6b6e   6 weeks ago     564MB
netskopetechnicalalliances/cloudexchange   ui3-latest           e6b7cc83a33f   6 weeks ago     29.5MB
netdata/netdata                            latest               eccf6965171c   6 months ago    367MB
containrrr/watchtower                      1.3.0                dd78a816fb76   13 months ago   16.4MB
traefik                                    v2.3                 70860b377f5f   20 months ago   92.1MB
```
and after
```
ubuntu@ip-10-0-0-207:~$ docker images
REPOSITORY                                 TAG            IMAGE ID       CREATED         SIZE
bitnami/mongodb                            4.4            0c082ae84907   7 days ago      583MB
bitnami/rabbitmq                           3.8            ac5fd3c269bf   7 days ago      221MB
netskopetechnicalalliances/cloudexchange   core3-latest   6dc9f86f827a   4 weeks ago     564MB
netskopetechnicalalliances/cloudexchange   ui3-latest     e6b7cc83a33f   6 weeks ago     29.5MB
netdata/netdata                            latest         eccf6965171c   6 months ago    367MB
containrrr/watchtower                      1.3.0          dd78a816fb76   13 months ago   16.4MB
traefik                                    v2.3           70860b377f5f   20 months ago   92.1MB
ubuntu@ip-10-0-0-207:~$
```

## SCP
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

## Ubuntu commands

To delete a directory that has files in it. 
```
rm -rf <folder>/
``` 
