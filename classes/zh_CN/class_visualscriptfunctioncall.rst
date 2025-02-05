:github_url: hide

.. Generated automatically by doc/tools/make_rst.py in Godot's source tree.
.. DO NOT EDIT THIS FILE, but the VisualScriptFunctionCall.xml source instead.
.. The source is found in doc/classes or modules/<name>/doc_classes.

.. _class_VisualScriptFunctionCall:

VisualScriptFunctionCall
========================

**Inherits:** :ref:`VisualScriptNode<class_VisualScriptNode>` **<** :ref:`Resource<class_Resource>` **<** :ref:`Reference<class_Reference>` **<** :ref:`Object<class_Object>`

用于调用函数的可视化脚本节点。

描述
----

``VisualScriptFunctionCall``\ 是在你添加或拖放一个函数到Visual Script图形中时创建。它允许对调用的参数进行调整，例如，函数被调用的对象。

属性
----

+---------------------------------------------------------------+-----------------------------------------------------------------------------------+--------------+
| :ref:`String<class_String>`                                   | :ref:`base_script<class_VisualScriptFunctionCall_property_base_script>`           |              |
+---------------------------------------------------------------+-----------------------------------------------------------------------------------+--------------+
| :ref:`String<class_String>`                                   | :ref:`base_type<class_VisualScriptFunctionCall_property_base_type>`               | ``"Object"`` |
+---------------------------------------------------------------+-----------------------------------------------------------------------------------+--------------+
| :ref:`Variant.Type<enum_@GlobalScope_Variant.Type>`           | :ref:`basic_type<class_VisualScriptFunctionCall_property_basic_type>`             |              |
+---------------------------------------------------------------+-----------------------------------------------------------------------------------+--------------+
| :ref:`CallMode<enum_VisualScriptFunctionCall_CallMode>`       | :ref:`call_mode<class_VisualScriptFunctionCall_property_call_mode>`               | ``0``        |
+---------------------------------------------------------------+-----------------------------------------------------------------------------------+--------------+
| :ref:`String<class_String>`                                   | :ref:`function<class_VisualScriptFunctionCall_property_function>`                 | ``""``       |
+---------------------------------------------------------------+-----------------------------------------------------------------------------------+--------------+
| :ref:`NodePath<class_NodePath>`                               | :ref:`node_path<class_VisualScriptFunctionCall_property_node_path>`               |              |
+---------------------------------------------------------------+-----------------------------------------------------------------------------------+--------------+
| :ref:`RPCCallMode<enum_VisualScriptFunctionCall_RPCCallMode>` | :ref:`rpc_call_mode<class_VisualScriptFunctionCall_property_rpc_call_mode>`       | ``0``        |
+---------------------------------------------------------------+-----------------------------------------------------------------------------------+--------------+
| :ref:`String<class_String>`                                   | :ref:`singleton<class_VisualScriptFunctionCall_property_singleton>`               |              |
+---------------------------------------------------------------+-----------------------------------------------------------------------------------+--------------+
| :ref:`int<class_int>`                                         | :ref:`use_default_args<class_VisualScriptFunctionCall_property_use_default_args>` |              |
+---------------------------------------------------------------+-----------------------------------------------------------------------------------+--------------+
| :ref:`bool<class_bool>`                                       | :ref:`validate<class_VisualScriptFunctionCall_property_validate>`                 | ``true``     |
+---------------------------------------------------------------+-----------------------------------------------------------------------------------+--------------+

枚举
----

.. _enum_VisualScriptFunctionCall_CallMode:

.. _class_VisualScriptFunctionCall_constant_CALL_MODE_SELF:

.. _class_VisualScriptFunctionCall_constant_CALL_MODE_NODE_PATH:

.. _class_VisualScriptFunctionCall_constant_CALL_MODE_INSTANCE:

.. _class_VisualScriptFunctionCall_constant_CALL_MODE_BASIC_TYPE:

.. _class_VisualScriptFunctionCall_constant_CALL_MODE_SINGLETON:

enum **CallMode**:

- **CALL_MODE_SELF** = **0** --- 将在此 :ref:`Object<class_Object>` 上调用该方法。

- **CALL_MODE_NODE_PATH** = **1** --- 该方法将在场景树中的指定 :ref:`Node<class_Node>` 上调用。

- **CALL_MODE_INSTANCE** = **2** --- 该方法将在具有指定类型和脚本的实例化节点上调用。

- **CALL_MODE_BASIC_TYPE** = **3** --- 该方法将在 GDScript 基本类型上调用，例如 :ref:`Vector2<class_Vector2>`\ 。

- **CALL_MODE_SINGLETON** = **4** --- 该方法将在单例上调用。

----

.. _enum_VisualScriptFunctionCall_RPCCallMode:

.. _class_VisualScriptFunctionCall_constant_RPC_DISABLED:

.. _class_VisualScriptFunctionCall_constant_RPC_RELIABLE:

.. _class_VisualScriptFunctionCall_constant_RPC_UNRELIABLE:

.. _class_VisualScriptFunctionCall_constant_RPC_RELIABLE_TO_ID:

.. _class_VisualScriptFunctionCall_constant_RPC_UNRELIABLE_TO_ID:

enum **RPCCallMode**:

- **RPC_DISABLED** = **0** --- 该方法将被本地调用。

- **RPC_RELIABLE** = **1** --- 该方法将被远程调用。

- **RPC_UNRELIABLE** = **2** --- 该方法将使用不可靠的协议远程调用。

- **RPC_RELIABLE_TO_ID** = **3** --- 该方法将被远程调用，用于给定的对等体。

- **RPC_UNRELIABLE_TO_ID** = **4** --- 该方法将被远程调用，用于给定的对等体，使用一个不可靠的协议。

