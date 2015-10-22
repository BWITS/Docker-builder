## build packer with Docker
Packer source code can be found at https://github.com/mitchellh/packer, build in alpine and Debina easily with Docker.

### Build packer in Alpine linux

Notes: The packer built in alpine linux can be run in Mac OS directly

```
docker build -f Dockerfile.alpine -t packer:alpine .
docker run -d packer:alpine bash
docker cp <CONTAINER_ID>:/go/src/github.com/mitchellh/packer/bin . 
```
### Build packer in Debian linux (the official golang docker image)

```
docker build -f Dockerfile.golang -t packer:golang . 
docker run -d packer:golang bash
docker cp <CONTAINER_ID>:/go/src/github.com/mitchellh/packer/bin .
```

Now you have packer and its plugins compiled from source code.

