jetty9-rpm
===========

A spec file (and support files) to build a Jetty 9.x (http://www.eclipse.org/jetty/) RPM package.

To Build:

`sudo yum -y install rpmdevtools && rpmdev-setuptree`

`wget https://github.com/jjonez/jetty9-rpm/blob/master/jetty9.spec -O ~/rpmbuild/SPECS/jetty9.spec`

`wget https://github.com/jjonez/jetty9-rpm/blob/master/jetty9.sysconfig -O ~/rpmbuild/SOURCES/jetty9.sysconfig`

`wget https://github.com/jjonez/jetty9-rpm/blob/master/jetty9.logrotate -O ~/rpmbuild/SOURCES/jetty9.logrotate`

`wget "http://eclipse.org/downloads/download.php?file=/jetty/9.1.3.v20140225/dist/jetty-distribution-9.1.3.v20140225.tar.gz&r=1" -O ~/rpmbuild/SOURCES/jetty-distribution-9.1.3.v20140225.tar.gz`


`wget "http://central.maven.org/maven2/org/eclipse/jetty/jetty-distribution/9.4.6.v20170531/jetty-distribution-9.4.6.v20170531.tar.gz" -O ~/rpmbuild/SOURCES/jetty-distribution-9.4.6.v20170531.tar.gz`

`rpmbuild -bb ~/rpmbuild/SPECS/jetty9.spec`


Note, after installation you will need to change owner of /var/run/jetty

`mkdir /var/run/jetty`
`chown jetty:jetty /var/run/jetty`