属性说明
--------

.. _class_VisualScriptFunctionCall_property_base_script:

- :ref:`String<class_String>` **base_script**

+----------+------------------------+
| *Setter* | set_base_script(value) |
+----------+------------------------+
| *Getter* | get_base_script()      |
+----------+------------------------+

:ref:`call_mode<class_VisualScriptFunctionCall_property_call_mode>` 设置为 :ref:`CALL_MODE_INSTANCE<class_VisualScriptFunctionCall_constant_CALL_MODE_INSTANCE>` 时使用的脚本。

----

.. _class_VisualScriptFunctionCall_property_base_type:

- :ref:`String<class_String>` **base_type**

+-----------+----------------------+
| *Default* | ``"Object"``         |
+-----------+----------------------+
| *Setter*  | set_base_type(value) |
+-----------+----------------------+
| *Getter*  | get_base_type()      |
+-----------+----------------------+

:ref:`call_mode<class_VisualScriptFunctionCall_property_call_mode>` 设置为 :ref:`CALL_MODE_INSTANCE<class_VisualScriptFunctionCall_constant_CALL_MODE_INSTANCE>` 时要使用的基本类型。

----

.. _class_VisualScriptFunctionCall_property_basic_type:

- :ref:`Variant.Type<enum_@GlobalScope_Variant.Type>` **basic_type**

+----------+-----------------------+
| *Setter* | set_basic_type(value) |
+----------+-----------------------+
| *Getter* | get_basic_type()      |
+----------+-----------------------+

:ref:`call_mode<class_VisualScriptFunctionCall_property_call_mode>` 设置为 :ref:`CALL_MODE_BASIC_TYPE<class_VisualScriptFunctionCall_constant_CALL_MODE_BASIC_TYPE>` 时使用的类型。

----

.. _class_VisualScriptFunctionCall_property_call_mode:

- :ref:`CallMode<enum_VisualScriptFunctionCall_CallMode>` **call_mode**

+-----------+----------------------+
| *Default* | ``0``                |
+-----------+----------------------+
| *Setter*  | set_call_mode(value) |
+-----------+----------------------+
| *Getter*  | get_call_mode()      |
+-----------+----------------------+

``call_mode`` 决定了方法将被调用的目标对象。参阅\ :ref:`CallMode<enum_VisualScriptFunctionCall_CallMode>`\ 的选项。

----

.. _class_VisualScriptFunctionCall_property_function:

- :ref:`String<class_String>` **function**

+-----------+---------------------+
| *Default* | ``""``              |
+-----------+---------------------+
| *Setter*  | set_function(value) |
+-----------+---------------------+
| *Getter*  | get_function()      |
+-----------+---------------------+

要调用的函数的名称。

----

.. _class_VisualScriptFunctionCall_property_node_path:

- :ref:`NodePath<class_NodePath>` **node_path**

+----------+----------------------+
| *Setter* | set_base_path(value) |
+----------+----------------------+
| *Getter* | get_base_path()      |
+----------+----------------------+

:ref:`call_mode<class_VisualScriptFunctionCall_property_call_mode>` 设置为 :ref:`CALL_MODE_NODE_PATH<class_VisualScriptFunctionCall_constant_CALL_MODE_NODE_PATH>` 时使用的节点路径。

----

.. _class_VisualScriptFunctionCall_property_rpc_call_mode:

- :ref:`RPCCallMode<enum_VisualScriptFunctionCall_RPCCallMode>` **rpc_call_mode**

+-----------+--------------------------+
| *Default* | ``0``                    |
+-----------+--------------------------+
| *Setter*  | set_rpc_call_mode(value) |
+-----------+--------------------------+
| *Getter*  | get_rpc_call_mode()      |
+-----------+--------------------------+

RPC 调用的模式。有关更多详细信息，请参阅 :ref:`Node.rpc<class_Node_method_rpc>`\ ，有关可用选项，请参阅 :ref:`RPCCallMode<enum_VisualScriptFunctionCall_RPCCallMode>`\ 。

----

.. _class_VisualScriptFunctionCall_property_singleton:

- :ref:`String<class_String>` **singleton**

+----------+----------------------+
| *Setter* | set_singleton(value) |
+----------+----------------------+
| *Getter* | get_singleton()      |
+----------+----------------------+

调用方法的单例。当 :ref:`call_mode<class_VisualScriptFunctionCall_property_call_mode>` 设置为 :ref:`CALL_MODE_SINGLETON<class_VisualScriptFunctionCall_constant_CALL_MODE_SINGLETON>` 时使用。

----

.. _class_VisualScriptFunctionCall_property_use_default_args:

- :ref:`int<class_int>` **use_default_args**

+----------+-----------------------------+
| *Setter* | set_use_default_args(value) |
+----------+-----------------------------+
| *Getter* | get_use_default_args()      |
+----------+-----------------------------+

调用函数时将使用的默认参数的数量。不能大于方法声明中可用默认参数的数量。

----

.. _class_VisualScriptFunctionCall_property_validate:

- :ref:`bool<class_bool>` **validate**

+-----------+---------------------+
| *Default* | ``true``            |
+-----------+---------------------+
| *Setter*  | set_validate(value) |
+-----------+---------------------+
| *Getter*  | get_validate()      |
+-----------+---------------------+

如果\ ``false``\ ，调用错误将被忽略，例如参数数量错误。

.. |virtual| replace:: :abbr:`virtual (This method should typically be overridden by the user to have any effect.)`
.. |const| replace:: :abbr:`const (This method has no side effects. It doesn't modify any of the instance's member variables.)`
.. |vararg| replace:: :abbr:`vararg (This method accepts any number of arguments after the ones described here.)`
