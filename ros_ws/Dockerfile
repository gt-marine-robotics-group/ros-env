FROM osrf/ros:humble-desktop
ARG USERNAME=vs
ARG USER_UID=1000
ARG USER_GID=$USER_UID

RUN groupadd --gid $USER_GID $USERNAME \
    && useradd --uid $USER_UID --gid $USER_GID -m $USERNAME -s /bin/bash \
    #
    # [Optional] Add sudo support. Omit if you don't need to install software after connecting.
    && apt-get update \
    && apt-get install -y sudo \
    && echo $USERNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$USERNAME \
    && chmod 0440 /etc/sudoers.d/$USERNAME

# Add rosdep update

# https://github.com/ros2/rviz/issues/834
# Fix broken Ubuntu 22.04 Mesa for WSL2 Docker https://bugs.launchpad.net/ubuntu/+source/mesa/+bug/2004649
RUN apt-get update
RUN apt -y install software-properties-common
RUN add-apt-repository -y ppa:kisak/kisak-mesa
RUN apt-get update
RUN apt-get -y upgrade

RUN echo 'source /opt/ros/humble/setup.bash' >> /home/$USERNAME/.bashrc
RUN echo 'PROMPT_DIRTRIM=2' >> /home/$USERNAME/.bashrc

USER $USERNAME