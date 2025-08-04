VLEED 铁膜制备
===================
自旋模块控制机柜有两套（Black 和 White），每套三个，从上到下分别是：Magnetic Pulse Control、Ferrum Spin Detector Control、UHV Evaporator。

在 W(100) 单晶上制备 Fe 膜步骤
------------------------------------
具体操作请参考《Ferrum Spin-Decector Technical Reference Manual》p26-29。此处仅将步骤简要列出，并补充一些注意事项。

.. image:: /_static/VLEED_Fe.png
   :alt: 铁膜制备过程
   :width: 500px
   :align: center


在开腔烘烤后准备干净的 W(100) 衬底
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
在烘烤Ferrum探测器和对Ebeam蒸发源灯丝除气后，在蒸铁前，接下来的步骤需要重复两到三次，一次制备下来需要2小时。

1. Hot Oxygen Treatment， 大约17分钟

#. 等待系统冷却，气压回到初始值， 30分钟左右。

#. Oxygen-flash 去除钨和碳的氧化物

#. 待真空恢复后，重复Oxygen Flash 2次， 每次间隔 30 分钟。

#. 在连续的制备循环之间，要让探测器的晶体冷却下来，同时使气压恢复。

Hot Oxygen Treatment
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
#. 用 “select” 旋钮调节到 Oxygen Hot 模式。

#. 点击 “CH ON/Start Prep” 按钮开始执行操作, 按返回键可以停止操作。

.. note::
   Black 对应真空计为 VFig2，在这一步中峰值气压7~8E-7 mbar
   White 对应真空计为 VFig1，在这一步中峰值气压1E-7 mbar

Oxide Flash 2300K
^^^^^^^^^^^^^^^^^^^^^^^^^^
#. 在 FERRUM SPIN DETECTOR CONTROL 上，用 “select” 旋钮调节到 2300K 模式。

#. 点击 “CH ON/Start Prep” 按钮开始执行操作。显示 “Local” 时，代表执行结束。

.. note::
   处理结束后，需要等待至少30分钟才能切换到测量模式，否则会损坏光电倍增管（channeltron）。

长铁膜步骤
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
#. 开腔烘烤后，在不接水冷的情况下，对灯丝进行除气，电流2.7A，时间1小时。

#. 接上水冷，全程注意观察蒸发源温度，一般在 26°C 以下

#. 把 FERRUM SPIN DETECTOR CONTROL 控制柜背后的 shield 接线改到盒子上（两个），用于检测蒸发束流。插拔时应捏住前端金属处。

#. 检查 Fe 棒的位置，一般会在上次生长位置前进0.5-1 mm。

#. 先用 Voltage 旋钮增加电压到 1000V，再用 Current 旋钮缓慢增加灯丝电流值，Black通常在1.7A左右出现发射电流，直到发射电流Emission达到12.5mA。

#. 观察VLEED气压，等待稳定，建议等5分钟

#. CO-flash，等待2-3分钟

#. 打开shutter，计时15分钟，记录此时的Flux，通常为100-200 nA.

#. 结束后，先将电流降低至零，然后在把电压降低至零， 关闭shutter.

#. Oxygen cold.大约10分钟，这一步要快，以减少氧化层形成过程中杂质气体的干扰。

#. Annealing.

#. 用 Voltage 旋钮调节电压到 1000V，用 Current 旋钮调节灯丝电流值使发射电流 Emission 达到 12.5 mA，此时 Fil 约为 1.6A。Filament 许可上限见 EFM 手册，系统设定上限为 2.56A，达到后将不再上升。如 Fil 到达 2.56A 后 Emission 仍低于 12.5 mA，需将电流电压依次归零，调整 Fe 棒位置后重试。生长过程中 Fil 会略有上升，因此最好留有一定余量。


测试
^^^^^^^^^^^^^^^^^^^^^
#. 检查 shield 线是否已经接回。

#. 打开磁控制模块（MAGNETIC PULSE CONTROL）的电源。

#. 打开测试模块的电源。

#. 确认常规模式下工作正常。

#. 使用 SES 软件进行测试。