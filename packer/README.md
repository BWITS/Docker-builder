## Build packer with Docker
Packer source code can be found at https://github.com/mitchellh/packer, easily build in alpine and Debina Linux with Docker.

### Build packer in Alpine linux

Notes: The packer built in alpine linux can be run in Mac OS directly.

```
cd alpine
docker build -t packer:alpine .
docker run -d packer:alpine bash

# Copy the compiled packer to your local disk.
docker cp <CONTAINER_ID>:/go/src/github.com/mitchellh/packer/bin . 
```
### Build packer in Debian linux (the official golang docker image)

```
cd debian
docker build -t packer:golang . 
docker run -d packer:golang bash
docker cp <CONTAINER_ID>:/go/src/github.com/mitchellh/packer/bin .
```

Now you have packer and its plugins compiled from source code in your local disk.

### Recommand to add --no-cache option when do the building, you will get the latest packer always.
