NS3 tutorial (1) - NS3 installation in Ubuntu 12.04 
=========================

步驟1：安裝必要Ubuntu套件
---------------
    > sudo apt-get install gcc g++ python
    > sudo apt-get install gcc g++ python python-dev
    > sudo apt-get install mercurial
    > sudo apt-get install bzr
    > sudo apt-get install gdb valgrind
    > sudo apt-get install gsl-bin libgsl0-dev libgsl0ldbl
    > sudo apt-get install flex bison libfl-dev
    > sudo apt-get install g++-3.4 gcc-3.4
    > sudo apt-get install tcpdump
    > sudo apt-get install sqlite sqlite3 libsqlite3-dev
    > sudo apt-get install libxml2 libxml2-dev
    > sudo apt-get install libgtk2.0-0 libgtk2.0-dev
    > sudo apt-get install vtun lxc
    > sudo apt-get install uncrustify
    > sudo apt-get install doxygen graphviz imagemagick
    > sudo apt-get install texlive texlive-extra-utils texlive-latex-extra
    > sudo apt-get install python-sphinx dia
    > sudo apt-get install python-pygraphviz python-kiwi python-pygoocanvas libgoocanvas-dev
    > sudo apt-get install libboost-signals-dev liboost-filesystem-dev
    > sudo apt-get install openmpi*

步驟2：Downloading NS-3 using a tarball
---------------
    > cd
    > mkdir tarballs
    > cd tarballs
    > wget https://www.nsnam.org/release/ns-allinone-3.20.tar.bz2
    > tar -zxvf ns-allinone-3.20.tar.bz2

步驟3：Build NS-3
---------------
    > ./build.py

步驟4：安裝waf
---------------
    > ./waf distclean
    > ./waf configure (OR ./waf configure -enable-examples-enable-tests)
    >./waf build

步驟5：測試安裝
---------------
    > ./test.py (OR use this, if you want to test core modules only. > ./test.py -c core)

步驟6：執行sample
---------------
    > cp -rf ../ns-3.17/examples/tutorial/first.py scrcatch/first.py
    > ./waf --pyrun scrcatch/first.py

步驟7：執行結果
---------------
    At time 2s client sent 1024 bytes to 10.1.1.2 port 9
    At time 2.00369s server received 1024 bytes from 10.1.1.1 port 49153
    At time 2.00369s server sent 1024 bytes to 10.1.1.1 port 49153
    At time 2.00737s client received 1024 bytes from 10.1.1.2 port 9



