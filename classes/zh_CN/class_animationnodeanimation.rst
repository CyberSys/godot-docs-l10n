:github_url: hide

.. Generated automatically by doc/tools/make_rst.py in Godot's source tree.
.. DO NOT EDIT THIS FILE, but the AnimationNodeAnimation.xml source instead.
.. The source is found in doc/classes or modules/<name>/doc_classes.

.. _class_AnimationNodeAnimation:

AnimationNodeAnimation
======================

**Inherits:** :ref:`AnimationRootNode<class_AnimationRootNode>` **<** :ref:`AnimationNode<class_AnimationNode>` **<** :ref:`Resource<class_Resource>` **<** :ref:`Reference<class_Reference>` **<** :ref:`Object<class_Object>`

输入要在\ :ref:`AnimationNodeBlendTree<class_AnimationNodeBlendTree>`\ 中使用的动画。

描述
----

添加到 :ref:`AnimationNodeBlendTree<class_AnimationNodeBlendTree>` 的资源。只具有一个使用 :ref:`animation<class_AnimationNodeAnimation_property_animation>` 属性的输出集。将其作为 :ref:`AnimationNode<class_AnimationNode>` 的输入，将动画融合在一起。

教程
----

- :doc:`AnimationTree <../tutorials/animation/animation_tree>`

- `3D Platformer Demo <https://godotengine.org/asset-library/asset/125>`__

- `Third Person Shooter Demo <https://godotengine.org/asset-library/asset/678>`__

属性
----

+-----------------------------+-------------------------------------------------------------------+--------+
| :ref:`String<class_String>` | :ref:`animation<class_AnimationNodeAnimation_property_animation>` | ``""`` |
+-----------------------------+-------------------------------------------------------------------+--------+

属性说明
--------

.. _class_AnimationNodeAnimation_property_animation:

- :ref:`String<class_String>` **animation**

+-----------+----------------------+
| *Default* | ``""``               |
+-----------+----------------------+
| *Setter*  | set_animation(value) |
+-----------+----------------------+
| *Getter*  | get_animation()      |
+-----------+----------------------+

作为输出使用的动画。它是\ :ref:`AnimationTree.anim_player<class_AnimationTree_property_anim_player>`\ 提供的动画之一。

.. |virtual| replace:: :abbr:`virtual (This method should typically be overridden by the user to have any effect.)`
.. |const| replace:: :abbr:`const (This method has no side effects. It doesn't modify any of the instance's member variables.)`
.. |vararg| replace:: :abbr:`vararg (This method accepts any number of arguments after the ones described here.)`
