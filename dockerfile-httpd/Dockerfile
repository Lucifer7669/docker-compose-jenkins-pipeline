FROM centos:8
RUN cd /etc/yum.repos.d/
RUN sed -i 's/mirrorlist/#mirrorlist/g' /etc/yum.repos.d/CentOS-*
RUN sed -i 's|#baseurl=http://mirror.centos.org|baseurl=http://vault.centos.org|g' /etc/yum.repos.d/CentOS-*
RUN  yum update -y && yum install httpd httpd-tools -y 
COPY index.html /var/www/html
COPY ../source-code/index.html /vat/www/html
EXPOSE 80
CMD ["usr/sbin/httpd","-D","FOREGROUND"]

