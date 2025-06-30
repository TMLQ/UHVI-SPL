VLEED 使用
==============
自旋模块控制机柜有两套（Black 和 White），每套三个，从上到下分别是：Magnetic Pulse Control、Ferrum Spin Detector Control、UHV Evaporator。

在 W(100) 单晶上制备 Fe 膜步骤
------------------------------------
步骤分为 4 步：

#. 准备 W(100) 衬底。

#. 用 Ebeam 蒸发源 EFM3 沉积 Fe 膜。

#. 用氧气给料器氧化铁膜。

#. 给铁膜退火去掉多余的氧气。


准备工作
^^^^^^^^^^^^^^^
#. 打开控制柜 FERRUM SPIN DETECTOR CONTROL 电源。

#. 点击 “Measurement/preparation” 按钮，由 Measurement 模式调到 Preparation 模式。

#. 把 FERRUM SPIN DETECTOR CONTROL 控制柜背后的 shield 接线改到盒子上（两个），用于检测蒸发束流。插拔时应捏住前端金属处。

Oxygen Heat Treatment
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
#. 用 “select” 旋钮调节到 Oxygen Hot 模式。

#. 点击 “CH ON/Start Prep” 按钮开始执行操作：
   - **5a**. 首先通过 Oxygen doser 释放氧气，然后循环加热 10 次，每次加热 10 秒，等待 50 秒。
   - **5b**. Black 对应真空计为 VFig2，峰值气压高于 5E-7 mbar 时需要停止操作（实际用到 7~8E-7 mbar）。
   - **5c**. 按返回键可以停止操作。
   - **5d**. Oxygen Heat 结束后 30 分钟内不得开启测试，否则将造成损坏。

.. note::
   如果钨（W）衬底干净或者近期作过处理，则步骤（4）和（5）不用每次都做。

Oxide Flash 2300K
^^^^^^^^^^^^^^^^^^^^^^^^^^
#. 在 FERRUM SPIN DETECTOR CONTROL 上，用 “select” 旋钮调节到 2300K 模式。

#. 点击 “CH ON/Start Prep” 按钮开始执行操作。显示 “Local” 时，代表执行结束。

Open EFM，wait pressure
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
#. 打开真空计 VFig1 和 VFig2，选择项目后按 OK 确定，FIL1 ON。

#. 检查 Fe 棒的位置，并视电流情况调整 Fe 棒的位置（~0.5-1 mm）。

#. 打开蒸发源对应的控制柜 UHV EVAPORATOR “power”，屏幕会快速出现 Filament OK 提示，说明正常，否则会报错。

#. 确保水冷机工作正常；全程注意观察蒸发源温度，一般在 26°C 以下。

#. 用 Voltage 旋钮调节电压到 1000V，用 Current 旋钮调节灯丝电流值使发射电流 Emission 达到 12.5 mA，此时 Fil 约为 1.6A。Filament 许可上限见 EFM 手册，系统设定上限为 2.56A，达到后将不再上升。如 Fil 到达 2.56A 后 Emission 仍低于 12.5 mA，需将电流电压依次归零，调整 Fe 棒位置后重试。生长过程中 Fil 会略有上升，因此最好留有一定余量。

CO Flash
^^^^^^^^^^^^^^^^^^^^
#. 在 FERRUM SPIN DETECTOR CONTROL 控制器上，用 “select” 旋钮调节到 1500K 模式。

#. 点击 “CH ON/Start Prep” 按钮开始执行操作（Black 和 White 同时按），结束后等待 2-3 分钟。

Fe Evaporation
^^^^^^^^^^^^^^^^^^^^^^^^^
#. 手动打开 Black 和 White 的 shutter，计时 15 分钟，此时 Flux 为 153 nA（Black）/90 nA（White），温度 26°C。此处 Flux 每次不同，需对 Fe 棒位置及 Fil/Emission/Flux 随时间的变化做详细记录。

#. 蒸镀时间到，直接同时关闭 Black/White 对应的 UHV EVAPORATOR 电源开关。

#. 立即用 “select” 旋钮将 Black 和 White 调节到 Oxygen Cold 模式，并同时点击 Black 和 White 的 “CH ON/Start Prep” 按钮开始执行操作，过程约 10 分钟（自动计时、停止）。这一步要快，以减少氧化层形成过程中杂质气体的干扰。

#. 手动关闭 shutter。

Annealing
^^^^^^^^^^^^^^^^^^^^^^^
#. 用 “select” 旋钮调节到 Annealing 模式。

#. 点击 “CH ON/Start Prep” 按钮开始执行操作（约 40 秒），完成后将 shield 线接回，计算总时间 30 分钟之后，可以开始测试。

测试
^^^^^^^^^^^^^^^^^^^^^
#. 检查 shield 线是否已经接回。

#. 打开磁控制模块（MAGNETIC PULSE CONTROL）的电源。

#. 打开测试模块的电源。

#. 确认常规模式下工作正常。

#. 使用 SES 软件进行测试。