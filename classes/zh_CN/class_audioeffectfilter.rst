:github_url: hide

.. Generated automatically by doc/tools/make_rst.py in Godot's source tree.
.. DO NOT EDIT THIS FILE, but the AudioEffectFilter.xml source instead.
.. The source is found in doc/classes or modules/<name>/doc_classes.

.. _class_AudioEffectFilter:

AudioEffectFilter
=================

**Inherits:** :ref:`AudioEffect<class_AudioEffect>` **<** :ref:`Resource<class_Resource>` **<** :ref:`Reference<class_Reference>` **<** :ref:`Object<class_Object>`

**Inherited By:** :ref:`AudioEffectBandLimitFilter<class_AudioEffectBandLimitFilter>`, :ref:`AudioEffectBandPassFilter<class_AudioEffectBandPassFilter>`, :ref:`AudioEffectHighPassFilter<class_AudioEffectHighPassFilter>`, :ref:`AudioEffectHighShelfFilter<class_AudioEffectHighShelfFilter>`, :ref:`AudioEffectLowPassFilter<class_AudioEffectLowPassFilter>`, :ref:`AudioEffectLowShelfFilter<class_AudioEffectLowShelfFilter>`, :ref:`AudioEffectNotchFilter<class_AudioEffectNotchFilter>`

为音频总线添加一个滤波器。

描述
----

允许通过\ :ref:`cutoff_hz<class_AudioEffectFilter_property_cutoff_hz>`\ 以外的频率。

教程
----

- :doc:`Audio buses <../tutorials/audio/audio_buses>`

属性
----

+--------------------------------------------------+--------------------------------------------------------------+------------+
| :ref:`float<class_float>`                        | :ref:`cutoff_hz<class_AudioEffectFilter_property_cutoff_hz>` | ``2000.0`` |
+--------------------------------------------------+--------------------------------------------------------------+------------+
| :ref:`FilterDB<enum_AudioEffectFilter_FilterDB>` | :ref:`db<class_AudioEffectFilter_property_db>`               | ``0``      |
+--------------------------------------------------+--------------------------------------------------------------+------------+
| :ref:`float<class_float>`                        | :ref:`gain<class_AudioEffectFilter_property_gain>`           | ``1.0``    |
+--------------------------------------------------+--------------------------------------------------------------+------------+
| :ref:`float<class_float>`                        | :ref:`resonance<class_AudioEffectFilter_property_resonance>` | ``0.5``    |
+--------------------------------------------------+--------------------------------------------------------------+------------+

枚举
----

.. _enum_AudioEffectFilter_FilterDB:

.. _class_AudioEffectFilter_constant_FILTER_6DB:

.. _class_AudioEffectFilter_constant_FILTER_12DB:

.. _class_AudioEffectFilter_constant_FILTER_18DB:

.. _class_AudioEffectFilter_constant_FILTER_24DB:

enum **FilterDB**:

- **FILTER_6DB** = **0**

- **FILTER_12DB** = **1**

- **FILTER_18DB** = **2**

- **FILTER_24DB** = **3**

属性说明
--------

.. _class_AudioEffectFilter_property_cutoff_hz:

- :ref:`float<class_float>` **cutoff_hz**

+-----------+-------------------+
| *Default* | ``2000.0``        |
+-----------+-------------------+
| *Setter*  | set_cutoff(value) |
+-----------+-------------------+
| *Getter*  | get_cutoff()      |
+-----------+-------------------+

滤波器的阈值频率，单位为Hz。

----

.. _class_AudioEffectFilter_property_db:

- :ref:`FilterDB<enum_AudioEffectFilter_FilterDB>` **db**

+-----------+---------------+
| *Default* | ``0``         |
+-----------+---------------+
| *Setter*  | set_db(value) |
+-----------+---------------+
| *Getter*  | get_db()      |
+-----------+---------------+

----

.. _class_AudioEffectFilter_property_gain:

- :ref:`float<class_float>` **gain**

+-----------+-----------------+
| *Default* | ``1.0``         |
+-----------+-----------------+
| *Setter*  | set_gain(value) |
+-----------+-----------------+
| *Getter*  | get_gain()      |
+-----------+-----------------+

滤波后频率的增益量。

----

.. _class_AudioEffectFilter_property_resonance:

- :ref:`float<class_float>` **resonance**

+-----------+----------------------+
| *Default* | ``0.5``              |
+-----------+----------------------+
| *Setter*  | set_resonance(value) |
+-----------+----------------------+
| *Getter*  | get_resonance()      |
+-----------+----------------------+

在截断频率附近的频率范围内的提升量。

.. |virtual| replace:: :abbr:`virtual (This method should typically be overridden by the user to have any effect.)`
.. |const| replace:: :abbr:`const (This method has no side effects. It doesn't modify any of the instance's member variables.)`
.. |vararg| replace:: :abbr:`vararg (This method accepts any number of arguments after the ones described here.)`
