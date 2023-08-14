FROM opensuse/leap:15.5

RUN zypper ref&&\
    zypper install -y systemd systemd-sysvinit openssh &&\
    systemctl enable sshd &&\
    systemctl disable systemd-resolved &&\
    systemctl mask systemd-resolved &&\
    sh -c '(echo root; echo root) | passwd'


#  users will likely be unhappy that they cant apt get immediately, so we leave this trash around:
#  rm -rf /var/lib/apt/lists/*

CMD ["/sbin/init"]
