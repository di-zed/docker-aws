FROM amazonlinux:latest
RUN yum update && yum install -y npm unzip groff mandoc pip git
RUN npm install aws-cdk -g
# Install AWS CLI:
RUN yum remove awscli
RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-aarch64.zip" -o "awscliv2.zip"  \
    && unzip awscliv2.zip  \
    && ./aws/install
RUN rm -rf ./aws && rm awscliv2.zip
# Install SAM CLI:
RUN pip install --upgrade aws-sam-cli
# Add colors to the terminal:
RUN echo "PS1='${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]\$ '" >> /root/.bashrc