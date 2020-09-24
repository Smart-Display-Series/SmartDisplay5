Screen Layout
=============================

.. contents:: Table of Contents

Screen Layout Log Analysis
---------------------------------

..

  The Screen layout described in this section is intended to demonstrate the setup of vehicle 
  situation that can be used on the **SmartDisplay5**.

  This log shows the control of each object parameter ``x``, ``y``, ``style`` 
  through the canopen method ``SDO``, ``NMT`` in the following content

.. |CanOpen_Form| image:: ./images/CanOpen_Form.png
      :scale: 100%
    

1. Switch Pre-Operation Mode
---------------------------------------

  To put a node **0x7B** in pre-operational mode 
  
  +--------+------+------------------------+
  |ID      |DLC   |Data Byte(s)            |
  +========+======+========================+
  |0x000   |2     |80 7B                   |
  +--------+------+------------------------+

  .. note::
  
    the node id **0x7B** is **SmartDisplay5** canopen id.

2. Setup Object 
-------------------------

Set up Obj Index 0x2000
^^^^^^^^^^^^^^^^^^^^^^^^^^

subIndex 0x01(Item Type)
"""""""""""""""""""""""""

  The Host send item value ``2`` to **object index** 0x2000 **subindex** 0x01 through 
  canopen ``SDO``

  +--------+------+------------------------+---------------------------+
  |ID      |DLC   |Data Byte(s)            |                           |
  +========+======+========================+===========================+
  |0x67B   |8     |2B 00 20 01 02 00 00 00 | **Host -> SmartDisplay5** |
  +--------+------+------------------------+---------------------------+
  |0x000   |7     |60 00 20 01 00 00 00 00 | **Host <- SmartDisplay5** |
  +--------+------+------------------------+---------------------------+
  
  .. note::
  
    the item value **2** is type **Gauge**

subIndex 0x03(position X)
"""""""""""""""""""""""""

  The Host send position X value ``0x17`` to **object index** 0x2000 **subindex** 0x03 through 
  canopen ``SDO``.
  
  +--------+------+------------------------+---------------------------+
  |ID      |DLC   |Data Byte(s)            |                           |
  +========+======+========================+===========================+
  |0x67B   |8     |2B 00 20 03 17 00 00 00 | **Host -> SmartDisplay5** |
  +--------+------+------------------------+---------------------------+
  |0x000   |7     |60 00 20 03 00 00 00 00 | **Host <- SmartDisplay5** |
  +--------+------+------------------------+---------------------------+

subIndex 0x04(position Y)
"""""""""""""""""""""""""

  The Host send position Y value ``0x49`` to **object index** 0x2000 **subindex** 0x04 through 
  canopen ``SDO``.

  +--------+------+------------------------+---------------------------+
  |ID      |DLC   |Data Byte(s)            |                           |
  +========+======+========================+===========================+
  |0x67B   |8     |2B 00 20 04 49 00 00 00 | **Host -> SmartDisplay5** |
  +--------+------+------------------------+---------------------------+
  |0x000   |7     |60 00 20 04 00 00 00 00 | **Host <- SmartDisplay5** |
  +--------+------+------------------------+---------------------------+

subIndex 0x05(Style)
"""""""""""""""""""""""""

  The Host send position Y value ``0x49`` to **object index** 0x2000 **subindex** 0x05 through 
  canopen ``SDO``.

  +--------+------+------------------------+---------------------------+
  |ID      |DLC   |Data Byte(s)            |                           |
  +========+======+========================+===========================+
  |0x67B   |8     |2B 00 20 05 05 00 00 00 | **Host -> SmartDisplay5** |
  +--------+------+------------------------+---------------------------+
  |0x000   |7     |60 00 20 05 00 00 00 00 | **Host <- SmartDisplay5** |
  +--------+------+------------------------+---------------------------+
  
  .. |Gauge_5| image:: ./images/Gauge_5.png
    :scale: 5%
    
  .. note ::

    put the object 0x2000, set the item type **Gauge**, and select style image |Gauge_5|  
    plac x, y at 0x17, 0x49
  

Update Object 0x2001~0x2009 
""""""""""""""""""""""""""""""""""""""""""""""""""
  
.. |Temperature_2| image:: ./images/Temperature_2.png
  :scale: 20%
  
