# servo-redis
Optune adjust driver for Redis

Note: this driver requires `measure.py` base class from the Optune servo core. It can be copied or symlinked here as part of packaging.

## Installation
1. Pull
2. Create config.yaml referring to config.yaml.example
    * **maxmemory** section: `min`, `max` and `step` settings are required. You can read more about them in the section `redis.maxmemory` below.
3. Make sure you set initial values for `maxmemory` and `maxmemory-policy` using command `CONFIG SET`. Ex. `redis-cli CONFIG SET maxmemory 1g` and `redis-cli CONFIG SET maxmemory-policy allkeys-random`. It'd be good to determine your current memory usage and use that as a starting point for `maxmemory` setting. If you're not aware of your usecase's access pattern - we'd recommend to start with `allkeys-random`.
4. Run the driver
5. 🍾🥂

## config.yaml options
### redis.connection
In this section you can define credentials to be used to connect to your redis node. You can refer to config.yaml.example for more information.

### redis.maxmemory
To understand the limits of your redis node please define the following keys - min, max and step.
* **min** - minimum amount of memory available for cluster's dataset in megabytes, ex. 128
* **max** - maximum amount of memory available for cluster's dataset in megabytes, ex. 6144 (so we know the boundaries).
Typically you may want to specify 90% of available instance memory.
* **step** - how big is a step of memory increase in megabytes, ex. 128
