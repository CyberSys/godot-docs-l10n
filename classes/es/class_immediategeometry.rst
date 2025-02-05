:github_url: hide

.. Generated automatically by doc/tools/make_rst.py in Godot's source tree.
.. DO NOT EDIT THIS FILE, but the ImmediateGeometry.xml source instead.
.. The source is found in doc/classes or modules/<name>/doc_classes.

.. _class_ImmediateGeometry:

ImmediateGeometry
=================

**Inherits:** :ref:`GeometryInstance<class_GeometryInstance>` **<** :ref:`VisualInstance<class_VisualInstance>` **<** :ref:`CullInstance<class_CullInstance>` **<** :ref:`Spatial<class_Spatial>` **<** :ref:`Node<class_Node>` **<** :ref:`Object<class_Object>`

Dibuja una geometría simple desde código.

Descripción
----------------------

Draws simple geometry from code. Uses a drawing mode similar to OpenGL 1.x.

See also :ref:`ArrayMesh<class_ArrayMesh>`, :ref:`MeshDataTool<class_MeshDataTool>` and :ref:`SurfaceTool<class_SurfaceTool>` for procedural geometry generation.

\ **Note:** ImmediateGeometry3D is best suited to small amounts of mesh data that change every frame. It will be slow when handling large amounts of mesh data. If mesh data doesn't change often, use :ref:`ArrayMesh<class_ArrayMesh>`, :ref:`MeshDataTool<class_MeshDataTool>` or :ref:`SurfaceTool<class_SurfaceTool>` instead.

\ **Note:** Godot uses clockwise `winding order <https://learnopengl.com/Advanced-OpenGL/Face-culling>`__ for front faces of triangle primitive modes.

\ **Note:** In case of missing points when handling large amounts of mesh data, try increasing its buffer size limit under :ref:`ProjectSettings.rendering/limits/buffers/immediate_buffer_size_kb<class_ProjectSettings_property_rendering/limits/buffers/immediate_buffer_size_kb>`.

Métodos
--------------

+------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void | :ref:`add_sphere<class_ImmediateGeometry_method_add_sphere>` **(** :ref:`int<class_int>` lats, :ref:`int<class_int>` lons, :ref:`float<class_float>` radius, :ref:`bool<class_bool>` add_uv=true **)** |
+------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void | :ref:`add_vertex<class_ImmediateGeometry_method_add_vertex>` **(** :ref:`Vector3<class_Vector3>` position **)**                                                                                        |
+------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void | :ref:`begin<class_ImmediateGeometry_method_begin>` **(** :ref:`PrimitiveType<enum_Mesh_PrimitiveType>` primitive, :ref:`Texture<class_Texture>` texture=null **)**                                     |
+------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void | :ref:`clear<class_ImmediateGeometry_method_clear>` **(** **)**                                                                                                                                         |
+------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void | :ref:`end<class_ImmediateGeometry_method_end>` **(** **)**                                                                                                                                             |
+------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void | :ref:`set_color<class_ImmediateGeometry_method_set_color>` **(** :ref:`Color<class_Color>` color **)**                                                                                                 |
+------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void | :ref:`set_normal<class_ImmediateGeometry_method_set_normal>` **(** :ref:`Vector3<class_Vector3>` normal **)**                                                                                          |
+------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void | :ref:`set_tangent<class_ImmediateGeometry_method_set_tangent>` **(** :ref:`Plane<class_Plane>` tangent **)**                                                                                           |
+------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void | :ref:`set_uv<class_ImmediateGeometry_method_set_uv>` **(** :ref:`Vector2<class_Vector2>` uv **)**                                                                                                      |
+------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void | :ref:`set_uv2<class_ImmediateGeometry_method_set_uv2>` **(** :ref:`Vector2<class_Vector2>` uv **)**                                                                                                    |
+------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Descripciones de Métodos
------------------------------------------------

.. _class_ImmediateGeometry_method_add_sphere:

- void **add_sphere** **(** :ref:`int<class_int>` lats, :ref:`int<class_int>` lons, :ref:`float<class_float>` radius, :ref:`bool<class_bool>` add_uv=true **)**

Un simple ayudante para dibujar una esfera ultravioleta con la latitud, longitud y radio dados.

----

.. _class_ImmediateGeometry_method_add_vertex:

- void **add_vertex** **(** :ref:`Vector3<class_Vector3>` position **)**

Añade un vértice en el espacio de coordenadas locales con el color/uv/etc actualmente establecido.

----

.. _class_ImmediateGeometry_method_begin:

- void **begin** **(** :ref:`PrimitiveType<enum_Mesh_PrimitiveType>` primitive, :ref:`Texture<class_Texture>` texture=null **)**

Comienza a dibujar (y opcionalmente pasa una anulación de la textura). Cuando termine, llame a :ref:`end<class_ImmediateGeometry_method_end>`. Para más información sobre cómo funciona, busca las referencias ``glBegin()`` y ``glEnd()``.

Para el tipo de primitivo, ver el enum :ref:`PrimitiveType<enum_Mesh_PrimitiveType>`.

----

.. _class_ImmediateGeometry_method_clear:

- void **clear** **(** **)**

Borra todo lo que fue dibujado usando el principio/fin.

----

.. _class_ImmediateGeometry_method_end:

- void **end** **(** **)**

Termina un contexto de dibujo y muestra los resultados.

----

.. _class_ImmediateGeometry_method_set_color:

- void **set_color** **(** :ref:`Color<class_Color>` color **)**

El color del dibujado actual.

----

.. _class_ImmediateGeometry_method_set_normal:

- void **set_normal** **(** :ref:`Vector3<class_Vector3>` normal **)**

La normal del próximo vértice.

----

.. _class_ImmediateGeometry_method_set_tangent:

- void **set_tangent** **(** :ref:`Plane<class_Plane>` tangent **)**

La próxima tangente del vértice (y la orientación binormal).

----

.. _class_ImmediateGeometry_method_set_uv:

- void **set_uv** **(** :ref:`Vector2<class_Vector2>` uv **)**

El próximo vértice es UV.

----

.. _class_ImmediateGeometry_method_set_uv2:

- void **set_uv2** **(** :ref:`Vector2<class_Vector2>` uv **)**

La segunda capa del próximo vértice es UV.

.. |virtual| replace:: :abbr:`virtual (This method should typically be overridden by the user to have any effect.)`
.. |const| replace:: :abbr:`const (This method has no side effects. It doesn't modify any of the instance's member variables.)`
.. |vararg| replace:: :abbr:`vararg (This method accepts any number of arguments after the ones described here.)`
