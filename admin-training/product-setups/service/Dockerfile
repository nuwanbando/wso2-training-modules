FROM nuwanbando/javabase

RUN mkdir wso2

ENV ANT_VERSION 1.9.7

RUN cd && wget -q http://www.eu.apache.org/dist//ant/binaries/apache-ant-${ANT_VERSION}-bin.tar.gz && \
    tar xzf apache-ant-${ANT_VERSION}-bin.tar.gz && \
    mv apache-ant-${ANT_VERSION} /opt/ant && \
    rm -f apache-ant-${ANT_VERSION}-bin.tar.gz

ENV ANT_HOME /opt/ant
ENV PATH ${PATH}:/opt/ant/bin

COPY esb/pack/wso2esb-4.9.0.zip wso2/

RUN cd wso2/ && \
        unzip wso2esb-4.9.0.zip && \
        cd wso2esb-4.9.0/samples/axis2Server/src/SimpleStockQuoteService/ && \
        ant

CMD ["sh", "/wso2/wso2esb-4.9.0/samples/axis2Server/axis2server.sh"]

EXPOSE 9000
EXPOSE 9002