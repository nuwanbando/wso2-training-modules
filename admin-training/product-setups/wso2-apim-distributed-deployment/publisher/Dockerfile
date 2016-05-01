FROM nuwanbando/javabase

RUN mkdir wso2 

COPY packs/wso2am-1.10.0.zip wso2/

RUN cd wso2/ && \
        unzip wso2am-1.10.0.zip

COPY artifacts/mysql-connector-java-5.1.34-bin.jar /wso2/wso2am-1.10.0/repository/components/lib/
COPY publisher/api-manager.xml /wso2/wso2am-1.10.0/repository/conf/
COPY publisher/master-datasources.xml /wso2/wso2am-1.10.0/repository/conf/datasources/
COPY publisher/registry.xml /wso2/wso2am-1.10.0/repository/conf/
COPY publisher/user-mgt.xml /wso2/wso2am-1.10.0/repository/conf/
COPY publisher/axis2.xml /wso2/wso2am-1.10.0/repository/conf/axis2/

CMD ["sh", "/wso2/wso2am-1.10.0/bin/wso2server.sh"]

EXPOSE 9763
EXPOSE 9443
EXPOSE 8280
EXPOSE 8243
EXPOSE 10397