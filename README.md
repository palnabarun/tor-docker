# Tor Proxy

This is a simple and lightweight Docker image for running a Tor proxy.

The base image used is `alpine`.

# Usage

It is pretty simple to run and has some sane defaults.

```
$ docker run \
    --rm \
    --detach \
    --name tor \
    --publish 9050:9050 \ # change the port to whatever you put in the torrc
    palnabarun/tor
...
```

The Tor proxy would be coming up shortly after establishing a Tor circuit.

If you want to customize the Tor configuration, create a `torrc` locally and the mount the same as a volume.

```
$ docker run \
    --rm \
    --detach \
    --name tor \
    --volume $PWD/torrc:/etc/tor/torrc
    --publish 9050:9050 \ # change the port to whatever you put in the torrc
    palnabarun/tor
...
```

The options in `torrc` are documented [here](https://2019.www.torproject.org/docs/tor-manual.html.en)

# Contributing

Please feel free to create issues and file PRs with any change that you wish to see.

# License

The repository is licensed under [GPLv3](https://choosealicense.com/licenses/gpl-3.0).
