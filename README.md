# redis-consul - Self-Registering Redis Container

## Description
This image contains a compiled version of Redis 3.0.7 installed into Alpine Linux. It is accompanied by Containerbuddy, which handles health checks and Consul registration.

## Environment Variables
This image can utilise the following variables

* ```CONSUL_ADDRESS``` sets the address of the Consul instance to register against. This should be in the form of ```hostname:8500``` such as ```discovery.provider.com:8500```. 