DA30L-R8000 电子分析器 
========================

=====================  ================================================================
参数                   说明
=====================  ================================================================
Camera                 Basler scA 1400-17gm (ICX285AL sensor, 12bit 1392x1040), 17fps
Working distance       34 mm
Mean radius            200 mm
Configuration          Low pass mode*
=====================  ================================================================

一共有三个工作模式，High pass mode(UPS)，Low pass mode(Laser)和SubmeV。目前我们光源为Kr灯和激光，一般工作在Laser模式下。UPS和Laser切换需要在机柜后面更改以下接口的连接方式：AV-， AV+， LV1，LV2，LV3，LV4，LBAIS，SPhi。Laser切换到SubmeV时，还需要更换junction box的连线。

聚焦
-----------------
聚焦是ARPES实验中非常重要的一步，为使分析仪达到最佳性能，样品的受照部分必须在三个方向上都处于分析仪的焦点位置：平行于入射狭缝的方向（X），垂直于入射狭缝的方向（Y）、以及朝向/远离分析仪的方向（Z）.

聚焦的第一步是光源的调节
---------------------------
对于工作距离的确定，我们会在利用定位托来确定。确定工作距离后，平整的样品表面就会放置在工作距离，在光源调节中固定不变。

灯的方向
-----------------
我们有两种光源，分别是激光和紫外气体灯，它们的几何位置如下图。当样品台R1=0°时，样品台运动轴和上述分析器焦点的三个方向重合。但定义不一样，样品台的运动轴如下图括号中的定义。

.. image:: /_static/ARPES_light_geometry.png
   :alt: ARPES_light_geometry
   :width: 500px
   :align: center

**激光光源align：**

激光光斑为几十微米，transmission模式下，看到的都是激光本身光斑大小，可使用大样品来调节光源。

工作距离的确定已经由定位托给定，需要微调的话可以改变L1或L2的电压，在camera显示上观察transmission线的变化。以此来判断工作距离的好坏。理想状态时在不需要改变L1和L2的电压的情况下，transmission线能够最聚焦。

平行于狭缝的方向：这个调整是将transmission线放到Image的中间位置，Y轴刻度为零处。需要通过调节聚焦镜的俯仰和上下来实现。

垂直于狭缝的方向：这个调整是将transmission的强度跳到最大。可以通过UP/Down来判断，UP/Down是DA模式下将电子沿着垂直于狭缝的方向进行偏转。逐渐通过调节聚焦镜的偏摆和左右，将UP/Down增加的值降低到零。

垂直于狭缝方向和工作距离耦合再一起，需要两者重复交替进行优化达来到达最佳状态。平行于狭缝方向也需兼顾下。

.. image:: /_static/ARPES_focus_lens.png
   :alt: ARPES_laser_focuslens
   :width: 600px
   :align: center

**激光光斑大小的调节：**

该聚焦镜由NTT Advanced Technology制造，在190-210nm激光下，焦距为250-210mm。聚集镜入光口为1.7mm，numeric aperture (NA)在入射光直径为1.0mm时 ~0.04，理论上能够聚焦到~3um。cited from xxx。

该聚焦支架设计存在不足，焦距的调节没法精确进行，需通过螺杆的移动和聚焦镜的夹持改动进行，非常粗糙。一开始优化光斑大小确定焦距需要花费大量时间。上方聚焦旋钮改变伽利略扩束镜的扩束倍数，可以动态调节光斑大小。目前激光光斑大小为xxum

**紫外光源align：**

紫外气体光源光斑大小~1.6mm，比狭缝宽度宽，通常使用和光源尺度差不多的Post样品进行优化。

工作距离还是由定位托确定后，将Post样品表面放置到工作距离。

由于紫外灯的方向不是一个常规的方向，而且能调节的PA方向也不是独立的，所以调节起来相对费劲。但原理和激光调节一致，首先也是通过调节灯头和样品位置，将transmission线移动到中间。其次调节灯的左右和样品的左右，让强度达到最大。接下来反复调节使得最后trasmission达到最优。是否为最优也可通过改变L1/L2，以及Up/Down，看是否能够继续优化来判断。

**样品align:**

在光源优化之后，放入样品后，只需将样品优化到最佳聚焦位置。同样的，也可通过改变L1/L2，以及Up/Down，看是否能够继续优化。但此时只能动样品位置来进一步优化。


