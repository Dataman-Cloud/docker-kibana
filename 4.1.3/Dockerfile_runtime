# Pull base image.
FROM demoregistry.dataman-inc.com/library/centos7-base:latest

MAINTAINER Jinye Liu "jyliu@dataman-inc.com"

ENV KIBANA_PKG_NAME=kibana-4.1.3-linux-x64
ENV ES_HOME=/usr/share/kibana
ENV PATH=$ES_HOME/bin:$PATH

# Install kibana
RUN curl  -o $KIBANA_PKG_NAME.tar.gz https://download.elastic.co/kibana/kibana/$KIBANA_PKG_NAME.tar.gz && tar xzf $KIBANA_PKG_NAME.tar.gz -C /usr/share/ && rm -f $KIBANA_PKG_NAME.tar.gz && mv /usr/share/$KIBANA_PKG_NAME /usr/share/kibana
#ADD $KIBANA_PKG_NAME.tar.gz /usr/share/
#RUN mv /usr/share/$KIBANA_PKG_NAME /usr/share/kibana

COPY entrypoint.sh /
RUN chmod +x *.sh

# Define working directory.
WORKDIR  /usr/share/kibana

# Define default command.
ENTRYPOINT ["/entrypoint.sh"]

