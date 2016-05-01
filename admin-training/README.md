#### This directory contains the training modules for WSO2 Product Administration workshops ####

By navigating to ```product-setup``` you can find the guide to setting up relevant products

Following are the standard lab setup guides

* LAB Settup-1: Environment setup
	
	1. Setting up the docker environment
		- `docker-compose images` - will show all avaible images
		- `docker-compose up -d esb` - will create the esb image and boot it up

	2. Installing the diployable archive
		- navigate to `./artifacts/<>.car`
		- point the browser to `https://docker.machine:9444/carbon/` and login in to the management console with admin/admin
		- navigate to `Carbon Application --> add` in the menue items
		- upload the `.car`

	3. Health check
		- navigate to `` if you get 200K the service is running

	4. Looking at ESB logs
		- `docker exec -it tail -f wso2/wso2esb-4.9.0/repository/logs/wso2carbon.log` will tail the log file to the running console

	5. Analizing wire logs

	6. Taking a memory dump
	
