:github_url: hide

.. Generated automatically by doc/tools/make_rst.py in Godot's source tree.
.. DO NOT EDIT THIS FILE, but the Skeleton.xml source instead.
.. The source is found in doc/classes or modules/<name>/doc_classes.

.. _class_Skeleton:

Skeleton
========

**Inherits:** :ref:`Spatial<class_Spatial>` **<** :ref:`Node<class_Node>` **<** :ref:`Object<class_Object>`

Esqueleto de personajes y objetos animados.

Descripción
----------------------

Skeleton provides a hierarchical interface for managing bones, including pose, rest and animation (see :ref:`Animation<class_Animation>`). It can also use ragdoll physics.

The overall transform of a bone with respect to the skeleton is determined by the following hierarchical order: rest pose, custom pose and pose.

Note that "global pose" below refers to the overall transform of the bone with respect to skeleton, so it not the actual global/world transform of the bone.

Tutoriales
--------------------

- `3D Inverse Kinematics Demo <https://godotengine.org/asset-library/asset/523>`__

- `Third Person Shooter Demo <https://godotengine.org/asset-library/asset/678>`__

Métodos
--------------

+-------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                      | :ref:`add_bone<class_Skeleton_method_add_bone>` **(** :ref:`String<class_String>` name **)**                                                                                                                                                             |
+-------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                      | :ref:`bind_child_node_to_bone<class_Skeleton_method_bind_child_node_to_bone>` **(** :ref:`int<class_int>` bone_idx, :ref:`Node<class_Node>` node **)**                                                                                                   |
+-------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                      | :ref:`clear_bones<class_Skeleton_method_clear_bones>` **(** **)**                                                                                                                                                                                        |
+-------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                      | :ref:`clear_bones_global_pose_override<class_Skeleton_method_clear_bones_global_pose_override>` **(** **)**                                                                                                                                              |
+-------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`int<class_int>`                     | :ref:`find_bone<class_Skeleton_method_find_bone>` **(** :ref:`String<class_String>` name **)** |const|                                                                                                                                                   |
+-------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`int<class_int>`                     | :ref:`get_bone_count<class_Skeleton_method_get_bone_count>` **(** **)** |const|                                                                                                                                                                          |
+-------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`Transform<class_Transform>`         | :ref:`get_bone_custom_pose<class_Skeleton_method_get_bone_custom_pose>` **(** :ref:`int<class_int>` bone_idx **)** |const|                                                                                                                               |
+-------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`Transform<class_Transform>`         | :ref:`get_bone_global_pose<class_Skeleton_method_get_bone_global_pose>` **(** :ref:`int<class_int>` bone_idx **)** |const|                                                                                                                               |
+-------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`Transform<class_Transform>`         | :ref:`get_bone_global_pose_no_override<class_Skeleton_method_get_bone_global_pose_no_override>` **(** :ref:`int<class_int>` bone_idx **)** |const|                                                                                                       |
+-------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`String<class_String>`               | :ref:`get_bone_name<class_Skeleton_method_get_bone_name>` **(** :ref:`int<class_int>` bone_idx **)** |const|                                                                                                                                             |
+-------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`int<class_int>`                     | :ref:`get_bone_parent<class_Skeleton_method_get_bone_parent>` **(** :ref:`int<class_int>` bone_idx **)** |const|                                                                                                                                         |
+-------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`Transform<class_Transform>`         | :ref:`get_bone_pose<class_Skeleton_method_get_bone_pose>` **(** :ref:`int<class_int>` bone_idx **)** |const|                                                                                                                                             |
+-------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`Transform<class_Transform>`         | :ref:`get_bone_rest<class_Skeleton_method_get_bone_rest>` **(** :ref:`int<class_int>` bone_idx **)** |const|                                                                                                                                             |
+-------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`Array<class_Array>`                 | :ref:`get_bound_child_nodes_to_bone<class_Skeleton_method_get_bound_child_nodes_to_bone>` **(** :ref:`int<class_int>` bone_idx **)** |const|                                                                                                             |
+-------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`bool<class_bool>`                   | :ref:`is_bone_rest_disabled<class_Skeleton_method_is_bone_rest_disabled>` **(** :ref:`int<class_int>` bone_idx **)** |const|                                                                                                                             |
+-------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                      | :ref:`localize_rests<class_Skeleton_method_localize_rests>` **(** **)**                                                                                                                                                                                  |
+-------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                      | :ref:`physical_bones_add_collision_exception<class_Skeleton_method_physical_bones_add_collision_exception>` **(** :ref:`RID<class_RID>` exception **)**                                                                                                  |
+-------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                      | :ref:`physical_bones_remove_collision_exception<class_Skeleton_method_physical_bones_remove_collision_exception>` **(** :ref:`RID<class_RID>` exception **)**                                                                                            |
+-------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                      | :ref:`physical_bones_start_simulation<class_Skeleton_method_physical_bones_start_simulation>` **(** :ref:`Array<class_Array>` bones=[  ] **)**                                                                                                           |
+-------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                      | :ref:`physical_bones_stop_simulation<class_Skeleton_method_physical_bones_stop_simulation>` **(** **)**                                                                                                                                                  |
+-------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`SkinReference<class_SkinReference>` | :ref:`register_skin<class_Skeleton_method_register_skin>` **(** :ref:`Skin<class_Skin>` skin **)**                                                                                                                                                       |
+-------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                      | :ref:`set_bone_custom_pose<class_Skeleton_method_set_bone_custom_pose>` **(** :ref:`int<class_int>` bone_idx, :ref:`Transform<class_Transform>` custom_pose **)**                                                                                        |
+-------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                      | :ref:`set_bone_disable_rest<class_Skeleton_method_set_bone_disable_rest>` **(** :ref:`int<class_int>` bone_idx, :ref:`bool<class_bool>` disable **)**                                                                                                    |
+-------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                      | :ref:`set_bone_global_pose_override<class_Skeleton_method_set_bone_global_pose_override>` **(** :ref:`int<class_int>` bone_idx, :ref:`Transform<class_Transform>` pose, :ref:`float<class_float>` amount, :ref:`bool<class_bool>` persistent=false **)** |
+-------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                      | :ref:`set_bone_name<class_Skeleton_method_set_bone_name>` **(** :ref:`int<class_int>` bone_idx, :ref:`String<class_String>` name **)**                                                                                                                   |
+-------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                      | :ref:`set_bone_parent<class_Skeleton_method_set_bone_parent>` **(** :ref:`int<class_int>` bone_idx, :ref:`int<class_int>` parent_idx **)**                                                                                                               |
+-------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                      | :ref:`set_bone_pose<class_Skeleton_method_set_bone_pose>` **(** :ref:`int<class_int>` bone_idx, :ref:`Transform<class_Transform>` pose **)**                                                                                                             |
+-------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                      | :ref:`set_bone_rest<class_Skeleton_method_set_bone_rest>` **(** :ref:`int<class_int>` bone_idx, :ref:`Transform<class_Transform>` rest **)**                                                                                                             |
+-------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                      | :ref:`unbind_child_node_from_bone<class_Skeleton_method_unbind_child_node_from_bone>` **(** :ref:`int<class_int>` bone_idx, :ref:`Node<class_Node>` node **)**                                                                                           |
+-------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                      | :ref:`unparent_bone_and_rest<class_Skeleton_method_unparent_bone_and_rest>` **(** :ref:`int<class_int>` bone_idx **)**                                                                                                                                   |
+-------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Señales
--------------

