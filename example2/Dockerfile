FROM phusion/baseimage

ENV HOME /root

CMD ["/sbin/my_init"]

RUN apt-get update && apt-get install -y python
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
