FROM centos:6.6

RUN rpm --rebuilddb \
	&& yum --setopt=tsflags=nodocs -y install \
		httpd-2.2.15-59.el6.centos \
		mod_ssl-2.2.15-59.el6.centos \
		php-5.3.3 \
		epel-release-6-8.noarch \
		wget \
		nfs-utils
		
RUN yum --setopt=tsflags=nodocs -y install \
		php-pecl-xdebug.x86_64\
		php-pecl-memcached \
		php-pecl-memcache \
		php-pecl-amqp\
		php-pdo \
		php-mssql \
		php-mbstring \
		php-xml \
		php-mysql \
		php-bcmath \
		php-mcrypt \
		php-soap
	    && rm -rf /var/cache/yum/* \
        && yum clean all
        
EXPOSE 80
CMD ["/usr/sbin/apachectl","-D","FOREGROUND"]
