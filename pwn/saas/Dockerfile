# sudo docker build -t saas .
# sudo docker run -d -p 1024:1024 --rm -it saas

FROM ubuntu:21.04

RUN apt-get update

RUN useradd -d /home/ept/ -m -p ept -s /bin/bash ept
RUN echo "ept:ept" | chpasswd

WORKDIR /home/ept

COPY ynetd .
COPY flag.txt /opt/flag
COPY saas .
COPY art.txt .

RUN chown -R root:root /home/ept
RUN chmod  -R a+rx /home/ept
USER ept
CMD ./ynetd ./saas
