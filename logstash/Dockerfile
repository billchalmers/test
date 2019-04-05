# Wazuh App Copyright (C) 2019 Wazuh Inc. (License GPLv2)
FROM docker.elastic.co/logstash/logstash:6.5.4

ADD --chown=logstash:logstash https://raw.githubusercontent.com/billchalmers/test/master/logstash/entrypoint.sh /entrypoint.sh

RUN chmod 755 /entrypoint.sh

RUN rm -f /usr/share/logstash/pipeline/logstash.conf

ADD --chown=logstash:logstash https://raw.githubusercontent.com/billchalmers/test/master/logstash/01-wazuh.conf /usr/share/logstash/pipeline/01-wazuh.conf

ENTRYPOINT /entrypoint.sh