FROM debian:12

RUN apt update &&\
    apt install -y systemd systemd-sysv openssh-server &&\
    sh -c '(echo root; echo root) | passwd'


#  users will likely be unhappy that they cant apt get immediately, so we leave this trash around:
#  rm -rf /var/lib/apt/lists/*

CMD ["/sbin/init"]
