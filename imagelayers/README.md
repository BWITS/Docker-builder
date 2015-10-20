### build imagelayers api in golang docker environment

```
docker build --no-cache -t imagelayers . 
docker run -d imagelayers 
docker cp <CONTAINER_ID>:/go/bin/imagelayers .
```

Read detail at https://github.com/CenturyLinkLabs/imagelayers/blob/master/README.md#installation