.. |Battery_1| image:: ./images/Battery_1.png
  :scale: 20%
  
.. |button_8| image:: ./images/button_8.png
  :scale: 20%  
  
.. |button_10| image:: ./images/button_10.png
  :scale: 20%
  
.. |Indicator_0| image:: ./images/Indicator_0.png
  :scale: 20%
  
.. 

  This update object 0x2001 ~ 0x2009 through **canopen** ``SDO`` in the picture below.

  .. figure:: ./images/Vehicle_Obj2001.png
      :align: left                        

  .. Note::

    put the object **0x2001**, set the item type **Battery**, and select style |Battery_1|
    plac x, y at 0x17, 0x49 
    
  .. figure:: ./images/Vehicle_Obj2002.png
    :align: left
      
  .. Note::

    put the object **0x2002**, set the item type **Temperature**, and select style |Temperature_2|  
    plac x, y at 0x17, 0x49
      
  .. figure:: ./images/Vehicle_Obj2003.png
    :align: left
      
  .. Note::

    put the object **0x2003**, set the item type **Toggle Button**, and select style |button_10|  
    plac x, y at 0x17, 0x49
      
  .. figure:: ./images/Vehicle_Obj2004.png
    :align: left

  .. Note::
      
    put the object **0x2004**, set the item type **Toggle Button**, and select style |button_8|  
    plac x, y at 0x17, 0x49
      
  .. figure:: ./images/Vehicle_Obj2005.png
    :align: left
      
  .. Note::
    
    put the object **0x2005**, set the item type **Indicator**, and select style |Indicator_0|  
    plac x, y at 0x17, 0x49
      
  .. figure:: ./images/Vehicle_Obj2006.png
    :align: left
      
  .. Note::
      
    put the object **0x2006**, set the item type **empty**.

  .. figure:: ./images/Vehicle_Obj2007.png
    :align: left

  .. Note::
          
    put the object **0x2007**, set the item type **empty**.
      
  .. figure:: ./images/Vehicle_Obj2008.png
    :align: left

  .. Note::
          
    put the object **0x2008**, set the item type **empty**.
      
  .. figure:: ./images/Vehicle_Obj2009.png
    :align: left

  .. Note::       

    put the object **0x2009**, set the item type **empty**.

3. Setup Background
---------------------------------------------

  .. |background_Industry| image:: ./images/background_Industry.png
   :scale: 15%

  .. |background_Vehicle| image:: ./images/background_Vehicle.png
   :scale: 15%

  .. |background_Medical| image:: ./images/background_Medical.png
   :scale: 15%

  +-------------------------+----------------------+----------------------+ 
  | **0x00**  Industry      |**0x01**  Vehicle     |**0x02**  Medical     |
  +=========================+======================+======================+
  | |background_Industry|   | |background_Vehicle| | |background_Vehicle| |
  +-------------------------+----------------------+----------------------+


  Select Picture value **0x01** to setting backgruond picturen at operation-mode through Canopne ``SDO``.

  +--------+------+------------------------+---------------------------+
  |ID      |DLC   |Data Byte(s)            |                           |
  +========+======+========================+===========================+
  |0x67B   |8     |2F 00 21 00 01 00 00 00 | **Host -> SmartDisplay5** |
  +--------+------+------------------------+---------------------------+
  |0x5FB   |8     |60 00 21 00 00 00 00 00 | **Host <- SmartDisplay5** |
  +--------+------+------------------------+---------------------------+


4. Switch Operation Mode
-------------------------------
  
.. epigraph::

  To put a node 0x7B(SmartDisplay5) in operational mode 
  
  +--------+------+------------------------+
  |ID      |DLC   |Data Byte(s)            |
  +========+======+========================+
  |0x000   |2     |80 7B                   |
  +--------+------+------------------------+
  
  your can see this layout in below screen.

  .. image:: ./images/Vehicle_total_set.png
    
5. Control **SmartDisplay5**
----------------------------------

.. sidebar:: Control Gauge of Vehicle Dashboard 

   .. image:: ./images/vehicle-animation.gif

..

    Write Object index 0x2000 subindx 0x07 ``set value`` **0~100** through CANOPEN ``PDO``
    that can control gauge the animation show as right.


