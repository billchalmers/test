# Wazuh App Copyright (C) 2019 Wazuh Inc. (License GPLv2)
FROM docker.elastic.co/elasticsearch/elasticsearch:6.5.4

ENV ALERTS_SHARDS="1" \
    ALERTS_REPLICAS="0"

ENV API_USER="foo" \
    API_PASS="bar"

ENV XPACK_ML="true" 

ENV ENABLE_CONFIGURE_S3="false"

ENV TEMPLATE_VERSION=v3.8.2

ADD https://raw.githubusercontent.com/wazuh/wazuh/$TEMPLATE_VERSION/extensions/elasticsearch/wazuh-elastic6-template-alerts.json /usr/share/elasticsearch/config

ADD https://raw.githubusercontent.com/billchalmers/test/master/elasticsearch/entrypoint.sh /entrypoint.sh

RUN chmod 755 /entrypoint.sh

ADD https://raw.githubusercontent.com/billchalmers/test/master/elasticsearch/load_settings.sh /load_settings.sh

RUN chmod +x /load_settings.sh

RUN elasticsearch-plugin install --batch repository-s3

ADD https://raw.githubusercontent.com/billchalmers/test/master/elasticsearch/configure_s3.sh /configure_s3.sh

RUN chmod 755 /configure_s3.sh

VOLUME /var/lib/elasticsearch

ENTRYPOINT ["/entrypoint.sh"]
CMD ["elasticsearch"]
