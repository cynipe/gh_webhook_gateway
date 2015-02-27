# Github Webhook Gateway Example

## Requirements

* docker
* docker-compose

```
# boot instance
$ docker-compose up -d

# send test webhook with valid content
$ brew install httpie
$ http -v POST 192.168.59.103 'Content-Type:application/json' 'X-Hub-Signature:sha1=0567bf10a3ebdba96ee7c41268a2ecb570109e76' <<_EOM
abcd
_EOM

# send test webhook with invalid content
$ brew install httpie
$ http -v POST 192.168.59.103 'Content-Type:application/json' 'X-Hub-Signature:sha1=0567bf10a3ebdba96ee7c41268a2ecb570109e76' <<_EOM
invalid
_EOM

# access gateway directly
open http://your.docker.host

# access jenkins directly
open http://your.docker.host:8080
```
