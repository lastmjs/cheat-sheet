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

Commit changes to a Docker image (if you need to edit the files on a live container, you'll have to restart the container after committing for any code that is already running to be restarted):

```bash
sudo docker commit [container id]
```

Get container info such as the IP address:

```bash
sudo docker inspect [container id]
```

## Dokku

To make live changes to a Dokku application:

1. Log into the container
2. Make the changes
3. Commit the changes to the Docker image
4. Restart the container
5. Change the `nginx.conf` on the host server for Dokku. `/home/dokku/[app name]/nginx.conf`. Change the upstream ip address to the ip address of the container
6. Restart nginx: `sudo service nginx reload`

## AWS

Log into server:

```bash
ssh -i ~/.ssh/[private key name].pem ubuntu@[server ip or domain name]
```

## Git

Remove a directory completely from git history (https://stackoverflow.com/a/17824718/2196424):

``` bash
git filter-branch --tree-filter "rm -rf [directory name]" --prune-empty HEAD
git for-each-ref --format="%(refname)" refs/original/ | xargs -n 1 git update-ref -d
git commit -m "Removing [directory name] from git history"
git gc
git push origin master --force
```
