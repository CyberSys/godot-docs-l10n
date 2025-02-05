:github_url: hide

.. Generated automatically by doc/tools/make_rst.py in Godot's source tree.
.. DO NOT EDIT THIS FILE, but the EditorProperty.xml source instead.
.. The source is found in doc/classes or modules/<name>/doc_classes.

.. _class_EditorProperty:

EditorProperty
==============

**Inherits:** :ref:`Container<class_Container>` **<** :ref:`Control<class_Control>` **<** :ref:`CanvasItem<class_CanvasItem>` **<** :ref:`Node<class_Node>` **<** :ref:`Object<class_Object>`

Control personalizado para editar las propiedades para añadirlas al inspector.

Descripción
----------------------

Este control permite la edición de propiedades para una o varias propiedades en :ref:`EditorInspector<class_EditorInspector>`. Se agrega a través de :ref:`EditorInspectorPlugin<class_EditorInspectorPlugin>`.

Propiedades
----------------------

+-----------------------------+-----------------------------------------------------------+-----------+
| :ref:`bool<class_bool>`     | :ref:`checkable<class_EditorProperty_property_checkable>` | ``false`` |
+-----------------------------+-----------------------------------------------------------+-----------+
| :ref:`bool<class_bool>`     | :ref:`checked<class_EditorProperty_property_checked>`     | ``false`` |
+-----------------------------+-----------------------------------------------------------+-----------+
| :ref:`bool<class_bool>`     | :ref:`draw_red<class_EditorProperty_property_draw_red>`   | ``false`` |
+-----------------------------+-----------------------------------------------------------+-----------+
| :ref:`bool<class_bool>`     | :ref:`keying<class_EditorProperty_property_keying>`       | ``false`` |
+-----------------------------+-----------------------------------------------------------+-----------+
| :ref:`String<class_String>` | :ref:`label<class_EditorProperty_property_label>`         | ``""``    |
+-----------------------------+-----------------------------------------------------------+-----------+
| :ref:`bool<class_bool>`     | :ref:`read_only<class_EditorProperty_property_read_only>` | ``false`` |
+-----------------------------+-----------------------------------------------------------+-----------+

Métodos
--------------

+-----------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                        | :ref:`add_focusable<class_EditorProperty_method_add_focusable>` **(** :ref:`Control<class_Control>` control **)**                                                                                                                 |
+-----------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                        | :ref:`emit_changed<class_EditorProperty_method_emit_changed>` **(** :ref:`String<class_String>` property, :ref:`Variant<class_Variant>` value, :ref:`String<class_String>` field="", :ref:`bool<class_bool>` changing=false **)** |
+-----------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`Object<class_Object>` | :ref:`get_edited_object<class_EditorProperty_method_get_edited_object>` **(** **)**                                                                                                                                               |
+-----------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`String<class_String>` | :ref:`get_edited_property<class_EditorProperty_method_get_edited_property>` **(** **)**                                                                                                                                           |
+-----------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`String<class_String>` | :ref:`get_tooltip_text<class_EditorProperty_method_get_tooltip_text>` **(** **)** |const|                                                                                                                                         |
+-----------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                        | :ref:`set_bottom_editor<class_EditorProperty_method_set_bottom_editor>` **(** :ref:`Control<class_Control>` editor **)**                                                                                                          |
+-----------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                        | :ref:`update_property<class_EditorProperty_method_update_property>` **(** **)** |virtual|                                                                                                                                         |
+-----------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Señales
--------------

.. _class_EditorProperty_signal_multiple_properties_changed:

- **multiple_properties_changed** **(** :ref:`PoolStringArray<class_PoolStringArray>` properties, :ref:`Array<class_Array>` value **)**

Emitelo si quieres que se modifiquen varias propiedades al mismo tiempo. No lo utilice si se agrega a través de :ref:`EditorInspectorPlugin.parse_property<class_EditorInspectorPlugin_method_parse_property>`.

----

.. _class_EditorProperty_signal_object_id_selected:

- **object_id_selected** **(** :ref:`String<class_String>` property, :ref:`int<class_int>` id **)**

Utilizado por los subinspectores. Emitelo si lo que se seleccionó fue una idde objeto.

----

.. _class_EditorProperty_signal_property_changed:

- **property_changed** **(** :ref:`String<class_String>` property, :ref:`Variant<class_Variant>` value **)**

No lo emita manualmente, utilice en su lugar el método :ref:`emit_changed<class_EditorProperty_method_emit_changed>`.

----

.. _class_EditorProperty_signal_property_checked:

- **property_checked** **(** :ref:`String<class_String>` property, :ref:`bool<class_bool>` checked **)**

Emitido cuando una propiedad fue comprobada. Usado internamente.

----

.. _class_EditorProperty_signal_property_keyed:

- **property_keyed** **(** :ref:`String<class_String>` property **)**

Emite si quieres añadir este valor como una clave de animación (comprueba que la clave esté activada primero).

----

.. _class_EditorProperty_signal_property_keyed_with_value:

- **property_keyed_with_value** **(** :ref:`String<class_String>` property, :ref:`Variant<class_Variant>` value **)**

Emitelo si quieres poner una llave en una propiedad con un solo valor.

----

.. _class_EditorProperty_signal_property_pinned:

- **property_pinned** **(** :ref:`String<class_String>` property, :ref:`bool<class_bool>` pinned **)**

Emit it if you want to mark (or unmark) the value of a property for being saved regardless of being equal to the default value.

The default value is the one the property will get when the node is just instantiated and can come from an ancestor scene in the inheritance/instancing chain, a script or a builtin class.

