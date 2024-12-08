# Docker

## Use docker without always having to sudo
`sudo usermod -aG docker <username>`

## simple test
`docker run hello-world`

## Common commands
### list images that are available locally
`docker images`

### look for images
`docker search <keyword>`

### download image
`docker pull <image name>`

### run a container
`docker run <image ID>`
will exit itself if no jobs

### list containers
`docker ps -a`
shows list of containers running/were running

### Remove
`docker rm <container name>`  remove containers
`docker rmi <image name>` remove image

## Interactive mode
`docker -it --rm -v <local dir>:<container dir> --entrypoint "/bin/bash" <image name>`
use this to test images
--rm removes the container on exit
-it enters interactive mode
-v mount host folder to container
-d detached mode, sends interactive mode to background

### attach terminal to running container
`docker attach <containerID>'
use `ctrl+pq` instead of exit while inside the container so it doesnt stop

## Dockerfile
### Build custom images using dockerfile
`docker build -f <dockerfilename>  <path>`

### tag docker file
`docker tag <imageID>     <remote repo>:<user defined name for image>'
tags an image with name and repo to be deployed

### push image to repo
`docker push <repo path>:<imagetagname>`

## Docker example commands
`docker run -it -d --restart unless-stopped -p 8080:80 nginx
