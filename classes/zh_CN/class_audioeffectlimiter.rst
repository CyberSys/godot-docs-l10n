:github_url: hide

.. Generated automatically by doc/tools/make_rst.py in Godot's source tree.
.. DO NOT EDIT THIS FILE, but the AudioEffectLimiter.xml source instead.
.. The source is found in doc/classes or modules/<name>/doc_classes.

.. _class_AudioEffectLimiter:

AudioEffectLimiter
==================

**Inherits:** :ref:`AudioEffect<class_AudioEffect>` **<** :ref:`Resource<class_Resource>` **<** :ref:`Reference<class_Reference>` **<** :ref:`Object<class_Object>`

为音频总线添加一个软剪辑限制器音频效果。

描述
----

限制器类似于压缩器，但灵活性较差，并且设计为不允许声音超过给定的dB阈值。始终建议在主总线中添加一个以减少削波的影响。

软削波开始将峰值降低到略低于阈值水平，并随着输入水平的增加而逐渐增强其效果，从而永不超过阈值。

属性
----

+---------------------------+---------------------------------------------------------------------------+----------+
| :ref:`float<class_float>` | :ref:`ceiling_db<class_AudioEffectLimiter_property_ceiling_db>`           | ``-0.1`` |
+---------------------------+---------------------------------------------------------------------------+----------+
| :ref:`float<class_float>` | :ref:`soft_clip_db<class_AudioEffectLimiter_property_soft_clip_db>`       | ``2.0``  |
+---------------------------+---------------------------------------------------------------------------+----------+
| :ref:`float<class_float>` | :ref:`soft_clip_ratio<class_AudioEffectLimiter_property_soft_clip_ratio>` | ``10.0`` |
+---------------------------+---------------------------------------------------------------------------+----------+
| :ref:`float<class_float>` | :ref:`threshold_db<class_AudioEffectLimiter_property_threshold_db>`       | ``0.0``  |
+---------------------------+---------------------------------------------------------------------------+----------+

属性说明
--------

.. _class_AudioEffectLimiter_property_ceiling_db:

- :ref:`float<class_float>` **ceiling_db**

+-----------+-----------------------+
| *Default* | ``-0.1``              |
+-----------+-----------------------+
| *Setter*  | set_ceiling_db(value) |
+-----------+-----------------------+
| *Getter*  | get_ceiling_db()      |
+-----------+-----------------------+

波形的最大允许值，单位是分贝。数值范围从-20到-0.1。

----

.. _class_AudioEffectLimiter_property_soft_clip_db:

- :ref:`float<class_float>` **soft_clip_db**

+-----------+-------------------------+
| *Default* | ``2.0``                 |
+-----------+-------------------------+
| *Setter*  | set_soft_clip_db(value) |
+-----------+-------------------------+
| *Getter*  | get_soft_clip_db()      |
+-----------+-------------------------+

将增益应用于有限的波，以分贝为单位。取值范围是0到6。

----

.. _class_AudioEffectLimiter_property_soft_clip_ratio:

- :ref:`float<class_float>` **soft_clip_ratio**

+-----------+----------------------------+
| *Default* | ``10.0``                   |
+-----------+----------------------------+
| *Setter*  | set_soft_clip_ratio(value) |
+-----------+----------------------------+
| *Getter*  | get_soft_clip_ratio()      |
+-----------+----------------------------+

----

.. _class_AudioEffectLimiter_property_threshold_db:

- :ref:`float<class_float>` **threshold_db**

+-----------+-------------------------+
| *Default* | ``0.0``                 |
+-----------+-------------------------+
| *Setter*  | set_threshold_db(value) |
+-----------+-------------------------+
| *Getter*  | get_threshold_db()      |
+-----------+-------------------------+

限制器开始生效的阈值，以分贝为单位。值的范围可以从-30到0。

.. |virtual| replace:: :abbr:`virtual (This method should typically be overridden by the user to have any effect.)`
.. |const| replace:: :abbr:`const (This method has no side effects. It doesn't modify any of the instance's member variables.)`
.. |vararg| replace:: :abbr:`vararg (This method accepts any number of arguments after the ones described here.)`
