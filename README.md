build-environment
=================

This sets-up the oe-alliance build environment.



## The buildserver using this branch needs to run on: ##

> Ubuntu 16.04.1 LTS (GNU/Linux 3.14.32-xxxx-grs-ipv6-64 x86_64)


# Building Instructions #

1 - Install packages on your buildserver

    sudo apt-get install -y autoconf automake bison bzip2 chrpath coreutils curl cvs default-jre default-jre-headless diffstat flex g++ gawk gcc gettext git-core gzip help2man htop info java-common libc6-dev libglib2.0-dev libperl4-corelibs-perl libproc-processtable-perl libtool libxml2-utils make ncdu ncurses-bin ncurses-dev patch perl pkg-config po4a python-setuptools quilt sgmltools-lite sshpass subversion swig tar texi2html texinfo wget xsltproc zip zlib1g-dev

----------
2 - Set your shell to /bin/bash

    sudo dpkg-reconfigure dash
    When asked: Install dash as /bin/sh?
    select "NO"

----------
3 - Add user oealliancebuilder

    sudo adduser oealliancebuilder

----------
4 - Switch to user oealliancebuilder

    su oealliancebuilder

----------
5 - Switch to home of oealliancebuilder

    cd ~

----------
6 - Create folder oealliance

    mkdir -p ~/oealliance

----------
7 - Switch to folder oealliance

    cd oealliance

----------
8 - Clone oe-alliance build-environment git

    git clone git://github.com/oe-alliance/build-enviroment.git -b 4.1

----------
9 - Switch to folder build-enviroment

    cd build-enviroment

----------
10 - Update build-enviroment

    make update

----------
11 - Finally you can start building a image

    MACHINE=gbquadplus DISTRO=teamblue make image