.. _class_Skeleton_signal_skeleton_updated:

- **skeleton_updated** **(** **)**

Constantes
--------------------

.. _class_Skeleton_constant_NOTIFICATION_UPDATE_SKELETON:

- **NOTIFICATION_UPDATE_SKELETON** = **50**

Descripciones de Métodos
------------------------------------------------

.. _class_Skeleton_method_add_bone:

- void **add_bone** **(** :ref:`String<class_String>` name **)**

Añade un hueso, con el nombre ``name``. :ref:`get_bone_count<class_Skeleton_method_get_bone_count>` se convertirá en el índice óseo.

----

.. _class_Skeleton_method_bind_child_node_to_bone:

- void **bind_child_node_to_bone** **(** :ref:`int<class_int>` bone_idx, :ref:`Node<class_Node>` node **)**

*Pronto estara obsoleto.*

----

.. _class_Skeleton_method_clear_bones:

- void **clear_bones** **(** **)**

Limpia todos los huesos de este esqueleto.

----

.. _class_Skeleton_method_clear_bones_global_pose_override:

- void **clear_bones_global_pose_override** **(** **)**

----

.. _class_Skeleton_method_find_bone:

- :ref:`int<class_int>` **find_bone** **(** :ref:`String<class_String>` name **)** |const|

Devuelve el índice óseo que coincide con ``name`` como su nombre.

----

.. _class_Skeleton_method_get_bone_count:

- :ref:`int<class_int>` **get_bone_count** **(** **)** |const|

Devuelve la cantidad de huesos del esqueleto.

----

.. _class_Skeleton_method_get_bone_custom_pose:

- :ref:`Transform<class_Transform>` **get_bone_custom_pose** **(** :ref:`int<class_int>` bone_idx **)** |const|

Devuelve la postura personalizada del hueso especificado. La postura personalizada se aplica sobre la postura de descanso.

----

.. _class_Skeleton_method_get_bone_global_pose:

- :ref:`Transform<class_Transform>` **get_bone_global_pose** **(** :ref:`int<class_int>` bone_idx **)** |const|

Devuelve la transformación general del hueso especificado, con respecto al esqueleto. Siendo relativa al marco del esqueleto, esta no es la transformación "global" real del hueso.

----

.. _class_Skeleton_method_get_bone_global_pose_no_override:

- :ref:`Transform<class_Transform>` **get_bone_global_pose_no_override** **(** :ref:`int<class_int>` bone_idx **)** |const|

Returns the overall transform of the specified bone, with respect to the skeleton, but without any global pose overrides. Being relative to the skeleton frame, this is not the actual "global" transform of the bone.

----

.. _class_Skeleton_method_get_bone_name:

- :ref:`String<class_String>` **get_bone_name** **(** :ref:`int<class_int>` bone_idx **)** |const|

Devuelve el nombre del hueso en el índice ``index``.

----

.. _class_Skeleton_method_get_bone_parent:

- :ref:`int<class_int>` **get_bone_parent** **(** :ref:`int<class_int>` bone_idx **)** |const|

Devuelve el índice de hueso que es el padre del hueso en ``bone_idx``. Si es -1, entonces el hueso no tiene padre.

\ **Nota:** El hueso padre devuelto siempre será menor que ``bone_idx``.

----

.. _class_Skeleton_method_get_bone_pose:

- :ref:`Transform<class_Transform>` **get_bone_pose** **(** :ref:`int<class_int>` bone_idx **)** |const|

Devuelve la transformación de la postura del hueso especificado. La pose se aplica encima de la pose personalizada, que se aplica encima de la pose de descanso.

----

.. _class_Skeleton_method_get_bone_rest:

- :ref:`Transform<class_Transform>` **get_bone_rest** **(** :ref:`int<class_int>` bone_idx **)** |const|

Devuelve la transformación de reposo para un hueso ``bone_idx``.

----

.. _class_Skeleton_method_get_bound_child_nodes_to_bone:

- :ref:`Array<class_Array>` **get_bound_child_nodes_to_bone** **(** :ref:`int<class_int>` bone_idx **)** |const|

*Pronto estara obsoleto.*

----

.. _class_Skeleton_method_is_bone_rest_disabled:

- :ref:`bool<class_bool>` **is_bone_rest_disabled** **(** :ref:`int<class_int>` bone_idx **)** |const|

----

.. _class_Skeleton_method_localize_rests:

- void **localize_rests** **(** **)**

----

.. _class_Skeleton_method_physical_bones_add_collision_exception:

- void **physical_bones_add_collision_exception** **(** :ref:`RID<class_RID>` exception **)**

----

.. _class_Skeleton_method_physical_bones_remove_collision_exception:

- void **physical_bones_remove_collision_exception** **(** :ref:`RID<class_RID>` exception **)**

----

.. _class_Skeleton_method_physical_bones_start_simulation:

- void **physical_bones_start_simulation** **(** :ref:`Array<class_Array>` bones=[  ] **)**

----

.. _class_Skeleton_method_physical_bones_stop_simulation:

- void **physical_bones_stop_simulation** **(** **)**

----

.. _class_Skeleton_method_register_skin:

- :ref:`SkinReference<class_SkinReference>` **register_skin** **(** :ref:`Skin<class_Skin>` skin **)**

----

.. _class_Skeleton_method_set_bone_custom_pose:

- void **set_bone_custom_pose** **(** :ref:`int<class_int>` bone_idx, :ref:`Transform<class_Transform>` custom_pose **)**

----

.. _class_Skeleton_method_set_bone_disable_rest:

- void **set_bone_disable_rest** **(** :ref:`int<class_int>` bone_idx, :ref:`bool<class_bool>` disable **)**

----

.. _class_Skeleton_method_set_bone_global_pose_override:

- void **set_bone_global_pose_override** **(** :ref:`int<class_int>` bone_idx, :ref:`Transform<class_Transform>` pose, :ref:`float<class_float>` amount, :ref:`bool<class_bool>` persistent=false **)**

----

.. _class_Skeleton_method_set_bone_name:

- void **set_bone_name** **(** :ref:`int<class_int>` bone_idx, :ref:`String<class_String>` name **)**

----

.. _class_Skeleton_method_set_bone_parent:

- void **set_bone_parent** **(** :ref:`int<class_int>` bone_idx, :ref:`int<class_int>` parent_idx **)**

Establece el índice óseo ``parent_idx`` como el padre del hueso en ``bone_idx``. Si es -1, entonces el hueso no tiene padre.

\ **Nota:** ``parent_idx`` debe ser menor que ``bone_idx``.

----

.. _class_Skeleton_method_set_bone_pose:

- void **set_bone_pose** **(** :ref:`int<class_int>` bone_idx, :ref:`Transform<class_Transform>` pose **)**

Sets the pose transform for bone ``bone_idx``.

----

.. _class_Skeleton_method_set_bone_rest:

- void **set_bone_rest** **(** :ref:`int<class_int>` bone_idx, :ref:`Transform<class_Transform>` rest **)**

Establece la transformación del descanso para el hueso ``bone_idx``.

----

.. _class_Skeleton_method_unbind_child_node_from_bone:

- void **unbind_child_node_from_bone** **(** :ref:`int<class_int>` bone_idx, :ref:`Node<class_Node>` node **)**

*Pronto estara obsoleto.*

----

.. _class_Skeleton_method_unparent_bone_and_rest:

- void **unparent_bone_and_rest** **(** :ref:`int<class_int>` bone_idx **)**

.. |virtual| replace:: :abbr:`virtual (This method should typically be overridden by the user to have any effect.)`
.. |const| replace:: :abbr:`const (This method has no side effects. It doesn't modify any of the instance's member variables.)`
.. |vararg| replace:: :abbr:`vararg (This method accepts any number of arguments after the ones described here.)`