----

.. _class_EditorProperty_signal_resource_selected:

- **resource_selected** **(** :ref:`String<class_String>` path, :ref:`Resource<class_Resource>` resource **)**

Si quiere que se edite un subrecurso, emita esta señal con el recurso.

----

.. _class_EditorProperty_signal_selected:

- **selected** **(** :ref:`String<class_String>` path, :ref:`int<class_int>` focusable_idx **)**

Emitido cuando se selecciona. Se utiliza internamente.

Descripciones de Propiedades
--------------------------------------------------------

.. _class_EditorProperty_property_checkable:

- :ref:`bool<class_bool>` **checkable**

+-----------+----------------------+
| *Default* | ``false``            |
+-----------+----------------------+
| *Setter*  | set_checkable(value) |
+-----------+----------------------+
| *Getter*  | is_checkable()       |
+-----------+----------------------+

Usado por el inspector, establecido en ``true`` cuando la propiedad es comprobable.

----

.. _class_EditorProperty_property_checked:

- :ref:`bool<class_bool>` **checked**

+-----------+--------------------+
| *Default* | ``false``          |
+-----------+--------------------+
| *Setter*  | set_checked(value) |
+-----------+--------------------+
| *Getter*  | is_checked()       |
+-----------+--------------------+

Usado por el inspector, establecido en ``true`` cuando se comprueba la propiedad.

----

.. _class_EditorProperty_property_draw_red:

- :ref:`bool<class_bool>` **draw_red**

+-----------+---------------------+
| *Default* | ``false``           |
+-----------+---------------------+
| *Setter*  | set_draw_red(value) |
+-----------+---------------------+
| *Getter*  | is_draw_red()       |
+-----------+---------------------+

Used by the inspector, set to ``true`` when the property is drawn with the editor theme's warning color. This is used for editable children's properties.

----

.. _class_EditorProperty_property_keying:

- :ref:`bool<class_bool>` **keying**

+-----------+-------------------+
| *Default* | ``false``         |
+-----------+-------------------+
| *Setter*  | set_keying(value) |
+-----------+-------------------+
| *Getter*  | is_keying()       |
+-----------+-------------------+

Usado por el inspector, establecido en ``true`` cuando la propiedad puede añadir teclas para la animación.

----

.. _class_EditorProperty_property_label:

- :ref:`String<class_String>` **label**

+-----------+------------------+
| *Default* | ``""``           |
+-----------+------------------+
| *Setter*  | set_label(value) |
+-----------+------------------+
| *Getter*  | get_label()      |
+-----------+------------------+

Establezca esta propiedad para cambiar la etiqueta (si quiere mostrar una).

----

.. _class_EditorProperty_property_read_only:

- :ref:`bool<class_bool>` **read_only**

+-----------+----------------------+
| *Default* | ``false``            |
+-----------+----------------------+
| *Setter*  | set_read_only(value) |
+-----------+----------------------+
| *Getter*  | is_read_only()       |
+-----------+----------------------+

Usado por el inspector, establecido en ``true`` cuando la propiedad es de sólo lectura.

Descripciones de Métodos
------------------------------------------------

.. _class_EditorProperty_method_add_focusable:

- void **add_focusable** **(** :ref:`Control<class_Control>` control **)**

Si alguno de los controles añadidos puede obtener el enfoque del teclado, añádalo aquí. Esto asegura que el enfoque se restaurará si el inspector se refresca.

----

.. _class_EditorProperty_method_emit_changed:

- void **emit_changed** **(** :ref:`String<class_String>` property, :ref:`Variant<class_Variant>` value, :ref:`String<class_String>` field="", :ref:`bool<class_bool>` changing=false **)**

Si una o varias propiedades han cambiado, esto debe ser llamado. ``field`` se utiliza en caso de que tu editor pueda modificar los campos por separado (como ejemplo, Vector3.x). El argumento ``changing`` evita que el editor pida que se actualice esta propiedad (deja como ``false`` si no estás seguro).

----

.. _class_EditorProperty_method_get_edited_object:

- :ref:`Object<class_Object>` **get_edited_object** **(** **)**

Obtiene el objeto editado.

----

.. _class_EditorProperty_method_get_edited_property:

- :ref:`String<class_String>` **get_edited_property** **(** **)**

Obtiene la propiedad editada. Si tu editor es para una sola propiedad (añadida mediante el método :ref:`EditorInspectorPlugin.parse_property<class_EditorInspectorPlugin_method_parse_property>`), entonces esto devolverá la propiedad.

----

.. _class_EditorProperty_method_get_tooltip_text:

- :ref:`String<class_String>` **get_tooltip_text** **(** **)** |const|

Must be implemented to provide a custom tooltip to the property editor.

----

.. _class_EditorProperty_method_set_bottom_editor:

- void **set_bottom_editor** **(** :ref:`Control<class_Control>` editor **)**

Puts the ``editor`` control below the property label. The control must be previously added using :ref:`Node.add_child<class_Node_method_add_child>`.

----

.. _class_EditorProperty_method_update_property:

- void **update_property** **(** **)** |virtual|

Cuando se llama a esta función virtual, tu debes actualizar tu editor.

.. |virtual| replace:: :abbr:`virtual (This method should typically be overridden by the user to have any effect.)`
.. |const| replace:: :abbr:`const (This method has no side effects. It doesn't modify any of the instance's member variables.)`
.. |vararg| replace:: :abbr:`vararg (This method accepts any number of arguments after the ones described here.)`
