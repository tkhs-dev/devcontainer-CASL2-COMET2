# [Choice] Debian / Ubuntu version (use Debian 11/9, Ubuntu 18.04/21.04 on local arm64/Apple Silicon): debian-11, debian-10, debian-9, ubuntu-21.04, ubuntu-20.04, ubuntu-18.04
ARG VARIANT=debian-11
FROM mcr.microsoft.com/devcontainers/base:${VARIANT}
WORKDIR /src
RUN apt-get update
RUN apt-get install perl
RUN wget https://naokikitamura.github.io/FCO/files/casl2-2017-11-16.zip
RUN unzip casl2-2017-11-16.zip
RUN rm casl2-2017-11-16.zip
RUN mv `ls` casl2
WORKDIR casl2
RUN perl Makefile.PL
RUN make
RUN make install
ENV PATH $PATH:/src/casl2

# [Optional] Uncomment this section to install additional OS packages you may want.
#
# RUN apk add --no-cache <your-package-list-here>
