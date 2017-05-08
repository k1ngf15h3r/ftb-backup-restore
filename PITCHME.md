--- 

Feed The Beast 

Restore your world from backup

---

#### Make sure you have a Backup

I am using a "Feed the Beast" Server inside a docker container. My actuall server modpack comes with **FTB Utilities** which does backups automaticly.

*Make sure you have a modpack that does backups*

---

#### Persist your data

To make your data persistent when using a docker container for your minecraft server, make sure you use the **--volume / -v** option when starting the minecraft server with docker

```
docker run -d --name mc-server -v /path/on/host:/data -p 25565:25565 itzg/minecraft-server
```
---

#### Get your backup

In my case I need my backup because there was a dive dropped by a mob and I did not know what the dice does. After placing the dice block I got a wither spawnd. Not good at the very beginnig of **Sky Factory 3** so my sky island was blown down.

The backup will be stored in */path/on/host/*FeedTheBeast/backups/*Year-Month-Day-Hour-Minute-Second.zip*

---

#### Restore your world

First stop your minecraft server. `docker stop mc-server`

save your actuall world `mv world world.bak` inside */path/on/host/FeedTheBeast/*

Unzip backup to */path/on/host/FeedTheBeast/* 

+++

check the permissions of the restored **world** folder. 

In my case I had to `chown -R 1000:1000 world/`. 

Check other folders with `ls -lA` inside */path/on/host/FeedTheBeast*

+++

if server start fails `docker start mc-server` check the logs with `docker logs mc-server`

maybe you have to `mv session.lock session.bak` inside the restored **world** folder

---

Have fun with your restored world again!
