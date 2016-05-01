FROM nuwanbando/javabase

RUN mkdir wso2 

COPY esb/pack/wso2esb-4.9.0.zip wso2/

RUN cd wso2/ && \
        unzip wso2esb-4.9.0.zip

COPY esb/conf/axis2.xml /wso2/wso2esb-4.9.0/repository/conf/axis2/
COPY esb/conf/carbon.xml /wso2/wso2esb-4.9.0/repository/conf/
COPY esb/conf/jmx.xml /wso2/wso2esb-4.9.0/repository/conf/etc/

CMD ["sh", "/wso2/wso2esb-4.9.0/bin/wso2server.sh","-Dcom.sun.management.jmxremote.port=9999","-Dcom.sun.management.jmxremote.authenticate=false","-Dcom.sun.management.jmxremote.ssl=false","-Dcom.sun.management.jmxremote.rmi.port=9999","-Djava.rmi.server.hostname=docker.machine"]]

EXPOSE 9763
EXPOSE 9443
EXPOSE 8280
EXPOSE 8243
EXPOSE 10397
EXPOSE 9999
EXPOSE 11111