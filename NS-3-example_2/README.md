NS3 example (2) - second.cc
===================================
  此範例為不同網段下的有線網路，主要針對不同網段下的點對點傳輸，被放在/ns-allinone/ns-3.20/examples/tutorial/底下。


步驟1：複製second.cc到/scratch底下
---------------
    > cp -rf ../ns-allinone/ns-3.20/examples/tutorial/second.cc scratch

步驟2：執行second.cc程式
---------------
    > ./waf --run scratch/second

步驟3：模擬結果
-----------------
    > [http://zhua0404.blogspot.tw/2014/08/ns3-example-2-secondcc.html]
    > [http://zhua0404.blogspot.tw/2014/08/ns3-example-2-secondcc.html]

分析
---------------
> 如果要建置不同網段下的有線網路應該要如何處理，大致上需要注意的部份有：
> > CommandLine的宣告，有助於後續程式執行參數的修改。
> > > ./waf --run "scatch/second -nCsma=50" <br />
> > > ./waf --run "scatch/second -nCsma=100"

> > Container類別：包括有
> > > Node Container -> 分別有兩種節點: p2pNodes and csmaNodes <br />
> > > NetDevice Container -> p2pDevices and csmaDevices <br />
> > > Ipv4Interface Container -> 提供pointToPoint的Interface <br />
> > > Application Container (Server) <br />
> > > Application Container (Client)

> > Helper類別：包括有
> > > PointToPointHelper -> 分別有兩種Helper: pointToPoint and  csma
> > > InternetStackHelper -> 此範例並未給予protocol stack <br />
> > > Ipv4AddressHelper -> 分配有線的IP address <br />
> > > UdpEchoServerHelper <br />
> > > UdpEchoClientHelper

網址：http://zhua0404.blogspot.tw/2014/08/ns3-example-2-secondcc.html
