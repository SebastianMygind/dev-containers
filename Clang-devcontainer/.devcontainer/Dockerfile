FROM debian:latest
RUN apt update && apt upgrade -y
RUN apt install sudo -y
RUN useradd -m -s /bin/bash -G sudo dev && echo 'dev ALL=(ALL) NOPASSWD:ALL' >> /etc/sudoers
USER dev
WORKDIR /home/dev

RUN sudo apt install ca-certificates git wget curl bash lsb-release software-properties-common gnupg -y

SHELL ["/bin/bash", "-c"]

RUN wget https://apt.llvm.org/llvm.sh && chmod +x llvm.sh && sudo ./llvm.sh 18

SHELL ["/bin/sh", "-c"]

RUN wget -O - https://apt.llvm.org/llvm-snapshot.gpg.key | sudo apt-key add -
RUN sudo apt install clang-18 lldb-18 lld-18 libwayland-dev wayland-protocols make cmake meson -y



