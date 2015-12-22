# CouchDB RPM package for CentOS 7

Steps to build:

  * Install build tools: yum groupinstall "Development tools" && yum install rpmdevtools
  * git clone https://github.com/idi-ops/couchdb-centos-rpm
  * cd couchdb-centos-rpm
  * Install build dependencies: yum install -y `egrep '^BuildRequires' couchdb.spec | awk '{ printf("%s ", $2); }'`
  * spectool -g -A -R couchdb.spec
  * mkdir -p ~/rpmbuild/SOURCES
  * cp * ~/rpmbuild/SOURCES
  * rpmbuild -bb couchdb.spec
