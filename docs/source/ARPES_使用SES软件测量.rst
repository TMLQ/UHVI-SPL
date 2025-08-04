使用SES软件测量
====================
测试使用Scienta的SES软件，版本1.9.7。快捷方式固定在任务栏上。

关于SES的初步说明
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
区域（Regions）、序列（Sequences）与迭代（Iterations）

所有测量均需在序列编辑器中配置后运行。在序列编辑器中编程测量时，SES提供多层级的结构。相关术语可能容易混淆：序列（Sequence）：待执行的测量任务列表，其中每个条目称为区域（Region）。某些区域类型支持多次迭代（Iteration）（或称扫描）

若设置多区域迭代，需全部完成后才会保存（自然结束或手动停止）。优点：减少磁盘写入时间

若在序列级别设置迭代，则每次迭代后都会保存。优点：防止SES崩溃导致数据丢失, 可在外部分析软件中实时访问数据


Sequence编辑器
----------------------
打开sequence编辑器后，点击Region区域的'New'，新建一个sequence，点击Region的'Edit'，对已有的一个sequence进行编辑。

在Info区域，写上对应的'Sample'和'File Name'，通常两者取同一名字，最后添加下划线，比如'Au111_d'。

在Comment区域，可以写上备注

.. image:: /_static/ARPES_ses_sequence.png
   :alt: sequence editor
   :width: 600px
   :align: center



Normal scan
------------------------------
Normal 模式就是对样品沿着某个方向进行扫描，在图中的Region Editor中选择合适的参数。关闭该界面后，在Sequence Editor中的Sequence Run Mode也选择Normal, 并选择迭代扫描的次数或直到手动停止

.. image:: /_static/ARPES_ses_normal.png
   :alt: ses normal scan
   :width: 300px
   :align: center

ARPES mapping
-----------------
ARPES mapping是在不转动样品的情况下，可以对样品出射的电子在thetay方向进行偏转，得到mapping图像。点击Run Mode中的Edit，可以编辑thetay的范围和步长。注意一点DA30L_08只能到±12°，而DA30L_01可以到±15°

.. image:: /_static/ARPES_ses_DAmap.png
   :alt: arpes mapping
   :width: 500px
   :align: center


Scattering energy scan
----------------------------
Scattering energy scan是对铁靶的质量进行扫描，需要选择Black/White探测器，并在Run Mode中的Edit选择扫描范围和步长，通常是1-20eV，步长为0.5-1eV。用Coil1或2都可以，Switch Magnetization勾不勾也无关紧要。但是可以记录下一个值的对比，6.3eV处的散射强度和Io的比值。

.. image:: /_static/ARPES_ses_scattering_energy.png
   :alt: scattering energy scan
   :width: 500px
   :align: center

.. Note::
    在Scattering energy scan结束后，软件有bug会卡在那里，需要重启。数据找回步骤：在ses软件中，点击open spectrum，点击文件格式"recover spectrum .nfo"，然后在下面文件夹中"ses/backup/work xxxx-xx-xx time/"找到对应的nfo文件并打开。 可点击file将文件save成为pxt.

Ferrum
-----------------------
Ferrum是自旋数据采集模式。选择Black/White探测器，Run Mode选择Edit，选择测试的目标，测I0还是Ispin。通常这里不要勾选Start with default polarization和Start with Coil1，为了节省扫描时间。选择某个特定detector后，coil1和coil2会标记出磁性极化方向。关闭该界面后，在Sequence Editor中的Sequence Run Mode中选择Spin Mapping。测试时需要选择合适的角度和能量步长范围，具体可以参考xxx 章节中，自旋分辨率的计算值。

.. image:: /_static/ARPES_ses_Ferrum.png
   :alt: Ferrum scan
   :width: 600px
   :align: center

Manipulator scan
-----------------------
Manipulator scan是对样品台的移动进行扫描。在Sequence Editor中的Sequence Run Mode中选择manipulator scan，在弹出的Manipulor Scan Editor中，编辑开始位置和结束位置，以及步长。点击Axis行中Start和Stop可以选择当前位置。注意要去的位置都要在扫描前先确认过，避免碰撞分析器。Manipulator scan时不要保存txt格式，这会导致数据写入花大量时间，使扫描变非常慢直到软件卡死。

.. image:: /_static/ARPES_ses_manipulator.png
   :alt: manipulator
   :width: 600px
   :align: center
