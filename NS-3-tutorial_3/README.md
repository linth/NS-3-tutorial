NS3 tutorial (3) - Click installation 
=========================
  下面為[Click](http://www.nsnam.org/docs/models/html/click.html)的介紹：

Click is a software architecture for building configurable routers. By using different combinations of packet processing units called elements, a Click router can be made to perform a specific kind of functionality. This flexibility provides a good platform for testing and experimenting with different protocols.

步驟1：下載NS-3 Click必要資料
---------------
    > git clone https://github.com/kohler/click
    > cd click/
    > ./configure --disable-linuxmodule --enable-nsclick --enable-wifi
    > make

步驟2：回到NS-3 directory並在NS-3安裝Click Integration
---------------
    > ./waf configure --enable-examples --enable-tests --with-nsclick=[click的路徑]
For example: ..... --with-nsclick=/home/name/..../ns-allinone-3.17/ns-3.17/click

步驟3：顯示出Click enable結果
---------------
http://zhua0404.blogspot.tw/2014/07/ns3-tutorial-3-click-installation.html#more


步驟4：測試一個例子
---------------
  會出現nsclick-simple-lan-0-0.pcap 和 nsclick-simple-lan-1-0.pcap兩個檔案。<br />

    > ./waf --run nsclick-simple-lan


網址：http://zhua0404.blogspot.tw/2014/07/ns3-tutorial-3-click-installation.html#more
