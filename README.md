## Docker

List Docker containers:

```bash
sudo docker ps
```

Log into container:

```bash
sudo docker exec -it [container id] /bin/bash
```

Restart Docker container:

```bash
sudo docker restart [container id]
```

Commit changes to a Docker container (if you need to edit the files on a live container, you'll have to restart the container after committing for any code that is already running to be restarted):

```bash
sudo docker commit [container id]
```

## Dokku

