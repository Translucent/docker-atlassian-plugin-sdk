FROM java:7-jdk

# Maintainers on this project are the following:
MAINTAINER Martin Aksel Jensen <maj@translucent.dk>

# Install the Atlassian Plugins SDK using the official Aptitude debian
# package repository
RUN echo "deb http://sdkrepo.atlassian.com/debian/ stable contrib" >>/etc/apt/sources.list \
    && apt-key adv --keyserver keyserver.ubuntu.com --recv-keys B07804338C015B73 \
    && apt-get -yqq update \
    && apt-get -yqq install apt-transport-https \
    && apt-get -yqq update \
    && apt-get -yqq install atlassian-plugin-sdk=6.2.2

# Copy Maven preference files to predefine the command line question about
# subscribing to the mailing list to `NO`.
COPY .java /root/.java

# Create directory for sources using the same practice as the ruby images
RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

# Set the default running command of the AMPS image to be running the
# application in debug mode.
CMD ["atlas-version"]
