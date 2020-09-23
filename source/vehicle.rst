設定車載情境
=============================

.. contents:: Table of Contents

Screen Layout Log Analysis
---------------------------------

The  Screen  layout  described  in  this  section  is  intended  to  demonstrate  the  setup  of  each 
screen item that can be used on the main screen. This is the same layout as provided in the 
generic supplied display. 

以下log內容是使用busmaster + usbtoCan dogle 捉取log資料，目的是展示傳送以下canbus訊息，讓smart display 呈現
車載情境畫面。

.. |CanOpen_Form| image:: ./images/CanOpen_Form.png
      :scale: 100%
	  

1. Switch Pre-Operation Mode
---------------------------------------

	To put a node 0x7B(SmartDisplay5) in pre-operational mode 

	+--------+------+------------------------+
	|ID      |DLC   |Data Byte(s)            |
	+========+======+========================+
	|0x000   |2     |80 7B                   |
	+--------+------+------------------------+

2. Set up Object 
-------------------------

Set up Obj Index 0x2000
^^^^^^^^^^^^^^^^^^^^^^^^^^

subIndex 0x01(Item Type)
"""""""""""""""""""""""""

	+--------+------+------------------------+-----------------------+
	|ID      |DLC   |Data Byte(s)            |                       |
	+========+======+========================+=======================+
	|0x67B   |8     |2B 00 20 01 02 00 00 00 | Host -> SmartDisplay5 |
	+--------+------+------------------------+-----------------------+
	|0x000   |7     |60 00 20 01 00 00 00 00 | Host <- SmartDisplay5 |
	+--------+------+------------------------+-----------------------+

subIndex 0x03(position X)
"""""""""""""""""""""""""

	+--------+------+------------------------+-----------------------+
	|ID      |DLC   |Data Byte(s)            |                       |
	+========+======+========================+=======================+
	|0x67B   |8     |2B 00 20 03 17 00 00 00 | Host -> SmartDisplay5 |
	+--------+------+------------------------+-----------------------+
	|0x000   |7     |60 00 20 03 00 00 00 00 | Host <- SmartDisplay5 |
	+--------+------+------------------------+-----------------------+

subIndex 0x04(position Y)
"""""""""""""""""""""""""

	+--------+------+------------------------+-----------------------+
	|ID      |DLC   |Data Byte(s)            |                       |
	+========+======+========================+=======================+
	|0x67B   |8     |2B 00 20 04 49 00 00 00 | Host -> SmartDisplay5 |
	+--------+------+------------------------+-----------------------+
	|0x000   |7     |60 00 20 04 00 00 00 00 | Host <- SmartDisplay5 |
	+--------+------+------------------------+-----------------------+

subIndex 0x05(Style)
"""""""""""""""""""""""""

	+--------+------+------------------------+-----------------------+
	|ID      |DLC   |Data Byte(s)            |                       |
	+========+======+========================+=======================+
	|0x67B   |8     |2B 00 20 05 02 00 00 00 | Host -> SmartDisplay5 |
	+--------+------+------------------------+-----------------------+
	|0x000   |7     |60 00 20 05 00 00 00 00 | Host <- SmartDisplay5 |
	+--------+------+------------------------+-----------------------+

依序更新Object 0x2000~0x2009 如下圖片
""""""""""""""""""""""""""""""""""""""""""""""""""

	.. figure:: ./images/Vehicle_Obj2001.png
		:align: left
		
		0x2001
		
	.. figure:: ./images/Vehicle_Obj2002.png
		:align: left
		
		0x2002
		
	.. figure:: ./images/Vehicle_Obj2003.png
		:align: left
		
		0x2003
		
	.. figure:: ./images/Vehicle_Obj2004.png
		:align: left
		
		0x2004
		
	.. figure:: ./images/Vehicle_Obj2005.png
		:align: left
		
		0x2005
		
	.. figure:: ./images/Vehicle_Obj2006.png
		:align: left
		
		0x2006

	.. figure:: ./images/Vehicle_Obj2007.png
		:align: left
		
		0x2007
		
	.. figure:: ./images/Vehicle_Obj2008.png
		:align: left
		
		0x2008
		
	.. figure:: ./images/Vehicle_Obj2009.png
		:align: left
		
		0x2009

Setup Obj Index 0x2010 Background
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. 

   +--------+------+------------------------+
   |ID      |DLC   |Data Byte(s)            |
   +========+======+========================+
   |0x000   |2     |80 7B                   |
   +--------+------+------------------------+


Step 3 Switch Operation Mode
-------------------------------
	
.. epigraph::

	To put a node 0x7B(SmartDisplay5) in operational mode 

	+--------+------+------------------------+
	|ID      |DLC   |Data Byte(s)            |
	+========+======+========================+
	|0x000   |2     |01 7B                   |
	+--------+------+------------------------+


Step 4 Complete
-------------------------

	.. image:: ./images/Vehicle_total_set.png
		
Step 5 Read/Write Value
-------------------------

.. sidebar:: Code for example

   .. image:: ./images/industry_demo.gif

Write Object 0x2000 can control gauge 

the animote show as below.

and show current ``value``.

``datepicker``
 
 


