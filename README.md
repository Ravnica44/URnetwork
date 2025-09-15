https://app.ur.network/
https://docs.ur.io/provider

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

```shell
docker run --rm bringyour/community-provider:g4-latest --help
Connect provider.

The default URLs are:
    api_url: https://api.bringyour.com
    connect_url: wss://connect.bringyour.com

Usage:
    provider auth ([<auth_code>] | --user_auth=<user_auth> [--password=<password>]) [-f]
        [--api_url=<api_url>]
        [--max-memory=<mem>]
        [-v...]
    provider provide [--port=<port>]
        [--api_url=<api_url>]
        [--connect_url=<connect_url>]
        [--max-memory=<mem>]
        [-v...]
    provider auth-provide ([<auth_code>] | --user_auth=<user_auth> [--password=<password>]) [-f]
        [--port=<port>]
        [--api_url=<api_url>]
        [--connect_url=<connect_url>]
        [--max-memory=<mem>]
        [-v...]
    provider proxy auth add [<key>] <proxy_user> <proxy_password> [-f]
    provider proxy auth remove [<key>] [--all]
    provider proxy add [<key_address>...] [--proxy_file=<proxy_file>] [-f]
    provider proxy remove [<key_address>...] [--all]

Options:
    -h --help                        Show this help and exit.
    --version                        Show version.
    -v...                            Enable verbose mode. -v implies verbose level 1,
                                                 -vv implies level 2... etc.
    -f                               Force overwrite the JWT token store file or proxy value, if exists.
                                     By default, existing values will not be overwritten.
    --api_url=<api_url>              Specify a custom API URL to use.
    --connect_url=<connect_url>      Specify a custom connect URL to use.
    --user_auth=<user_auth>              Login with a username.
    --password=<password>            Login with a password. If --user_auth is used, you will be prompted for your
                                                 password anyways, if you don't specify it using this option.
    -p --port=<port>                 Status server port [default: 0].
    --max-memory=<mem>               Set the maximum amount of memory in bytes, or the suffixes b, kib, mib, gib may be used [This is a soft limit].
    <key>                            Authentication key
    <proxy_user>                     SOCKS5 user
    <proxy_password>                 SOCKS5 password
    <key_address>                    SOCKS5 server as host:port, host:port:user:pass, host:port::, or key@host:port
    --proxy_file=<proxy_file>        A path to a file where each line contains on entry as host:port, host:port:user:pass, host:port::, or key@host:port
```
