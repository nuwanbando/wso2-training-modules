FROM nuwanbando/javabase

RUN mkdir wso2 

COPY esb/pack/wso2esb-4.9.0.zip wso2/

RUN cd wso2/ && \
        unzip wso2esb-4.9.0.zip

CMD ["sh", "/wso2/wso2esb-4.9.0/bin/wso2server.sh"]

EXPOSE 9763
EXPOSE 9443
EXPOSE 8280
EXPOSE 8243
EXPOSE 10397