### This repository contains API Manager 1.10.0 distributed deployment for PoC / Demo purposes

Following instructions will help you to setup the deployment

1. Clone the repository to your local file system
2. Navigate to ``` packs/ ``` and copy ```wso2am-1.10.0.zip``` and ```wso2das-3.0.1.zip```
3. navigate into the parent directory (wso2-apim-distributed-deployment)
4. Execute ``` docker-compose up -d ```

This will setup 

* A mysql server (container) with apimdb / userdb / regdb
* A container for each API-M profile (apim-gateway / apim-keymanager / apim-store / apim-publisher)
* A container with DAS and configured for API statistics
