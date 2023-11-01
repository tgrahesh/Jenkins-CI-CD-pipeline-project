FROM amazonlinux:latest

# Install dependencies
RUN yum update -y && \
    yum install -y httpd && \
    yum search wget && \
    yum install wget -y && \
    yum install unzip -y

# change directory
RUN cd /var/www/html

# download webfiles
ADD https://github.com/tgrahesh/Jenkins-CI-CD-pipeline-project/blob/main/2136_kool_form_pack.zip /var/www/html/

# unzip folder
RUN unzip 2136_kool_form_pack.zip

# copy files into html directory
RUN cp -r onlineform/* /var/www/html/

# remove unwanted folder
RUN rm -rf onlineform 2136_kool_form_pack.zip

# exposes port 80 on the container
EXPOSE 80

# set the default application that will start when the container start
ENTRYPOINT ["/usr/sbin/httpd", "-D", "FOREGROUND"]