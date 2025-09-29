FROM ubuntu:24.04

# Install SSH server and Redis CLI
RUN apt update && \
    apt install -y openssh-server redis-tools sudo && \
    mkdir /var/run/sshd

# Set root password
RUN echo 'root:root' | chpasswd

# Allow root login
RUN sed -i 's/#PermitRootLogin prohibit-password/PermitRootLogin yes/' /etc/ssh/sshd_config

# Expose SSH port
EXPOSE 22

# Start SSH daemon
CMD ["/usr/sbin/sshd", "-D"]
