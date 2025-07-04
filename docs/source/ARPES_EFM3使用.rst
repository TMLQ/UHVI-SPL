EFM3的使用
=========================
 EFM3是小型的电子束蒸发源，可以用来制备直径不超过15mm的薄膜。在我们设备上，用来制备自旋分辨的Fe膜。

参数表
----------------
.. image:: /_static/EFM specs.jpg
   :alt: EFM参数表
   :width: 500px
   :align: center
      

电极接线
----------------

#. 4pin的feedthrough提供灯丝电流以及热电电压
#. SHV-SHV同轴线提供高压
#. flux monitor提供束流监测 BNC线

检查
----------------
#. 4pin， A和B之间的电阻应该小于1Ω，这些pin之间都需要对地绝缘
#. 4pin，D和C之间以及到地之间的电阻应该小于2Ω
#. 检查HV和地之间，以及HV和灯丝之间的电阻，需要大于2MΩ。加高压到400V，观察有无打火出现。是不是可以用耐压表进行测试。


如何装样金属棒
----------------
#. 棒的总长度不应该超过50mm，通常来说45mm。在退回到最远的状态时，棒的顶端不能和灯丝定义的平面接触
#. 棒的直径1.5-2.5mm，通常来说2mm
#. 装棒的时候，推进器要退回到最远，不然有可能在插入的过程中损坏灯丝
#. 棒要尽量做到直，不能有弯曲
#. 检查棒安装的同轴性，通过顶部束流出来的口观察，建议在真空外组一个仔细对准（精准到±1mm）

操作
----------
烘烤
^^^^^^^^^^^
使用前需要烘烤，最高可以到250°C。烘烤前需要把接线和水管移除，并吹干水。

除气
^^^^^^^^^^^^^^^
#. 烘烤之后需要进行除气，除气时气压不能超过5E-6mbar。除气过程中不能接水管，不然的话水冷罩的温度没法超过100°C。除气时，所有水都需要吹走。

#. 温度可以从热电偶读取，不能超过300°C。

#. 除气过程中，shutter保持关闭。防止杂质污染样品

用灯丝加热除气
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
#. 高压设为0V
#. 灯丝电流缓慢升到2.7A
#. 铜的水冷罩会逐渐升温。通常来说会经历1-2小时，来达到200-300℃。
#. 我们是一般加热到 220度以上保持几个小时直到气压明显下降，然后等它一晚上慢慢降温，这个过程始终保持 turbo 开着，因为气压可能到-7

蒸发源除气以及使用
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
两者步骤一致

#. 连接并打开水冷

#. 将高压加到1000V

#. 逐渐升高灯丝电流到1.7A，再继续增加电流知道看到Emission电流出现以及flux monitor显示1nA左右

#. 如果没有电流出现，需要调整棒的位置。缓慢将棒推进并慢慢，注意不要接触到灯丝。逐渐增加电流到想要的束流。

#. 注意如果出现一个flux monitor突然的增加，快速将发射电流下降

White

.. image:: /_static/EFMwhite.jpg
   :alt: EFMwihte
   :width: 500px
   :align: center

Black

.. image:: /_static/EFMblack.jpg
   :alt: EFMblack
   :width: 500px
   :align: center