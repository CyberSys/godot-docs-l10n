:github_url: hide

.. Generated automatically by doc/tools/make_rst.py in Godot's source tree.
.. DO NOT EDIT THIS FILE, but the VisualScriptSubCall.xml source instead.
.. The source is found in doc/classes or modules/<name>/doc_classes.

.. _class_VisualScriptSubCall:

VisualScriptSubCall
===================

**Inherits:** :ref:`VisualScriptNode<class_VisualScriptNode>` **<** :ref:`Resource<class_Resource>` **<** :ref:`Reference<class_Reference>` **<** :ref:`Object<class_Object>`

在此对象中调用名为 ``_subcall`` 的方法。

描述
----

``VisualScriptSubCall`` 将调用当前脚本中名为 ``_subcall`` 的方法。如果该方法不存在或提供的参数错误，它将失败。

方法
----

+-------------------------------+--------------------------------------------------------------------------------------------------------------------------+
| :ref:`Variant<class_Variant>` | :ref:`_subcall<class_VisualScriptSubCall_method__subcall>` **(** :ref:`Variant<class_Variant>` arguments **)** |virtual| |
+-------------------------------+--------------------------------------------------------------------------------------------------------------------------+

方法说明
--------

.. _class_VisualScriptSubCall_method__subcall:

- :ref:`Variant<class_Variant>` **_subcall** **(** :ref:`Variant<class_Variant>` arguments **)** |virtual|

由该节点调用。

.. |virtual| replace:: :abbr:`virtual (This method should typically be overridden by the user to have any effect.)`
.. |const| replace:: :abbr:`const (This method has no side effects. It doesn't modify any of the instance's member variables.)`
.. |vararg| replace:: :abbr:`vararg (This method accepts any number of arguments after the ones described here.)`
