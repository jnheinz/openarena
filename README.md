# Docker SickRage

This is a Dockerfile to deploy OpenArena server.

## How to run

Here's how you can run the container :

```
docker run --restart=always --name openarena -d -p 27050:27050/udo -p 27060:27060 -v /etc/localtime:/etc/localtime:ro -v /<local-directory-for-config-files>:/data fgracia/openarena
```


Where :

* **--restart=always** : allows to automatically restart the container if it stops, of if the host reboots.
* **--name openarena** : you can choose the name that you want
* **-d** : - daemon mode
* **-p 27050:27050/udo -p 27060:27060** :  maps the defaults UDP ports 27050 and 27060.
* **-v /etc/localtime:/etc/localtime:ro** : sets the UTC like the host (optional)
* **-v /local-directory-for-config-files:/data** : if you want persistent config and map files, stored outside of your container. You can put all your maps in this folder.


## Docker Compose

Because of a pretty hard docker run command to remember, you can use docker-compose (see the docker-compose.yml script). 
You will juste have to adapt the data volume and then run :

```
docker-compose up -d
```

