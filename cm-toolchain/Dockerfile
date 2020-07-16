FROM ubuntu

# install requirements
RUN apt update
RUN apt -y install make wget tar unzip build-essential libusb-1.0-0 libusb-1.0-0-dev
RUN DEBIAN_FRONTEND=noninteractive apt-get -yq install cmake

# download gcc toolchain
RUN mkdir /temp
RUN wget -O /temp/arm-gcc.tar.bz2 "https://developer.arm.com/-/media/Files/downloads/gnu-rm/9-2020q2/gcc-arm-none-eabi-9-2020-q2-update-x86_64-linux.tar.bz2"

# move to the final places
RUN cd /opt && mkdir arm-gcc && tar -xjvf /temp/arm-gcc.tar.bz2 -C arm-gcc --strip-components 1

# add cross-compiler path
ENV PATH="/opt/arm-gcc/bin:${PATH}"

# download stlink util and install it
RUN cd /temp && wget https://github.com/stlink-org/stlink/archive/master.zip
RUN cd /temp && unzip master.zip && cd stlink-master && make release
RUN mkdir /opt/stlink && mkdir /opt/stlink/bin
RUN cp /temp/stlink-master/build/Release/bin/st-* /opt/stlink/bin -r

# add stlink path
ENV PATH="/opt/stlink/bin:${PATH}"

WORKDIR /mnt
