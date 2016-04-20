#### Product Setup ####

The products in this directory are composed as docker containers. 

Before executing the scripts, please download the product distribution into the relevant pack directory

```
i.e ./apim/pack/
```

In order to run each of the product use the following command

```
Start All Product Containers

$docker-compose up -d
````

```
Start an individual product

$docker-compose up -d {esb|mb|apim|das}
```