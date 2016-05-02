#### This directory contains the training modules for WSO2 Product Administration workshops ####

By navigating to ```product-setup``` you can find the guide to setting up relevant products

Following are the standard lab setup guides

**LAB Settup-1:** Environment setup
	
	1. Setting up the docker environment
		- `docker-compose images` - will show all avaible images
		- `docker-compose up -d esb` - will create the esb image and boot it up

	2. Installing the diployable archive
		- navigate to `./artifacts/<>.car`
		- point the browser to `https://docker.machine:9444/carbon/` and login in to the management console with admin/admin
		- navigate to `Carbon Application --> add` in the menue items
		- upload the `.car`

	3. Health check
		- navigate to `http://docker.machine:8281/services/Version?wsdl` if you get 200 OK the service is running

	4. Looking at ESB logs
		- `docker exec -it tail -f wso2/wso2esb-4.9.0/repository/logs/wso2carbon.log` will tail the log file to the running console

	5. Analizing wire logs
		- navigate to `configure->logging` from management console
		- search for `wire` and enable debug for `org.apache.synapse.transport.http.wire` class

	6. Analizing the JVM with JMX console
		- use visualVM / JConsole / jmc and connect to esb's jmx `service:jmx:rmi://docker.machine:11111/jndi/rmi://docker.machine:9999/jmxrmi`

**LAB Setup-2:** API Manager distributed deployment
	
	1. Navigate to `wso2-training-modules/admin-training/product-setups/wso2-apim-distributed-deployment`
	2. Start the setup with `docker-compose up -d`

**LAB Setup-3:** Monitoring with DAS

	1. Start WSO2 Data Analytics Server `docker-compose up -d das`
	2. Navigate to `http://docker.machine:9447/carbon`
	
**LAB Setup-4:** Connecting ESB with MB as a subscriber

	1. Start WSO2 ESB `docker-compose up -d esb`. This will also start the WSO2 MB internally.
	2. Navigate to `http://docker.machine:9444/carbon` (ESB admin console)
	3. Upload the `SampleCompositeApp_1.0.0.car` via the ESB admin console
		- `Main->Manage->Carbon Application->Add`
		- Observe ESB logs
	4. Navigate to `http://docker.machine:9446/carbon` (MB admin console)
	5. List `Queues`
		- `Main->Queues->list`
	6. Publish messages to `ordersQueue`
		- Click `Publish messages`
		- `Number of messages = 1`
		- `Message Body = {"id":1,"name":"A green door","price":12.5,"tags":["home","green"]}`
		- Click `Send Message`
	7. Observe ESB logs
	
**LAB Setup-5:** Connecting ESB with MB as a publisher

	1. Open `http://docker.machine:8281/services/jms-publisher-http-proxy?wsdl` with SOAP UI
	2. publish a mesage
		<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/">
   		    <soapenv:Header/>
   		    <soapenv:Body>
   		    	<mtn:getSalesRecords xmlns:mtn="http://www.salesorg.com">
         	        	<mtn:reference>N435UA</mtn:reference>
      		    	</mtn:getSalesRecords>
   		    </soapenv:Body>
		</soapenv:Envelope>
	3. Navigate to `http://docker.machine:9446/carbon` (MB admin console)
	4. Observe what has been added to `example.SampleQueue`
	
