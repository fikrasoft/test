FROM centos:6.6

RUN rpm --rebuilddb \
	&& yum --setopt=tsflags=nodocs -y install \
		httpd-2.2.15-54.el6.centos \
		mod_ssl-2.2.15-54.el6.centos \
		php-5.3.3-48.el6_8 \
		wget \
		nfs-utils

RUN  wget http://download.fedoraproject.org/pub/epel/6/x86_64/epel-release-6-8.noarch.rpm \
		 && rpm -ivh epel-release-6-8.noarch.rpm

RUN yum --setopt=tsflags=nodocs -y install \
		php-pecl-xdebug \
		php-pecl-memcached \
		php-pecl-memcache \
		php-pdo \
		php-mssql \
		php-mbstring \
		php-xml \
		php-mysql \
		php-bcmath \
		memcached \
		&& rm -rf /var/cache/yum/* \
		&& yum clean all

		
		
EXPOSE 80
CMD ["/usr/sbin/apachectl","-D","FOREGROUND"]
		