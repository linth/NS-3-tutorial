NS3 tutorial (5) - NetAnim installation (Animation)
=========================
請先稍微看一下有關於Animation的介紹，主要是QT-based的UI圖形介面的模擬軟體，有助於執行程式所產生的行為觀察。

> Animation介紹：
> > Animation is an important tool for network simulation. While ns-3 does not contain a default graphical animation too, we currently have two ways to provide animation, namely using the PyViz method or the NetAnim method. The PyViz method is described in http://www.nsnam.org/wiki/PyViz.

> [NetAnim介紹] (http://www.nsnam.org/docs/models/html/animation.html)：
> > NetAnim is a standalone, Qt4-based software executable that uses a trace file generated during an ns-3 simulation to display the topology and animate the packet flow between nodes.

步驟1：下載NetAnim
---------------
(如果你的版本是NS-3.20，就不需要下載，因為已經在/ns-allinone-3.20/netanim-3.105底下)

    > hg clone http://code.nsnam.org/netanim

步驟2：安裝NetAnim必要套件
---------------
> For Debian/Ubuntu Linux

    > sudo apt-get install mercurial
    > sudo apt-get install qt4-dev-tools

> For Red Hat/Fedora

    > yum install qt4
    > yum install qt4-devel

步驟3：Building步驟
---------------
    > cd netanim-3.105
    > make clean
    > qmake NetAnim.pro (For MAC Users: qmake -spec macx-g++ NetAnim.pro)
    > make
    > 將會產生出NetAnim執行檔...


步驟4：Usage (NetAnim用法，需經過兩個流程)
---------------
> 根據說明NetAnim是two-step流程，先產生出animation XML trace file之後，再將XML trace file利用NetAnim執行 
> > Step 4-1: 
> > > Generate the animation XML trace file during simulation using "ns3::AnimationInterface" in the ns-3 code base.

> > Step 4-2: 
> > > Load the XML trace file generated in Step 1 with the offline Qt4-based animator named NetAnim.

步驟4-1：Generate XML animation trace file
################
強制性要加入的部分：<br />
> 1. 確認porgram的wscript有包含"netanim" module，可參考範例：/src/netanim/examples/wscript <br />
> 2. 在程式內增加include header: [#include "ns3/netanim-module.h"] <br />
> 3. 增加下列程式碼: AnimationInterface anim ("animation.xml"); // where "animation.xml" is any arbitrary filename <br />

非強制性加入的部份：(依照需求增加程式碼，共有八個有用的步驟 & functions) <br />
> 1. anim.SetMobilityPollInterval
> 2. anim.SetConstantPosition (Ptr<Node> n, double x, double y);
> 3. anim.SetStartTime (Seconds(150)); and anim.SetStopTime (Second(150));
> 4. AnimationInterface anim ("animation.xml", 50000);
> 5. anim.EnablePacketMetadata (true);
> 6. anim.UpdateNodeDescription (5, "Access-point");
> 7. anim.UpdateNodeSize (6, 1.5, 1.5);
> 8. anim.UpdateNodeCounter (89, 7, 3.4);

For example : 進入src/netanim/examples

    > ./waf -d debug configure --enable-examples
    > ./waf --run "dumbbell-animation"



步驟4-2：Load the XML in NetAnim
################
把.cc檔執行過後，會產生出.xml檔，最後將.xml檔案載入後直行即可!

    > cd netanim-3.105
    > ./NetAnim
    > When NetAnim is opened, click on the File open button at the top-left corner, select the XML file generated during Step 1.
    > Hit the green play button to begin animation.

網址：http://zhua0404.blogspot.tw/2014/08/ns3-tutorial-5-netanim-installation.html#more
