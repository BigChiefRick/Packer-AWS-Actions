FROM ubuntu

# Packer Installation
RUN apt-get -y upgrade
RUN apt-get -y update
RUN apt install -y packer
RUN packer --version
RUN export AWS_SECRET_KEY=$ {{ secrets.AWS_SECRET_KEY }}
RUN export AWS_ACCESS_KEY=$ {{ secrets.AWS_ACCESS_KEY }}
# Packer Build AWS EC2 Instance
ADD example.json /example.json
RUN packer validate /example.json
RUN packer build example.json
