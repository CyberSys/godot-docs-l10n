:github_url: hide

.. Generated automatically by doc/tools/make_rst.py in Godot's source tree.
.. DO NOT EDIT THIS FILE, but the EditorSettings.xml source instead.
.. The source is found in doc/classes or modules/<name>/doc_classes.

.. _class_EditorSettings:

EditorSettings
==============

**Inherits:** :ref:`Resource<class_Resource>` **<** :ref:`Reference<class_Reference>` **<** :ref:`Object<class_Object>`

Objeto que contiene la configuración del editor independiente del proyecto.

Descripción
----------------------

Objeto que contiene la configuración del editor independiente del proyecto. Estos ajustes son generalmente visibles en el menú **Editor > Ajustes del editor**.

Los nombres de las propiedades utilizan delimitadores de barra para distinguir las secciones. Los valores de los ajustes pueden ser de cualquier tipo :ref:`Variant<class_Variant>`. Se recomienda utilizar ``snake_case`` para que los ajustes del editor sean coherentes con el propio editor Godot.

Se puede acceder a los ajustes mediante los siguientes métodos, como por ejemplo:

::

    # `settings.set("alguna/propiedade", valor)` también funciona ya que esta clase anula `_set()` internamente.
    settings.set_setting("some/property",value)
    
    # `settings.get("alguna/propiedad", value)` también funciona ya que esta clase anula `_get()` internamente.
    settings.get_setting("alguna/propiedad")
    
    var lista_de_configuracion = settings.get_property_list()

\ **Nota:** Esta clase no debe ser instanciada directamente. En su lugar, accede al singleton usando :ref:`EditorInterface.get_editor_settings<class_EditorInterface_method_get_editor_settings>`.

Métodos
--------------

+-----------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                          | :ref:`add_property_info<class_EditorSettings_method_add_property_info>` **(** :ref:`Dictionary<class_Dictionary>` info **)**                                                                                       |
+-----------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                          | :ref:`erase<class_EditorSettings_method_erase>` **(** :ref:`String<class_String>` property **)**                                                                                                                   |
+-----------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`PoolStringArray<class_PoolStringArray>` | :ref:`get_favorites<class_EditorSettings_method_get_favorites>` **(** **)** |const|                                                                                                                                |
+-----------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`Variant<class_Variant>`                 | :ref:`get_project_metadata<class_EditorSettings_method_get_project_metadata>` **(** :ref:`String<class_String>` section, :ref:`String<class_String>` key, :ref:`Variant<class_Variant>` default=null **)** |const| |
+-----------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`String<class_String>`                   | :ref:`get_project_settings_dir<class_EditorSettings_method_get_project_settings_dir>` **(** **)** |const|                                                                                                          |
+-----------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`PoolStringArray<class_PoolStringArray>` | :ref:`get_recent_dirs<class_EditorSettings_method_get_recent_dirs>` **(** **)** |const|                                                                                                                            |
+-----------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`Variant<class_Variant>`                 | :ref:`get_setting<class_EditorSettings_method_get_setting>` **(** :ref:`String<class_String>` name **)** |const|                                                                                                   |
+-----------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`String<class_String>`                   | :ref:`get_settings_dir<class_EditorSettings_method_get_settings_dir>` **(** **)** |const|                                                                                                                          |
+-----------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`bool<class_bool>`                       | :ref:`has_setting<class_EditorSettings_method_has_setting>` **(** :ref:`String<class_String>` name **)** |const|                                                                                                   |
+-----------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`bool<class_bool>`                       | :ref:`property_can_revert<class_EditorSettings_method_property_can_revert>` **(** :ref:`String<class_String>` name **)**                                                                                           |
+-----------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`Variant<class_Variant>`                 | :ref:`property_get_revert<class_EditorSettings_method_property_get_revert>` **(** :ref:`String<class_String>` name **)**                                                                                           |
+-----------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                          | :ref:`set_favorites<class_EditorSettings_method_set_favorites>` **(** :ref:`PoolStringArray<class_PoolStringArray>` dirs **)**                                                                                     |
+-----------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                          | :ref:`set_initial_value<class_EditorSettings_method_set_initial_value>` **(** :ref:`String<class_String>` name, :ref:`Variant<class_Variant>` value, :ref:`bool<class_bool>` update_current **)**                  |
+-----------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                          | :ref:`set_project_metadata<class_EditorSettings_method_set_project_metadata>` **(** :ref:`String<class_String>` section, :ref:`String<class_String>` key, :ref:`Variant<class_Variant>` data **)**                 |
+-----------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                          | :ref:`set_recent_dirs<class_EditorSettings_method_set_recent_dirs>` **(** :ref:`PoolStringArray<class_PoolStringArray>` dirs **)**                                                                                 |
+-----------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                          | :ref:`set_setting<class_EditorSettings_method_set_setting>` **(** :ref:`String<class_String>` name, :ref:`Variant<class_Variant>` value **)**                                                                      |
+-----------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Señales
--------------

