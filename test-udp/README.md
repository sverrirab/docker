# Quick and easy UDP testing with Docker

Simple containers for checking network connectivity and speed.

For more information see for example: https://support.asperasoft.com/hc/en-us/articles/216126068-UDP-connectivity-testing


## Start the server

```
docker run --name test-udp-server -d -p 33001 sverrirab/test-udp
```

To find the IP-ADDRESS of the test-udp-server on the container network:

```
docker inspect --format '{{ .NetworkSettings.IPAddress }}' test-udp-server
```

## Start the client

```
docker run --name test-udp-client --rm -it sverrirab/test-udp -u -p 33001 -b 10M -c <IP-ADDRESS>
```

## Cleaning up

```
docker logs test-udp-server
docker stop test-udp-server
```