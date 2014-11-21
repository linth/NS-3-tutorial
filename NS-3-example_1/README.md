NS3 example (1) - Wire network (first.cc or first.py)
====================================
此範例為Sample Wire network (Point-to-Point)，主要是針對點對點的範例檔。被放在/ns-allinone/ns-3.20/examples/tutorial/底下，有兩個檔案，分別為first.cc和first.py。

步驟1：如果要執行first.cc，需要先copy檔案到/scratch底下
------------
    > cp -rf ../ns-allinone/ns-3.20/examples/tutorial/first.cc scratch
    > ./waf --run scratch/first

如果要執行first.py，需要先copy檔案到/scratch底下

    > cp -rf ../ns-allinone/ns-3.20/examples/tutorial/first.cc scratch
    > ./waf --pyrun scratch/first.py

步驟2：檢視模擬結果
------------
http://zhua0404.blogspot.tw/2014/08/ns3-example-1-wire-network-firstcc-or.html

分析：
-------------
> 程式碼大致上分類2個項目：
> > Container類別：包括有
> > > 1. Node Container
> > > 2. NetDevice Container
> > > 3. Ipv4Interface Container
> > > 4. Application Container (Server)
> > > 5. Application Container (Client)

> > Helper類別：包括有
> > > 1. PointToPointHelper
> > > 2. InternetStackHelper
> > > 3. Ipv4AddressHelper
> > > 4. UdpEchoServerHelper
> > > 5. UdpEchoClientHelper

有線部分之Point-to-Point需要撰寫上述兩個類別，需要按造順序進行script程式的撰寫，否則會出錯。 <br />
其中，推薦這份[IWING文件](http://iwing.cpe.ku.ac.th/sites/default/files/file4download/ns3-Part3-Wireline.pdf)寫得很好，滿容易上手的。 <br />
