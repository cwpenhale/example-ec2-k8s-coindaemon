# example-ec2-k8s-coindaemon

## Prerequisites
1. AWS credentials exposed on the bastion host running the playbook (export AWS_etc)
2. ansible 2.5 is installed on centos 7 on a machine with enough memory and cpu to do a rust compile in docker, see notes
3. Amazon ECR for docker repository is set up. Mine's hard-coded in, you can edit yours in @FIXME

## Run Instructions:
1. Run the playbook in this repository (ansible-playbook -i ./hosts site.yml)
2. Run the Kubespray playbook to set up the staged atomic kubernetes deployment (outside the scope of this document)
3. Deploy the parity coindaemon docker image you built in step one and deployed in ECR with the other playbook (in development)

## Notes:
1. built on cent7
2. won't build on a tiny amazon free instance. Rustc dies compiling deps. Built on a 4cpu/4GB host
3. parity's centos dockerfile is busted, needs libudev-devel as part of the yum install. will PR eventually.

