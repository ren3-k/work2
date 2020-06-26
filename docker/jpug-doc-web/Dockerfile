FROM centos:7 AS jpug-doc-builder
RUN yum update -y && yum install -y \
  docbook-dtds \
  docbook-style-dsssl \
  docbook-style-xsl \
  gcc \
  gettext \
  git \
  jade \
  libxml2-devel \
  libxslt \
  libxslt-devel \
  make \
  readline-devel \
&& yum clean all
COPY ./jpug-doc /jpug-doc
RUN cd /jpug-doc && ./configure --enable-nls --with-libxml --with-libxslt && make html

FROM nginx:latest
COPY --from=jpug-doc-builder /jpug-doc/doc/src/sgml/html /usr/share/nginx/html
COPY ./default.conf /etc/nginx/conf.d
