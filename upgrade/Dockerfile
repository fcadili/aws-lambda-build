# Create amzn-ami-hvm-2016.03.3.x86_64-gp2 container suitable for building Lambda binaries
FROM stechstudio/aws-lambda-build:1.2.2
LABEL authors="Bubba Hines <bubba@stechstudio.com>"

# Update dependencies
RUN yum makecache fast
RUN rpm --rebuilddb && yum update -y
RUN rpm --rebuilddb && yum install -y glib2-devel
RUN rpm --rebuilddb && yum install -y gperf
RUN curl https://sh.rustup.rs -sSf | sh -s -- -y
RUN curl -L https://ftp.gnu.org/pub/gnu/gettext/gettext-0.20.1.tar.gz | tar xzC .
RUN cd gettext-0.20.1 && ./configure && make install
RUN rm -rf gettext-0.20.1*
RUN rpm --rebuilddb && yum install -y gobject-introspection-devel
RUN curl -sL https://rpm.nodesource.com/setup_10.x | bash -
RUN rpm --rebuilddb && yum install -y nodejs
RUN rpm --rebuilddb && yum install -y libtool-ltdl-devel
