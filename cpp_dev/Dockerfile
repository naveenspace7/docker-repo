FROM ubuntu

RUN apt update

RUN apt -y install build-essential tar wget make unzip
RUN DEBIAN_FRONTEND=noninteractive apt-get -yq install cmake

RUN mkdir /temp && cd temp && wget https://github.com/google/googletest/archive/master.zip
RUN cd /temp && unzip master.zip

RUN cd /temp/googletest-master && mkdir build

RUN cd /temp/googletest-master/build && cmake .. -DBUILD_SHARED_LIBS=ON -DINSTALL_GTEST=ON -DCMAKE_INSTALL_PREFIX:PATH=/usr && make && make install && ldconfig

WORKDIR /mnt 
