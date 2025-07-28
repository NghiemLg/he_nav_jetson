FROM dustynv/ros:melodic-ros-base-l4t-r32.7.1

ENV NVIDIA_VISIBLE_DEVICES ${NVIDIA_VISIBLE_DEVICES:-all}
ENV NVIDIA_DRIVER_CAPABILITIES ${NVIDIA_DRIVER_CAPABILITIES:+$NVIDIA_DRIVER_CAPABILITIES,}graphics
ENV DEBIAN_FRONTEND noninteractive

# Cài đặt công cụ cơ bản
RUN apt-get update && apt-get install -y --no-install-recommends \
    sudo less emacs tmux bash-completion command-not-found software-properties-common \
    xsel curl xdg-user-dirs python-pip python-protobuf python-apt python-pexpect \
    pcl-tools libomp5 vulkan-utils

# Cài đặt Python 3 và PyTorch
RUN apt-get install -y python3-pip
RUN pip3 install --upgrade pip
RUN pip3 install torch==1.10.0+cu102 torchvision==0.11.0+cu102 torchaudio==0.10.0 -f https://download.pytorch.org/whl/cu102/torch_stable.html

# Cài đặt công cụ phát triển
RUN apt-get install -y tmux vim git libsdl-image1.2-dev libsdl-dev

# Dọn dẹp
RUN apt-get clean && rm -rf /var/lib/apt/lists/*

CMD ["bash"]