.. _class_EditorSettings_signal_settings_changed:

- **settings_changed** **(** **)**

Emitido después de que cualquier ajuste del editor haya cambiado.

Constantes
--------------------

.. _class_EditorSettings_constant_NOTIFICATION_EDITOR_SETTINGS_CHANGED:

- **NOTIFICATION_EDITOR_SETTINGS_CHANGED** = **10000** --- Emitido después de que cualquier ajuste del editor haya cambiado. Es usado por varios plugins de edición para actualizar sus visuales en los cambios de temas o la lógica en los cambios de configuración.

Descripciones de Métodos
------------------------------------------------

.. _class_EditorSettings_method_add_property_info:

- void **add_property_info** **(** :ref:`Dictionary<class_Dictionary>` info **)**

Añade una información de propiedad personalizada a una propiedad. El diccionario debe contener:

- ``name``: :ref:`String<class_String>` (el nombre de la propiedad)

- ``type``: :ref:`int<class_int>` (véase :ref:`Variant.Type<enum_@GlobalScope_Variant.Type>`)

- opcionalmente ``sugerencia``: :ref:`int<class_int>` (ver :ref:`PropertyHint<enum_@GlobalScope_PropertyHint>`) y ``hint_string``: :ref:`String<class_String>`\ 

\ **Ejemplo:**\ 

::

    editor_settings.set("category/property_name", 0)
    
    var informacion_propiedad = {
        "name": "categoria/nombre_propiedad",
        "type": TYPE_INT,
        "hint": PROPERTY_HINT_ENUM,
        "hint_string": "uno, dos, tres"
    }
    
    editor_settings.add_property_info(property_info)

----

.. _class_EditorSettings_method_erase:

- void **erase** **(** :ref:`String<class_String>` property **)**

Borra el ajuste cuyo nombre se especifica en ``property``.

----

.. _class_EditorSettings_method_get_favorites:

- :ref:`PoolStringArray<class_PoolStringArray>` **get_favorites** **(** **)** |const|

Devuelve la lista de archivos y directorios favoritos para este proyecto.

----

.. _class_EditorSettings_method_get_project_metadata:

- :ref:`Variant<class_Variant>` **get_project_metadata** **(** :ref:`String<class_String>` section, :ref:`String<class_String>` key, :ref:`Variant<class_Variant>` default=null **)** |const|

Devuelve los metadatos específicos del proyecto para la ``section`` y la ``key`` especificados. Si los metadatos no existen, se devolverá en su lugar ``default``. Véase también :ref:`set_project_metadata<class_EditorSettings_method_set_project_metadata>`.

----

.. _class_EditorSettings_method_get_project_settings_dir:

- :ref:`String<class_String>` **get_project_settings_dir** **(** **)** |const|

Devuelve la ruta de configuración específica del proyecto. Todos los proyectos tienen un subdirectorio único dentro de la ruta de ajustes donde se guardan los ajustes específicos del proyecto.

----

.. _class_EditorSettings_method_get_recent_dirs:

- :ref:`PoolStringArray<class_PoolStringArray>` **get_recent_dirs** **(** **)** |const|

