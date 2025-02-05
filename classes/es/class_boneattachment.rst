:github_url: hide

.. Generated automatically by doc/tools/make_rst.py in Godot's source tree.
.. DO NOT EDIT THIS FILE, but the BoneAttachment.xml source instead.
.. The source is found in doc/classes or modules/<name>/doc_classes.

.. _class_BoneAttachment:

BoneAttachment
==============

**Inherits:** :ref:`Spatial<class_Spatial>` **<** :ref:`Node<class_Node>` **<** :ref:`Object<class_Object>`

Un nodo que se unirá a un hueso.

Descripción
----------------------

This node must be the child of a :ref:`Skeleton<class_Skeleton>` node. You can then select a bone for this node to attach to. The BoneAttachment node will copy the transform of the selected bone.

Propiedades
----------------------

+-----------------------------+-----------------------------------------------------------+--------+
| :ref:`String<class_String>` | :ref:`bone_name<class_BoneAttachment_property_bone_name>` | ``""`` |
+-----------------------------+-----------------------------------------------------------+--------+

Descripciones de Propiedades
--------------------------------------------------------

.. _class_BoneAttachment_property_bone_name:

- :ref:`String<class_String>` **bone_name**

+-----------+----------------------+
| *Default* | ``""``               |
+-----------+----------------------+
| *Setter*  | set_bone_name(value) |
+-----------+----------------------+
| *Getter*  | get_bone_name()      |
+-----------+----------------------+

El nombre del hueso unido.

.. |virtual| replace:: :abbr:`virtual (This method should typically be overridden by the user to have any effect.)`
.. |const| replace:: :abbr:`const (This method has no side effects. It doesn't modify any of the instance's member variables.)`
.. |vararg| replace:: :abbr:`vararg (This method accepts any number of arguments after the ones described here.)`
