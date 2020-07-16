# How to use the docker image

Current status: cross-compiler works, stlink utility works, segger - pending, install nrf sdk - pending

Use the following structure for the source:

```
+ /files/ <- run the above command here
    - Makefile
    +src
        + files_1
        + files_2
    + inc
```

Run the following command:
`$ sudo docker run -v $(pwd):/mnt arm-build make`

`$ sudo docker run --device=/dev/bus/usb/002/006 naveenspace7/arm-cm-toolchain:v2 st-info --probe
`
