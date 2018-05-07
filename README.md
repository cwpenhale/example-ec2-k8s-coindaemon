# example-ec2-k8s-coindaemon

## Notes:
1. built on cent7
2. won't build on a tiny amazon free instance. Rustc dies compiling deps. Built on a 4cpu/4GB host
3. parity's centos dockerfile is busted, needs libudev-devel as part of the yum install. will PR eventually.

