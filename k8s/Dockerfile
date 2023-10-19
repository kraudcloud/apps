FROM debian:12

RUN apt update &&\
    apt upgrade -y &&\
    apt install -y systemd systemd-sysv ca-certificates

COPY k8s.sysctl /etc/sysctl.d/k8s.conf
COPY k8s.list /etc/apt/sources.list.d/k8s.list
COPY packages.cloud.google.com.asc obs-crio.asc obs-kubic.asc /etc/apt/trusted.gpg.d/

RUN apt update &&\
    apt install -y kubelet kubeadm kubectl cri-o cri-o-runc &&\
    sh -c '(echo root; echo root) | passwd' &&\
    rm -rf /var/lib/apt/lists/* &&\
    systemctl enable crio &&\
    systemctl enable kubelet &&\
    echo "br-netfilter" >> /etc/modules-load.d/modules.conf




CMD ["/sbin/init"]
