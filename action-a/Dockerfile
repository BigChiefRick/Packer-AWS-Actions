FROM ubuntu

# Packer Installation
RUN apt-get -y upgrade
RUN apt-get -y update
RUN apt install -y packer
RUN packer --version
RUN declare -x AWS_SECRET_KEY= "$AWS_SECRET_KEY"
RUN declare -x AWS_ACCESS_KEY= "$AWS_ACCESS_KEY"

# Packer Build AWS EC2 Instance
ADD example.json /example.json
RUN packer validate /example.json
RUN packer build example.json
