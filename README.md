# servo-redis
_Optune adjust driver for Redis_

This driver updates Redis server settings in real-time (without server restart) using built-in command `CONFIG SET`. It only serves one Redis node. It does not flush the changes to the configuration file `redis.conf`.

__Note__ this driver requires `adjust.py` base class from the Optune servo core. It can be copied or symlinked here as part of packaging.

<!--
## Installation
1. Referring to `config.yaml.example` create file `config.yaml` in driver's folder. It will contain settings you'd want to make adjustable on your Redis instance.
1. Referring to `secret.yaml.example` create file `secret.yaml` in driver's folder. It will contain connection credentials to your Redis server.
1. Run bash command `docker build -t servo-redis .` to build driver's image.
1. Request access token file from us. Map it to `/run/secrets/optune_auth_token` with argument `-v /path/to/optune.token:/run/secrets/optune_auth_token` when running the driver. Ex. `docker run -d -v /path/to/optune.token:/run/secrets/optune_auth_token servo-redis`.
1. Run the driver using command `docker run -v /path/to/optune.token:/run/secrets/optune_auth_token -d servo-redis`.
-->