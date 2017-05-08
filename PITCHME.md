--- 

Feed The Beast 

Restore Backup from world

---

### Make sure you have a Backup

I am using a "Feed the Beast" Server inside a docker container. My actuall server modpack comes with **FTB Utilities** which does backups automaticly.

*Make sure you have a modpack that does backups*

---

### Persist your data

To make your data persistent when using a docker container for your minecraft server, make sure you use the **--volume / -v** option when starting the minecraft server with docker

```
docker run -d --name mc-server -v /path/on/host:/data -p 25565:25565 itzg/minecraft-server
```
---

### Get your backup

In my case I need my backup because there was a dive dropped by a mob and I did not know what the dice does. After placing the dice block I got a wither spawnd. Not good at the very beginnig of **Sky Factory 3** so my sky island was blown down.

The backup will be stored in */path/on/host/*FeedTheBeast/backups/*Year-Month-Day-Hour-Minute-Second.zip*

---

Have fun!
