NS3 tutorial (2) - NS3 visualization
=========================
關於NS-3 visualization的介紹，可以先看NS-3官網介紹，使用[PyViz](http://www.nsnam.org/wiki/PyViz)來實現。

NS-3 PyViz is a live simulation visualizer, meaning that it uses no trace files. It can be most useful for debugging purposes, i.e. to figure out if mobility models are what you expect, where packets are being dropped, etc. There's also a builtin interactive python console that can be used to debug the state of the running objects. Although it is mostly written in Python, it works both with Python and pure C++ simulations.


步驟1：安裝Ubuntu PyViz必要套件
---------------
    > sudo apt-get install python-dev 
    > sudo apt-get install python-pygraphviz 
    > sudo apt-get install python-kiwi 
    > sudo apt-get install python-pyhoocanvas
    > sudo apt-get install python-gnome2 
    > sudo apt-get install python-gnomedesktop 
    > sudo apt-get install python-rsvg

步驟2：安裝Python interactive (可選擇不安裝)
---------------
    > sudo apt-get install ipython

步驟3：執行NS-3 visualization指令
---------------
    > ./waf --pyrun scr/flow-monitor/examples/wifi-olsr-flowmon.py --visualize

網址：http://zhua0404.blogspot.tw/2014/07/ns3-tutorial-2-ns3-visualization.html
