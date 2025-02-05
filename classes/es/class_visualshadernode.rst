:github_url: hide

.. Generated automatically by doc/tools/make_rst.py in Godot's source tree.
.. DO NOT EDIT THIS FILE, but the VisualShaderNode.xml source instead.
.. The source is found in doc/classes or modules/<name>/doc_classes.

.. _class_VisualShaderNode:

VisualShaderNode
================

**Inherits:** :ref:`Resource<class_Resource>` **<** :ref:`Reference<class_Reference>` **<** :ref:`Object<class_Object>`

**Inherited By:** :ref:`VisualShaderNodeBooleanConstant<class_VisualShaderNodeBooleanConstant>`, :ref:`VisualShaderNodeColorConstant<class_VisualShaderNodeColorConstant>`, :ref:`VisualShaderNodeColorFunc<class_VisualShaderNodeColorFunc>`, :ref:`VisualShaderNodeColorOp<class_VisualShaderNodeColorOp>`, :ref:`VisualShaderNodeCompare<class_VisualShaderNodeCompare>`, :ref:`VisualShaderNodeCubeMap<class_VisualShaderNodeCubeMap>`, :ref:`VisualShaderNodeCustom<class_VisualShaderNodeCustom>`, :ref:`VisualShaderNodeDeterminant<class_VisualShaderNodeDeterminant>`, :ref:`VisualShaderNodeDotProduct<class_VisualShaderNodeDotProduct>`, :ref:`VisualShaderNodeFaceForward<class_VisualShaderNodeFaceForward>`, :ref:`VisualShaderNodeFresnel<class_VisualShaderNodeFresnel>`, :ref:`VisualShaderNodeGroupBase<class_VisualShaderNodeGroupBase>`, :ref:`VisualShaderNodeIf<class_VisualShaderNodeIf>`, :ref:`VisualShaderNodeInput<class_VisualShaderNodeInput>`, :ref:`VisualShaderNodeIs<class_VisualShaderNodeIs>`, :ref:`VisualShaderNodeOuterProduct<class_VisualShaderNodeOuterProduct>`, :ref:`VisualShaderNodeOutput<class_VisualShaderNodeOutput>`, :ref:`VisualShaderNodeScalarClamp<class_VisualShaderNodeScalarClamp>`, :ref:`VisualShaderNodeScalarConstant<class_VisualShaderNodeScalarConstant>`, :ref:`VisualShaderNodeScalarDerivativeFunc<class_VisualShaderNodeScalarDerivativeFunc>`, :ref:`VisualShaderNodeScalarFunc<class_VisualShaderNodeScalarFunc>`, :ref:`VisualShaderNodeScalarInterp<class_VisualShaderNodeScalarInterp>`, :ref:`VisualShaderNodeScalarOp<class_VisualShaderNodeScalarOp>`, :ref:`VisualShaderNodeScalarSmoothStep<class_VisualShaderNodeScalarSmoothStep>`, :ref:`VisualShaderNodeSwitch<class_VisualShaderNodeSwitch>`, :ref:`VisualShaderNodeTexture<class_VisualShaderNodeTexture>`, :ref:`VisualShaderNodeTransformCompose<class_VisualShaderNodeTransformCompose>`, :ref:`VisualShaderNodeTransformConstant<class_VisualShaderNodeTransformConstant>`, :ref:`VisualShaderNodeTransformDecompose<class_VisualShaderNodeTransformDecompose>`, :ref:`VisualShaderNodeTransformFunc<class_VisualShaderNodeTransformFunc>`, :ref:`VisualShaderNodeTransformMult<class_VisualShaderNodeTransformMult>`, :ref:`VisualShaderNodeTransformVecMult<class_VisualShaderNodeTransformVecMult>`, :ref:`VisualShaderNodeUniform<class_VisualShaderNodeUniform>`, :ref:`VisualShaderNodeUniformRef<class_VisualShaderNodeUniformRef>`, :ref:`VisualShaderNodeVec3Constant<class_VisualShaderNodeVec3Constant>`, :ref:`VisualShaderNodeVectorClamp<class_VisualShaderNodeVectorClamp>`, :ref:`VisualShaderNodeVectorCompose<class_VisualShaderNodeVectorCompose>`, :ref:`VisualShaderNodeVectorDecompose<class_VisualShaderNodeVectorDecompose>`, :ref:`VisualShaderNodeVectorDerivativeFunc<class_VisualShaderNodeVectorDerivativeFunc>`, :ref:`VisualShaderNodeVectorDistance<class_VisualShaderNodeVectorDistance>`, :ref:`VisualShaderNodeVectorFunc<class_VisualShaderNodeVectorFunc>`, :ref:`VisualShaderNodeVectorInterp<class_VisualShaderNodeVectorInterp>`, :ref:`VisualShaderNodeVectorLen<class_VisualShaderNodeVectorLen>`, :ref:`VisualShaderNodeVectorOp<class_VisualShaderNodeVectorOp>`, :ref:`VisualShaderNodeVectorRefract<class_VisualShaderNodeVectorRefract>`, :ref:`VisualShaderNodeVectorScalarMix<class_VisualShaderNodeVectorScalarMix>`, :ref:`VisualShaderNodeVectorScalarSmoothStep<class_VisualShaderNodeVectorScalarSmoothStep>`, :ref:`VisualShaderNodeVectorScalarStep<class_VisualShaderNodeVectorScalarStep>`, :ref:`VisualShaderNodeVectorSmoothStep<class_VisualShaderNodeVectorSmoothStep>`

Clase base para nodos en un gráfico de shader visual.

Descripción
----------------------

