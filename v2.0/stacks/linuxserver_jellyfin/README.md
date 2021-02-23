# Note: Jellyfin via docker-compose on Synology
- Install the **Docker** Package using **Package Center**

- The Synology **Docker** Package places the volumes in a custom location, **/volume1/@docker/volumes**

Once logged in as "root" user:
- To Run Jellyfin:

```
docker run -d \
  --name=jellyfin \
  -e PUID=0 \
  -e PGID=65536 \
  -e TZ=America/Chicago \
  -p 8096:8096 \
  -v /volume1/docker/jellyfin:/config \
  -v /volume1/video:/data/video \
  -v /volume1/music:/data/music \
  --device /dev/dri:/dev/dri \
  --restart unless-stopped \
  ghcr.io/linuxserver/jellyfin
```
