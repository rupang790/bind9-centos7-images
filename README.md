# bind9-centos7-images
This is the bind9 based on centos7:latest image for bind9-centos7 helm chart.

## Description
This image was considered mounting all `named` config files through the kubernetes configmap, in order to use a flexible config file for various domains. Dockerfile and entrypoint file were referenced by https://github.com/CentOS/CentOS-Dockerfiles.
+ All configuration file for `named` daemon such as `named.conf` and `named.rfc1912.zones` should be mounted at `/tmp/etc` on container.
+ All Zone files should be mounted at `/tmp/var` on container.
+ By `entrypoint` file, under `/tmp/*` directory files will be copied to `/named/*` directory.
+ `named` will be started with config file path as `/named/etc/named.conf`.

