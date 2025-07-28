FROM ubuntu:22.04
ENV DEBIAN_FRONTEND=noninteractive

# Update & Install required packages
RUN apt-get update && \
    apt-get install -y python3 python3-pip openssh-server sudo && \
    pip3 install ansible && \
    mkdir /var/run/sshd && \
    useradd -m ansible && echo "ansible:ansible" | chpasswd && adduser ansible sudo

EXPOSE 22
CMD ["/usr/sbin/sshd", "-D"]
