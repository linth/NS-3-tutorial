NS3 tutorial (4) - install OpenFlow 
=========================
假設使用者已經將NS-3正確安裝完畢。

步驟1：進入"/ns-allinone-2.30/ns-3.20/"目錄下安裝OpenFlow
---------------
    > hg clone http://code.nsnam.org/openflow
    > cd openflow

步驟2：在OpenFlow目錄下 Configure & Building
---------------
./waf build 出現滿多錯誤的，可以google解決。

    > ./waf configure
    > ./waf build  


步驟3：退回"/ns-allinone-2.30/ns-3.20/"目錄下，並enable起來。
---------------
For example: --with-openflow=/home/user_name/.../ns-allinone-2.30/ns-3.20/openflow

    > cd ..
    > ./waf configure --enable-examples --enable-tests --with-openflow=[openflow路徑]

步驟4：Build NS-3和激活OpenFlowSwitch模組
---------------
    > ./waf build

網址：http://zhua0404.blogspot.tw/2014/07/ns3-tutorial-4-install-openflow.html#more