Devuelve la lista de carpetas visitadas recientemente en el diálogo de archivos de este proyecto.

----

.. _class_EditorSettings_method_get_setting:

- :ref:`Variant<class_Variant>` **get_setting** **(** :ref:`String<class_String>` name **)** |const|

Devuelve el valor del ajuste especificado por ``name``. Esto equivale a usar :ref:`Object.get<class_Object_method_get>` en la instancia EditorSettings.

----

.. _class_EditorSettings_method_get_settings_dir:

- :ref:`String<class_String>` **get_settings_dir** **(** **)** |const|

Obtiene la ruta de configuración global para el motor. Dentro de esta ruta, puedes encontrar algunas rutas estándar como:

\ ``settings/tmp`` - Se utiliza para el almacenamiento temporal de archivos

\ ``settings/templates`` - Donde se encuentran las plantillas de exportación

----

.. _class_EditorSettings_method_has_setting:

- :ref:`bool<class_bool>` **has_setting** **(** :ref:`String<class_String>` name **)** |const|

Devuelve ``true`` si existe el ajuste especificado por ``name``, ``false`` en caso contrario.

----

.. _class_EditorSettings_method_property_can_revert:

- :ref:`bool<class_bool>` **property_can_revert** **(** :ref:`String<class_String>` name **)**

Devuelve ``true`` si el ajuste especificado por ``name`` puede tener su valor revertido al valor por defecto, ``false`` en caso contrario. Cuando este método devuelve ``true``, se mostrará un botón Revertir junto al ajuste en los Ajustes del Editor.

----

.. _class_EditorSettings_method_property_get_revert:

- :ref:`Variant<class_Variant>` **property_get_revert** **(** :ref:`String<class_String>` name **)**

Devuelve el valor por defecto del ajuste especificado por ``name``. Este es el valor que se aplicaría al hacer clic en el botón Revertir en los Ajustes del Editor.

----

.. _class_EditorSettings_method_set_favorites:

- void **set_favorites** **(** :ref:`PoolStringArray<class_PoolStringArray>` dirs **)**

Establece la lista de archivos y directorios favoritos para este proyecto.

----

.. _class_EditorSettings_method_set_initial_value:

- void **set_initial_value** **(** :ref:`String<class_String>` name, :ref:`Variant<class_Variant>` value, :ref:`bool<class_bool>` update_current **)**

Establece el valor inicial del ajuste especificado por ``name`` a ``value``. Esto se usa para proporcionar un valor para el botón Revertir en los Ajustes del Editor. Si ``update_current`` es verdadero, el valor actual del ajuste se fijará también en ``value``.

----

.. _class_EditorSettings_method_set_project_metadata:

- void **set_project_metadata** **(** :ref:`String<class_String>` section, :ref:`String<class_String>` key, :ref:`Variant<class_Variant>` data **)**

Establece metadatos específicos para cada proyecto con la ``section``, ``key`` y ``data`` especificados. Estos metadatos se almacenan fuera de la carpeta del proyecto y, por lo tanto, no se comprobarán en el control de versiones. Ver también :ref:`get_project_metadata<class_EditorSettings_method_get_project_metadata>`.

----

.. _class_EditorSettings_method_set_recent_dirs:

- void **set_recent_dirs** **(** :ref:`PoolStringArray<class_PoolStringArray>` dirs **)**

Establece la lista de carpetas visitadas recientemente en el diálogo de archivos de este proyecto.

----

.. _class_EditorSettings_method_set_setting:

- void **set_setting** **(** :ref:`String<class_String>` name, :ref:`Variant<class_Variant>` value **)**

Establece el valor ``valor`` del ajuste especificado por ``name``. Esto equivale a utilizar el :ref:`Object.set<class_Object_method_set>` en la instancia EditorSettings.

.. |virtual| replace:: :abbr:`virtual (This method should typically be overridden by the user to have any effect.)`
.. |const| replace:: :abbr:`const (This method has no side effects. It doesn't modify any of the instance's member variables.)`
.. |vararg| replace:: :abbr:`vararg (This method accepts any number of arguments after the ones described here.)`
