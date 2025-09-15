```shell
docker run -it \
  --name URnetwork \
  -v /var/run/docker.sock:/var/run/docker.sock \
  -v $HOME/.urnetwork:/root/.urnetwork \
  -h URnetwork \
  ubuntu:25.04 bash
```

`docker run -it --mount type=bind,source=$HOME/.urnetwork,target=/root/.urnetwork bringyour/community-provider:g4-latest auth`

`docker run --mount type=bind,source=$HOME/.urnetwork,target=/root/.urnetwork --restart always -d bringyour/community-provider:g4-latest provide`
