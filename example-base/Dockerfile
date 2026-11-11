FROM ros:jazzy-ros-base-noble

RUN rosdep update

# Example core dependencies
ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update \
    && apt-get install -yq --no-install-recommends \
        cmake \
        build-essential \
        git \
        curl \
        openssh-client \
        tmux \
        nano \
        python3-vcstool \
    && rm -rf /var/lib/apt/lists/*

# Example ROS dependencies
RUN apt-get update && apt-get install -y \
        ros-${ROS_DISTRO}-rviz2 \
        ros-${ROS_DISTRO}-rviz-common\
        ros-${ROS_DISTRO}-rviz-default-plugins \
    && rm -rf /var/lib/apt/lists/*

# Add user extras script to the image.
COPY install-user-extras.sh /install-user-extras.sh
