:github_url: hide

.. Generated automatically by doc/tools/make_rst.py in Godot's source tree.
.. DO NOT EDIT THIS FILE, but the Container.xml source instead.
.. The source is found in doc/classes or modules/<name>/doc_classes.

.. _class_Container:

Container
=========

**Inherits:** :ref:`Control<class_Control>` **<** :ref:`CanvasItem<class_CanvasItem>` **<** :ref:`Node<class_Node>` **<** :ref:`Object<class_Object>`

**Inherited By:** :ref:`AspectRatioContainer<class_AspectRatioContainer>`, :ref:`BoxContainer<class_BoxContainer>`, :ref:`CenterContainer<class_CenterContainer>`, :ref:`EditorProperty<class_EditorProperty>`, :ref:`GraphNode<class_GraphNode>`, :ref:`GridContainer<class_GridContainer>`, :ref:`MarginContainer<class_MarginContainer>`, :ref:`PanelContainer<class_PanelContainer>`, :ref:`ScrollContainer<class_ScrollContainer>`, :ref:`SplitContainer<class_SplitContainer>`, :ref:`TabContainer<class_TabContainer>`, :ref:`ViewportContainer<class_ViewportContainer>`

容器的基础节点。

描述
----

容器的基础节点。\ ``Container`` 包含其他控件，并自动以某种方式排列它们。

Control 可以继承该类来创建自定义的容器类。

方法
----

+------+----------------------------------------------------------------------------------------------------------------------------------------------------+
| void | :ref:`fit_child_in_rect<class_Container_method_fit_child_in_rect>` **(** :ref:`Control<class_Control>` child, :ref:`Rect2<class_Rect2>` rect **)** |
+------+----------------------------------------------------------------------------------------------------------------------------------------------------+
| void | :ref:`queue_sort<class_Container_method_queue_sort>` **(** **)**                                                                                   |
+------+----------------------------------------------------------------------------------------------------------------------------------------------------+

信号
----

.. _class_Container_signal_sort_children:

- **sort_children** **(** **)**

需要对子节点进行排序时发出。

常量
----

.. _class_Container_constant_NOTIFICATION_SORT_CHILDREN:

- **NOTIFICATION_SORT_CHILDREN** = **50** --- 对子节点进行排序时的通知，必须立即服从。

方法说明
--------

.. _class_Container_method_fit_child_in_rect:

- void **fit_child_in_rect** **(** :ref:`Control<class_Control>` child, :ref:`Rect2<class_Rect2>` rect **)**

在给定的矩形中适配子控件。这主要是用于创建自定义容器类的辅助工具。

----

.. _class_Container_method_queue_sort:

- void **queue_sort** **(** **)**

将子节点的重排加入队列。虽然会被自动调用，但也可以在需要时手动调用。

.. |virtual| replace:: :abbr:`virtual (This method should typically be overridden by the user to have any effect.)`
.. |const| replace:: :abbr:`const (This method has no side effects. It doesn't modify any of the instance's member variables.)`
.. |vararg| replace:: :abbr:`vararg (This method accepts any number of arguments after the ones described here.)`
