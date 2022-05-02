# Gemini V2（CAN）的配置流程
**全程参考官网：** [mellow.klipper.cn](https://mellow.klipper.cn/)

本文提供了<font style="background:yellow">软件</font>，<font style="background:yellow">镜像</font>，以及编译好的<font style="background:yellow">klipper固件</font>,方便一次性下载。

Google Drive：[package from drive.google](https://drive.google.com/drive/folders/1GtRI1C0IcE3mND4UErnZyka3ZrgK1Vmm)

*方便国内用户*：

百度网盘：[package from pan.baidu](https://pan.baidu.com/s/1SHc_n0J157p1p5Y2r8Q-0w?pwd=fly8 ) 提取码：fly8 

阿里云网盘：[package from aliyundrive](https://www.aliyundrive.com/s/FY1KDXQxaiS) 提取码: 8y0b 

## 1.物品准备
* ### 1.1 硬件类：
  **Gemini_v2**

  **UTOC-1**
  
  **SHT42**
* ### 1.2 线材类：

  18awg x 5m 黑色

  18awg x 5m 红色
  
  （长度可按需求，一般这些就够了）

  叉型冷压端子若干(如图)
  <div align=center>
  <img src="https://img-blog.csdnimg.cn/ebb9ffc8ecf444f6ad7d30e54cd685c2.png"/>
  </div>


  线材主要用于：

    a.**UTOC**的供电<font color=red>2根线</font>（<font color=red>24V</font>/<font color=black>GND</font>）
  
    b.**SHT42**与 **UTOC**进行CAN通讯的<font color=red>4根线</font>（CAN L / <font color=red>CAN H</font> / <font color=red>24V</font>/ GND）

* ### 1.3 工具类：
  4.2mm 5557 端子 压线钳
  
  ot 冷压端子 压线钳
 
## 2.电气接线部分
接线方式有很多种，这里仅仅展示一种情况，其他都可以根据CAN的功能进行类比。
* ### 2.1 制作can的4线通讯线（以UTOC和SHT42 为例）
   2x2p的 5557 端子，在购买的SHT42板的包裹中已经附带了
   
   如图：
   <div align=center>
  <img src="https://img-blog.csdnimg.cn/a66fa3ec5fce4d69999eb269092e1438.png"/>
  </div>

  <center><font style="background:yellow" color=red>5557 端子 一定要压好，不要让vcc虚连 </font></center>
  VCC 和 GND，CAN H 和 CAN L 分别对应好位置

  <div align=center>
  <img src="https://img-blog.csdnimg.cn/bf80bb107d0b474fa8b4a3551e780657.png"/>
  </div>

  <div align=center>
  <img src="https://img-blog.csdnimg.cn/0c67a35dc9fd4e12ad931c6529dc3af9.png"/>
  </div>

  接线端子的实际效果：
  <div align=center>
  <img src="https://img-blog.csdnimg.cn/be73b5077bc7407ca321c97d2b4e232e.png"/>
  </div>
  
  连线的实际效果：
  <div align=center>
  <img src="https://img-blog.csdnimg.cn/50b823c23c1c43c0adab91c9f07b6ed5.png"/>
  </div>

  <center><font style="background:yellow" color=red>线序一定不要接错</font></center>
* ### 2.2 CAN的VCC取电
  连接CAN工具头需要有VCC接入，这里以**UTOC** 取电为例
  <div align=center>
  <img src="https://img-blog.csdnimg.cn/e29a075d786c424fac87265cb4b636dc.png"/>
  </div>
  <div align=center>
  <img src="https://img-blog.csdnimg.cn/4bb932fc0b6e44d58909c5ca7343d4ad.png"/>
  </div>
*   ### 2.3 **UTOC** 与Gemini 连接
  <div align=center>
  <img src="https://img-blog.csdnimg.cn/bacee07b5ca44e1b9b7c041ef4647ff7.png"/>
  </div>
<center><u>接线部分至此完成</u></center>

## 3.固件刷写
 <center><font style="background:LightSteelBlue" color=red size=5>对于购买SD卡套餐的朋友，请直接看3.2</font></center>

*  ### 3.1 linux镜像的刷入
   一定要根据官网提供的<font style="background:yellow" color=red>最新</font>固件:
   
   下载链接：v2.9 [2022-04-12](https://upyun.pan.zxkxz.cn/IMG/Build/FLY-v2.9_Flygemini_bullseye_current_5.10.85.img.xz)
   
   <div align=center>
   <img src="https://img-blog.csdnimg.cn/f19fe836a4dc413196991c6aec5cb9f4.png"/>
   </div>
   下载后的镜像文件：
   <div align=center>
   <img src="https://img-blog.csdnimg.cn/fc1a53c255a0468d8a3712f92852959d.png"/>
   </div>
   通过工具balenaEtcher给sd卡刷入镜像：
   
   下载链接：[balenaEtcher - Flash OS images to SD cards & USB drives](https://www.balena.io/etcher/)
   <div align=center>
   <img src="https://img-blog.csdnimg.cn/29f64ff3bf3c4fe6a959eb13ffccb22b.png"/>
   </div>

   <div align=center>
   <img src="https://img-blog.csdnimg.cn/84cc3570434540119f5825d1749de59c.png"/>
   </div>

   <div align=center>
   <img src="https://img-blog.csdnimg.cn/842e611b14934f18b5baeac5e1d76c28.png"/>
   </div>

    等待5分钟后刷好后拔下，并直接插入图中所示的linux的SD卡接口。
   <div align=center>
   <img src="https://img-blog.csdnimg.cn/1e34e0ec0c87485699b10f373c1c7530.png"/>
   </div>

   Windows 提示的格式化不要管，直接拔出就行。
   **<center><u><font size=4>至此linux上位机端带有klipper 的系统镜像已经搞定</font></u></center>**
*  ### 3.2 通电测试
   图中位置插入SD卡
   <div align=center>
   <img src="https://img-blog.csdnimg.cn/1e34e0ec0c87485699b10f373c1c7530.png"/>
   </div>
   上电测试：注意这里采用的是USB（ CH340 ）连接的方式。
   
   因为刚烧录好的系统，没有配置WiFi

   <font color=red>如果使用12~24V 的VCC取电方式，USB连接一定要断开。</font >

   有些朋友不从事嵌入式开发，<font color=red>可能需要</font >：Windows下的CH340驱动，要单独下载，在<font color=red>文章开头</font >的软件包中提供。

   **终端连接gemini：**

   下载MobaXterm:[MobaXterm Xserver with SSH, telnet, RDP, VNC and X11 - Download](https://mobaxterm.mobatek.net/download.html)

   通过MobaXterm 的session里面的serial连接，<font color=red>首先确保没有接入vcc</font >

   具体步骤：

   Windows 设备管理器：记住COM号 如图：COM3
   <div align=center>
   <img src="https://img-blog.csdnimg.cn/6a8190f5dbfc48149868bfcfafc0e5fa.png"/>
   </div>
   
   打开MobaXterm 添加新的session，选择serial
   <div align=center>
   <img src="https://img-blog.csdnimg.cn/6daed671aa524b08ab165177c84292cd.png"/>
   </div>

    配置波特率<font color=red>115200</font >，连接端口号为刚在<font color=red>设备管理器</font >记住的端口
   <div align=center>
   <img src="https://img-blog.csdnimg.cn/28a099b97bf443d5935e07cba2719633.png"/>
   </div>

   <div align=center>
   <img src="https://img-blog.csdnimg.cn/4181764455af4d51b5f44e4ea765318b.png"/>
   </div>

    这个效果就ok了。

    配置WiFi
    在MobaXterm终端输入
 
    ```C
    nmtui
    ```
   



​







   



   
   
   

 

  


  

  

