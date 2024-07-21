FROM ubuntu:20.04
RUN apt-get update && apt-get install -y curl sudo
RUN curl -L -O https://artifacts.elastic.co/downloads/beats/filebeat/filebeat-8.5.3-amd64.deb
RUN sudo dpkg -i filebeat-8.5.3-amd64.deb

# Copy your Filebeat configuration
COPY filebeat.yml /etc/filebeat/

RUN filebeat modules enable logstash
RUN sudo filebeat setup
RUN sudo service filebeat start
ENTRYPOINT ["/etc/filebeat/filebeat.yml"]
