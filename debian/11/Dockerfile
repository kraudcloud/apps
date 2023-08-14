FROM debian:11

RUN apt update &&\
    apt install -y systemd systemd-sysv openssh-server &&\
    systemctl disable systemd-resolved &&\
    systemctl mask systemd-resolved &&\
    sh -c '(echo root; echo root) | passwd'


#  users will likely be unhappy that they cant apt get immediately, so we leave this trash around:
#  rm -rf /var/lib/apt/lists/*

CMD ["/sbin/init"]
