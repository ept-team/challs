# sudo docker build -t www .
# sudo docker run -d -p 1024:1024 --rm -it www

FROM ubuntu:21.04

RUN apt-get update

RUN useradd -d /home/ept/ -m -p ept -s /bin/bash ept
RUN echo "ept:ept" | chpasswd

WORKDIR /home/ept

COPY ynetd .
COPY flag.txt /opt/flag
COPY www .

RUN chown -R root:root /home/ept
RUN chmod -R a+rx /home/ept

USER ept
CMD ./ynetd ./www
