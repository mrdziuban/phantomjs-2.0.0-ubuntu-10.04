# PhantomJS 2.0.0 for Ubuntu 10.04

This repository contains a pre-compiled version of [PhantomJS 2.0.0](https://github.com/ariya/phantomjs/tree/2.0.0) for Ubuntu 10.04 x686.

To build it yourself, do the following:

    $ sudo apt-get install build-essential g++ flex bison gperf ruby perl \
        libsqlite3-dev libfontconfig1-dev libicu-dev libfreetype6 libssl-dev
        libpng-dev libjpeg-dev python
    $ wget https://bitbucket.org/ariya/phantomjs/downloads/phantomjs-2.0.0-source.zip
    $ unzip phantomjs-2.0.0-source.zip
    $ cd phantomjs-2.0.0
    $ vi src/qt/qtwebkit/Source/ThirdParty/leveldb/Target.pri
        # find the following lines
        #  QMAKE_CXXFLAGS_WARN_ON += -Wno-error=unused-but-set-variable
        #  QMAKE_CXXFLAGS += -Wno-error-unused-but-set-variable
        # and comment them out
        #  # QMAKE_CXXFLAGS_WARN_ON ...
        #  # QMAKE_CXXFLAGS ...
        # save and exit
    $ ./build.sh # this could take an hour or two

This will output the binary to `bin/phantomjs`.
