#### Product Setup ####

Product setup directory have pre-congigured individual WSO2 products as well as products groupings. 

Following instructions will help to setup the products and solutions.

Basic commands that will be helpful 

```
docker-compose up -d {esb|mb|apim|das|service} - Will start any of the individual produt in its own container.

docker-compose ps - Will list all running containers

docker-compose down --rmi all - will kill all container and remove the associated docker images

docker-compose kill {esb|mb|apim|das|service} - will kill any of the docker container
```

Before executing the scripts, please download the product distribution into the relevant pack directory

```
i.e ./apim/pack/

```

For API Manager distributed setup the packs needed to be copied to 

```
./wso2-apim-distributed-deployment/packs/
```

If the docker host is running in a VM the, there should be a host mapping 

```
<docker machine ip> docker.machine
```

To profile the product you can connect to it via JMX

```
service:jmx:rmi://docker.machine:11111/jndi/rmi://docker.machine:9999/jmxrmi
```