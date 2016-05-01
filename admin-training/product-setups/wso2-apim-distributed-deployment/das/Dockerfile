FROM nuwanbando/javabase

RUN mkdir wso2 

COPY packs/wso2das-3.0.1.zip wso2/

RUN cd wso2/ && \
        unzip wso2das-3.0.1.zip

COPY artifacts/mysql-connector-java-5.1.34-bin.jar /wso2/wso2das-3.0.1/repository/components/lib/
COPY das/analytics-datasources.xml /wso2/wso2das-3.0.1/repository/conf/datasources/
COPY das/API_Manager_Analytics_REST.car /wso2/wso2das-3.0.1/repository/deployment/server/carbonapps/

CMD ["sh", "/wso2/wso2das-3.0.1/bin/wso2server.sh"]

EXPOSE 9763
EXPOSE 9443
EXPOSE 7611
EXPOSE 7711