狭缝几何
-------------
==============  ================  ================  ================
Encoder index	  Slit width        Slit Length       Aperture
==============	================  ================  ================
100             0.05 mm            30 mm            No
200             0.1 mm             30 mm            No
300             0.2 mm             30 mm            No
400             0.3 mm             30 mm            No
500             0.2 mm             30 mm            Yes
600             0.3 mm             30 mm            Yes
700             0.5 mm             30 mm            Yes
800             0.8 mm             30 mm            Yes
900             1.5 mm             30 mm            Yes
==============	================  ================  ================

通常情况下，选取带Aperture的Slit。如果样品聚焦没有做好的话，使用带Aperture的slit时，样品DA mapping会有缺失等情况，这也可以进一步验证聚集的好坏。


MCP的调节
----------------------  
MCP需要工作在线性区，不然的话就无法测量一些小信号。不能因为激光强度强就降低MCP，需要降低的是激光强度，放置衰减片。

**如何得到MCP的线性曲线**

- 打开global detector,将ADC改成Plused 模式，在Plused模式下，会记录每一个相机事件的信号来得到强度，类似于我之前做过的RIXS的单光子计数。前提需要每个事件之间不存在overlap，这可以通过降低光强，降低Pass Energy以及改到DA14模式得到。

- 可以点击live camera pause检查下事件是否有重叠

- 然后点击MCP optimize, 设置扫描范围和步长。 得到曲线，选取在平台区间的最低点




- 首先要确定样品台，腔体没有场的影响，不会对出射电子产生影响

- 坐标系定义： X along the slit, Y perpendicular to the slit, Z along the optical axis of the analyzer.

对于小光斑，建议用一个大的样品来优化聚焦，因为trans线本身就很细了。
- UP/Down 垂直于狭缝，如果没有trans线消失了，通常是由于在这个方向上没有聚焦好
- L1和L2对工作距离敏感，可以调节看下工作距离的问题

对于大光斑，需要用小样品来调节 





当光斑远小于slit宽度时后，如果对准变得非常困难

- 调光的目的是为了正常测试，通常会在Image模式下，将由样品发出的信号汇聚在分析器前的狭缝处
- 如何对齐有三个维度，在狭缝面内垂直于狭缝，平行于狭缝，狭缝面内外，通常狭缝的30mm x 0.3mm
- 垂直于狭缝比较简单，通常只需要将transmission放到Image中间，这时候光斑也就聚焦在沿着30mm处，在狭缝正中间
- 狭缝面内外，这个就设计到分析器的工作距离，理论上是34mm，如果没有在这个维度聚焦好，整个Image不会收缩到一条线，是发散的形状，甚至能看到部分类似角分辨的信息。
- 这时候就要移动样品Y，让这条线收缩
- 狭缝垂直方向，优于狭缝宽度一般为0.3mm左右，而光斑大小为~20um, 如何在这个方向精细的调节，非常困难。（可以利用Up/Down让电子偏转进入狭缝，然后逐渐减少UP/Down的电压，并在水平和工作距离方向调节激光，知道将up/down降到最低时，trans线还在屏幕上）。



而且，If the focus is poor, the spectrum will be distorted, and if using an apertured exit slit also cropped. 

带有Apeture的slit在没有

As the retarding ratio (EK/EP) increases, there will be increased cropping. This can force you to use a higher pass energy than you might have liked, 
so you need to compensate with a smaller analyzer slit.

The DA30L is relatively relaxed about working distance (i.e. towards/away from the analyzer) -
 anything within 0.5mm of optimal is OK. 


  However it is important to be aware that the analyzer focal position is expected to 
  vary slightly with lens mode, pass energy and the presence of any electric fields around the sample. 



Samples are usually fixed using two component silver epoxy (Epotek H20E), both components should be mixed at 1 : 1 weight ratio. Hardening condition for Epotek H20E:

80 deg C for 3 hrs.
100 deg C for 2 hrs.
120 deg C for 15 mins.
150 deg C for 5 mins.
175 deg C for 45 sec.
We also use Torr-seal to mount sample or fix top-post pin, where we need stronger glue. Remember torr-seal is insulating, and requires graphite coating.