Visual shader graphs consist of various nodes. Each node in the graph is a separate object and they are represented as a rectangular boxes with title and a set of properties. Each node has also connection ports that allow to connect it to another nodes and control the flow of the shader.

Tutoriales
--------------------

- :doc:`../tutorials/shaders/visual_shaders`

Propiedades
----------------------

+-----------------------+-----------------------------------------------------------------------------------------+--------+
| :ref:`int<class_int>` | :ref:`output_port_for_preview<class_VisualShaderNode_property_output_port_for_preview>` | ``-1`` |
+-----------------------+-----------------------------------------------------------------------------------------+--------+

Métodos
--------------

+-------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`Array<class_Array>`     | :ref:`get_default_input_values<class_VisualShaderNode_method_get_default_input_values>` **(** **)** |const|                                                                 |
+-------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`Variant<class_Variant>` | :ref:`get_input_port_default_value<class_VisualShaderNode_method_get_input_port_default_value>` **(** :ref:`int<class_int>` port **)** |const|                              |
+-------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                          | :ref:`set_default_input_values<class_VisualShaderNode_method_set_default_input_values>` **(** :ref:`Array<class_Array>` values **)**                                        |
+-------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                          | :ref:`set_input_port_default_value<class_VisualShaderNode_method_set_input_port_default_value>` **(** :ref:`int<class_int>` port, :ref:`Variant<class_Variant>` value **)** |
+-------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Señales
--------------

.. _class_VisualShaderNode_signal_editor_refresh_request:

- **editor_refresh_request** **(** **)**

Emitted when the node requests an editor refresh. Currently called only in setter of :ref:`VisualShaderNodeTexture.source<class_VisualShaderNodeTexture_property_source>`, :ref:`VisualShaderNodeTexture<class_VisualShaderNodeTexture>`, and :ref:`VisualShaderNodeCubeMap<class_VisualShaderNodeCubeMap>` (and their derivatives).

Enumeraciones
--------------------------

.. _enum_VisualShaderNode_PortType:

.. _class_VisualShaderNode_constant_PORT_TYPE_SCALAR:

.. _class_VisualShaderNode_constant_PORT_TYPE_VECTOR:

.. _class_VisualShaderNode_constant_PORT_TYPE_BOOLEAN:

.. _class_VisualShaderNode_constant_PORT_TYPE_TRANSFORM:

.. _class_VisualShaderNode_constant_PORT_TYPE_SAMPLER:

.. _class_VisualShaderNode_constant_PORT_TYPE_MAX:

enum **PortType**:

- **PORT_TYPE_SCALAR** = **0** --- Escalar real. Traducido a tipo ``float`` en código shader.

- **PORT_TYPE_VECTOR** = **1** --- Vector 3D de valores de reales. Traducido a tipo ``vec3`` en código shader.

- **PORT_TYPE_BOOLEAN** = **2** --- Tipo booleano. Traducido al tipo ``bool`` en código shader.

- **PORT_TYPE_TRANSFORM** = **3** --- Tipo de transformada. Traducido al tipo ``mat4`` en código shader.

- **PORT_TYPE_SAMPLER** = **4** --- Tipo Sampler. Traducido a referencia del uniforme del muestras en el código shader. Sólo puede utilizarse para puertos de entrada en nodos no uniformes.

- **PORT_TYPE_MAX** = **5** --- Representa el tamaño del enum\ :ref:`PortType<enum_VisualShaderNode_PortType>`.

Descripciones de Propiedades
--------------------------------------------------------

.. _class_VisualShaderNode_property_output_port_for_preview:

- :ref:`int<class_int>` **output_port_for_preview**

+-----------+------------------------------------+
| *Default* | ``-1``                             |
+-----------+------------------------------------+
| *Setter*  | set_output_port_for_preview(value) |
+-----------+------------------------------------+
| *Getter*  | get_output_port_for_preview()      |
+-----------+------------------------------------+

Establece el índice del puerto de salida que se mostrará para la vista previa. Si se establece en ``-1`` no se abrirá ningún puerto para la vista previa.

Descripciones de Métodos
------------------------------------------------

.. _class_VisualShaderNode_method_get_default_input_values:

- :ref:`Array<class_Array>` **get_default_input_values** **(** **)** |const|

Devuelve un :ref:`Array<class_Array>` que contiene valores por defecto para todos los puertos de entrada del nodo en la forma ``[index0, value0, index1, value1, ...]``.

----

.. _class_VisualShaderNode_method_get_input_port_default_value:

- :ref:`Variant<class_Variant>` **get_input_port_default_value** **(** :ref:`int<class_int>` port **)** |const|

Devuelve el valor por defecto de la entrada ``port``.

----

.. _class_VisualShaderNode_method_set_default_input_values:

- void **set_default_input_values** **(** :ref:`Array<class_Array>` values **)**

Establece los valores de los puertos de entrada por defecto utilizando una :ref:`Array<class_Array>` de la forma ``[index0, value0, index1, value1, ...]``. Por ejemplo: ``[0, Vector3(0, 0, 0), 1, Vector3(0, 0, 0)]``.

----

.. _class_VisualShaderNode_method_set_input_port_default_value:

- void **set_input_port_default_value** **(** :ref:`int<class_int>` port, :ref:`Variant<class_Variant>` value **)**

Establece el valor por defecto para la entrada seleccionada ``port``.

.. |virtual| replace:: :abbr:`virtual (This method should typically be overridden by the user to have any effect.)`
.. |const| replace:: :abbr:`const (This method has no side effects. It doesn't modify any of the instance's member variables.)`
.. |vararg| replace:: :abbr:`vararg (This method accepts any number of arguments after the ones described here.)`
