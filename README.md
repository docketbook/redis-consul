# redis-consul - Self-Registering Redis Container

## Description
This image contains a compiled version of Redis 3.0.7 installed into Alpine Linux. It is accompanied by Containerpilot, which handles health checks and Consul registration. The Redis data is stored at ```/data``` which is designated as a volume.

## Environment Variables
This image can utilise the following variables

* ```CONSUL_ADDRESS``` sets the address of the Consul instance to register against. This should be in the form of ```hostname:8500``` such as ```discovery.provider.com:8500```. 

## Important Ports

* ```tcp/6379``` the port on which Redis is listening

## Data Directories

* ```/data``` Designated as a separate volume in which Redis stores any persistent data
