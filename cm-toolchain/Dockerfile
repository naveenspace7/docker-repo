FROM ubuntu

# install requirements
RUN apt update
RUN apt -y install make wget tar

# download gcc toolchain
RUN mkdir /temp
RUN wget -O /temp/arm-gcc.tar.bz2 "https://developer.arm.com/-/media/Files/downloads/gnu-rm/9-2020q2/gcc-arm-none-eabi-9-2020-q2-update-x86_64-linux.tar.bz2"

# move to the final places
RUN cd /opt && mkdir arm-gcc && tar -xjvf /temp/arm-gcc.tar.bz2 -C arm-gcc --strip-components 1

ENV PATH="/opt/arm-gcc/bin:${PATH}"

WORKDIR /mnt
