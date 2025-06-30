如何对齐小光斑
========================

当光斑远小于slit宽度时后，如果对准变得非常困难

- 调光的目的是为了正常测试，通常会在Image模式下，将由样品发出的信号汇聚在分析器前的狭缝处
- 如何对齐有三个维度，在狭缝面内垂直于狭缝，平行于狭缝，狭缝面内外，通常狭缝的30mm x 0.3mm
- 垂直于狭缝比较简单，通常只需要将transmission放到Image中间，这时候光斑也就聚焦在沿着30mm处，在狭缝正中间
- 狭缝面内外，这个就设计到分析器的工作距离，理论上是34mm，如果没有在这个维度聚焦好，整个Image不会收缩到一条线，是发散的形状，甚至能看到部分类似角分辨的信息。
- 这时候就要移动样品Y，让这条线收缩
- 狭缝垂直方向，优于狭缝宽度一般为0.3mm左右，而光斑大小为~20um, 如何在这个方向精细的调节，非常困难。



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