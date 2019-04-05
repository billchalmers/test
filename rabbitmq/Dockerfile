FROM rabbitmq:latest

#ENV RABBITMQ_VERSION 3.7.13

#ADD https://raw.githubusercontent.com/billchalmers/test/master/rabbitmq/rabbitmq-server.repo /etc/yum.repos.d/rabbitmq-server.repo
#ADD https://raw.githubusercontent.com/billchalmers/test/master/rabbitmq/erlang.repo /etc/yum.repos.d/erlang.repo

#RUN \
#  yum -q makecache -y fast && \
#  yum install -y epel-release && \
#  yum install -y rabbitmq-server-$RABBITMQ_VERSION && \
#  yum clean all

ADD https://raw.githubusercontent.com/billchalmers/test/master/rabbitmq/rabbitmq.config /etc/rabbitmq/
ADD https://raw.githubusercontent.com/billchalmers/test/master/rabbitmq/enabled_plugins /etc/rabbitmq/

EXPOSE 5672 15672
CMD ["rabbitmq-server"]