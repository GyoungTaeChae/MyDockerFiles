FROM --platform=linux/amd64 ubuntu:bionic

ARG DEBIAN_FRONTEND=noninteractive

RUN apt-get update -y && apt-get upgrade -y

RUN apt-get install build-essential -y && \
    apt-get install cmake -y && \
    apt-get install pkg-config -y && \
    apt-get install git -y && \
    apt-get install sudo -y && \
    apt-get install wget -y && \
    apt-get install ninja-build -y && \
    apt-get install software-properties-common -y && \
    apt-get install python3 -y && \
    apt-get install python3-pip -y && \
    apt-get install -y ssh && \
    apt-get install -y gcc && \
    apt-get install -y g++ && \
    apt-get install -y gdb && \
    apt-get install -y rsync && \
    apt-get install -y tar && \
    apt-get install -y x11-utils && \
    apt-get install -y x11-apps && \
    apt-get install -y zip && \
    apt-get clean
    


RUN apt-get install libjpeg-dev libtiff5-dev libpng-dev -y 
RUN apt-get install libavcodec-dev libavformat-dev libswscale-dev -y 
RUN apt-get install libdc1394-22-dev libxvidcore-dev libx264-dev -y 
RUN apt-get install libxine2-dev libv4l-dev v4l-utils -y 
RUN apt-get install libgstreamer1.0-dev libgstreamer-plugins-base1.0-dev -y 
RUN apt-get install libgtk-3-dev -y 
RUN apt-get install libatlas-base-dev libeigen3-dev gfortran -y  
RUN apt-get install python3-dev python3-numpy libtbb2 libtbb-dev -y  
RUN apt-get clean -y 



RUN mkdir opencv &&\
    cd opencv &&\
    wget -O opencv-4.0.0.zip https://github.com/opencv/opencv/archive/4.0.0.zip &&\ 
    wget -O opencv_contrib-4.0.0.zip https://github.com/opencv/opencv_contrib/archive/4.0.0.zip  &&\ 
    unzip opencv-4.0.0.zip &&\ 
    unzip opencv_contrib-4.0.0.zip &&\ 
    rm -rf opencv-4.0.0.zip &&\
    rm -rf opencv_contrib-4.0.0.zip &&\
    mkdir build && cd build &&\
    cmake \
-D CMAKE_BUILD_TYPE=Release \
-D CMAKE_INSTALL_PREFIX=/usr/local \
-D BUILD_WITH_DEBUG_INFO=OFF \
-D BUILD_EXAMPLES=ON \
-D BUILD_opencv_python3=ON \
-D INSTALL_PYTHON_EXAMPLES=ON \
-D OPENCV_ENABLE_NONFREE=ON \
-D OPENCV_EXTRA_MODULES_PATH=../opencv_contrib-4.0.0/modules \
-D OPENCV_GENERATE_PKGCONFIG=ON \
-D WITH_TBB=ON \
../opencv-4.0.0/ &&\
make -j4 &&\
make install 

RUN git clone https://github.com/sunkyoo/opencv4cvml.git
    
     



    







