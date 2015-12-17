FROM translucent/atlassian-plugin-sdk:latest

# Maintainers on this project are the following:
MAINTAINER Martin Aksel Jensen <maj@translucent.dk>

# Create directory for sources using the same practice as the ruby images
RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

# Once upon a time in the west this was thought to be a good idea, however in
# the dawn of the new ages it was discovered to be better to possible have
# a Maven repository volume mounted instead for speeding up running the AMPS
# utilities.
# ONBUILD COPY pom.xml /usr/src/app/
# ONBUILD RUN atlas-mvn dependency:copy-dependencies

# Copy the source to the build image and don't do anything else. We could
# choose to pre-download the source dependencies, build, and install the
# application, but it is not feasable. A lot of extra dependencies will be
# downloaded after a prefetch, eg. when running and testing and this image
# should not be used to release add-on's anyway.
ONBUILD COPY . /usr/src/app

# Set the default running command of the AMPS image to be running the
# application in debug mode.
CMD atlas-debug
