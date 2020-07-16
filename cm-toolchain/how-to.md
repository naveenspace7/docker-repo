# How to use the docker image

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
