:github_url: hide

.. Generated automatically by doc/tools/make_rst.py in Godot's source tree.
.. DO NOT EDIT THIS FILE, but the Particles.xml source instead.
.. The source is found in doc/classes or modules/<name>/doc_classes.

.. _class_Particles:

Particles
=========

**Inherits:** :ref:`GeometryInstance<class_GeometryInstance>` **<** :ref:`VisualInstance<class_VisualInstance>` **<** :ref:`CullInstance<class_CullInstance>` **<** :ref:`Spatial<class_Spatial>` **<** :ref:`Node<class_Node>` **<** :ref:`Object<class_Object>`

GPU-based 3D particle emitter.

Descripción
----------------------

3D particle node used to create a variety of particle systems and effects. ``Particles`` features an emitter that generates some number of particles at a given rate.

Use the ``process_material`` property to add a :ref:`ParticlesMaterial<class_ParticlesMaterial>` to configure particle appearance and behavior. Alternatively, you can add a :ref:`ShaderMaterial<class_ShaderMaterial>` which will be applied to all particles.

\ **Note:** ``Particles`` only work when using the GLES3 renderer. If using the GLES2 renderer, use :ref:`CPUParticles<class_CPUParticles>` instead. You can convert ``Particles`` to :ref:`CPUParticles<class_CPUParticles>` by selecting the node, clicking the **Particles** menu at the top of the 3D editor viewport then choosing **Convert to CPUParticles**.

\ **Note:** After working on a Particles node, remember to update its :ref:`visibility_aabb<class_Particles_property_visibility_aabb>` by selecting it, clicking the **Particles** menu at the top of the 3D editor viewport then choose **Generate Visibility AABB**. Otherwise, particles may suddenly disappear depending on the camera position and angle.

Tutoriales
--------------------

- :doc:`Controlling thousands of fish with Particles <../tutorials/performance/vertex_animation/controlling_thousands_of_fish>`

- `Third Person Shooter Demo <https://godotengine.org/asset-library/asset/678>`__

Propiedades
----------------------

+--------------------------------------------+--------------------------------------------------------------------+---------------------------------+
| :ref:`int<class_int>`                      | :ref:`amount<class_Particles_property_amount>`                     | ``8``                           |
+--------------------------------------------+--------------------------------------------------------------------+---------------------------------+
| :ref:`DrawOrder<enum_Particles_DrawOrder>` | :ref:`draw_order<class_Particles_property_draw_order>`             | ``0``                           |
+--------------------------------------------+--------------------------------------------------------------------+---------------------------------+
| :ref:`Mesh<class_Mesh>`                    | :ref:`draw_pass_1<class_Particles_property_draw_pass_1>`           |                                 |
+--------------------------------------------+--------------------------------------------------------------------+---------------------------------+
| :ref:`Mesh<class_Mesh>`                    | :ref:`draw_pass_2<class_Particles_property_draw_pass_2>`           |                                 |
+--------------------------------------------+--------------------------------------------------------------------+---------------------------------+
| :ref:`Mesh<class_Mesh>`                    | :ref:`draw_pass_3<class_Particles_property_draw_pass_3>`           |                                 |
+--------------------------------------------+--------------------------------------------------------------------+---------------------------------+
| :ref:`Mesh<class_Mesh>`                    | :ref:`draw_pass_4<class_Particles_property_draw_pass_4>`           |                                 |
+--------------------------------------------+--------------------------------------------------------------------+---------------------------------+
| :ref:`int<class_int>`                      | :ref:`draw_passes<class_Particles_property_draw_passes>`           | ``1``                           |
+--------------------------------------------+--------------------------------------------------------------------+---------------------------------+
| :ref:`bool<class_bool>`                    | :ref:`emitting<class_Particles_property_emitting>`                 | ``true``                        |
+--------------------------------------------+--------------------------------------------------------------------+---------------------------------+
| :ref:`float<class_float>`                  | :ref:`explosiveness<class_Particles_property_explosiveness>`       | ``0.0``                         |
+--------------------------------------------+--------------------------------------------------------------------+---------------------------------+
| :ref:`int<class_int>`                      | :ref:`fixed_fps<class_Particles_property_fixed_fps>`               | ``0``                           |
+--------------------------------------------+--------------------------------------------------------------------+---------------------------------+
| :ref:`bool<class_bool>`                    | :ref:`fract_delta<class_Particles_property_fract_delta>`           | ``true``                        |
+--------------------------------------------+--------------------------------------------------------------------+---------------------------------+
| :ref:`float<class_float>`                  | :ref:`lifetime<class_Particles_property_lifetime>`                 | ``1.0``                         |
+--------------------------------------------+--------------------------------------------------------------------+---------------------------------+
| :ref:`bool<class_bool>`                    | :ref:`local_coords<class_Particles_property_local_coords>`         | ``true``                        |
+--------------------------------------------+--------------------------------------------------------------------+---------------------------------+
| :ref:`bool<class_bool>`                    | :ref:`one_shot<class_Particles_property_one_shot>`                 | ``false``                       |
+--------------------------------------------+--------------------------------------------------------------------+---------------------------------+
| :ref:`float<class_float>`                  | :ref:`preprocess<class_Particles_property_preprocess>`             | ``0.0``                         |
+--------------------------------------------+--------------------------------------------------------------------+---------------------------------+
| :ref:`Material<class_Material>`            | :ref:`process_material<class_Particles_property_process_material>` |                                 |
+--------------------------------------------+--------------------------------------------------------------------+---------------------------------+
| :ref:`float<class_float>`                  | :ref:`randomness<class_Particles_property_randomness>`             | ``0.0``                         |
+--------------------------------------------+--------------------------------------------------------------------+---------------------------------+
| :ref:`float<class_float>`                  | :ref:`speed_scale<class_Particles_property_speed_scale>`           | ``1.0``                         |
+--------------------------------------------+--------------------------------------------------------------------+---------------------------------+
| :ref:`AABB<class_AABB>`                    | :ref:`visibility_aabb<class_Particles_property_visibility_aabb>`   | ``AABB( -4, -4, -4, 8, 8, 8 )`` |
+--------------------------------------------+--------------------------------------------------------------------+---------------------------------+

Métodos
--------------

+-------------------------+-------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`AABB<class_AABB>` | :ref:`capture_aabb<class_Particles_method_capture_aabb>` **(** **)** |const|                                                              |
+-------------------------+-------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`Mesh<class_Mesh>` | :ref:`get_draw_pass_mesh<class_Particles_method_get_draw_pass_mesh>` **(** :ref:`int<class_int>` pass **)** |const|                       |
+-------------------------+-------------------------------------------------------------------------------------------------------------------------------------------+
| void                    | :ref:`restart<class_Particles_method_restart>` **(** **)**                                                                                |
+-------------------------+-------------------------------------------------------------------------------------------------------------------------------------------+
| void                    | :ref:`set_draw_pass_mesh<class_Particles_method_set_draw_pass_mesh>` **(** :ref:`int<class_int>` pass, :ref:`Mesh<class_Mesh>` mesh **)** |
+-------------------------+-------------------------------------------------------------------------------------------------------------------------------------------+

Enumeraciones
--------------------------

.. _enum_Particles_DrawOrder:

.. _class_Particles_constant_DRAW_ORDER_INDEX:

.. _class_Particles_constant_DRAW_ORDER_LIFETIME:

.. _class_Particles_constant_DRAW_ORDER_VIEW_DEPTH:

enum **DrawOrder**:

- **DRAW_ORDER_INDEX** = **0** --- Las partículas se dibujan en el orden en que se emiten.

- **DRAW_ORDER_LIFETIME** = **1** --- Las partículas se dibujan en orden según el tiempo de vida restante.

- **DRAW_ORDER_VIEW_DEPTH** = **2** --- Las partículas se dibujan en orden de profundidad.

Constantes
--------------------

.. _class_Particles_constant_MAX_DRAW_PASSES:

- **MAX_DRAW_PASSES** = **4** --- Número máximo de pases de dibujado soportados.

Descripciones de Propiedades
--------------------------------------------------------

.. _class_Particles_property_amount:

- :ref:`int<class_int>` **amount**

+-----------+-------------------+
| *Default* | ``8``             |
+-----------+-------------------+
| *Setter*  | set_amount(value) |
+-----------+-------------------+
| *Getter*  | get_amount()      |
+-----------+-------------------+

The number of particles emitted in one emission cycle (corresponding to the :ref:`lifetime<class_Particles_property_lifetime>`).

\ **Note:** Changing :ref:`amount<class_Particles_property_amount>` will reset the particle emission, therefore removing all particles that were already emitted before changing :ref:`amount<class_Particles_property_amount>`.

----

.. _class_Particles_property_draw_order:

- :ref:`DrawOrder<enum_Particles_DrawOrder>` **draw_order**

+-----------+-----------------------+
| *Default* | ``0``                 |
+-----------+-----------------------+
| *Setter*  | set_draw_order(value) |
+-----------+-----------------------+
| *Getter*  | get_draw_order()      |
+-----------+-----------------------+

Orden de dibujo de las partículas. Utiliza los valores de :ref:`DrawOrder<enum_Particles_DrawOrder>`.

----

.. _class_Particles_property_draw_pass_1:

- :ref:`Mesh<class_Mesh>` **draw_pass_1**

+----------+---------------------------+
| *Setter* | set_draw_pass_mesh(value) |
+----------+---------------------------+
| *Getter* | get_draw_pass_mesh()      |
+----------+---------------------------+

:ref:`Mesh<class_Mesh>` que se dibuja para el primer pase de dibujado.

----

.. _class_Particles_property_draw_pass_2:

- :ref:`Mesh<class_Mesh>` **draw_pass_2**

+----------+---------------------------+
| *Setter* | set_draw_pass_mesh(value) |
+----------+---------------------------+
| *Getter* | get_draw_pass_mesh()      |
+----------+---------------------------+

:ref:`Mesh<class_Mesh>` que se dibuja para el segundo pase de dibujado.

----

.. _class_Particles_property_draw_pass_3:

- :ref:`Mesh<class_Mesh>` **draw_pass_3**

+----------+---------------------------+
| *Setter* | set_draw_pass_mesh(value) |
+----------+---------------------------+
| *Getter* | get_draw_pass_mesh()      |
+----------+---------------------------+

:ref:`Mesh<class_Mesh>` que se dibuja para el tercer pase de dibujado.

----

.. _class_Particles_property_draw_pass_4:

- :ref:`Mesh<class_Mesh>` **draw_pass_4**

+----------+---------------------------+
| *Setter* | set_draw_pass_mesh(value) |
+----------+---------------------------+
| *Getter* | get_draw_pass_mesh()      |
+----------+---------------------------+

:ref:`Mesh<class_Mesh>` que se dibuja para el cuarto pase de dibujado.

----

.. _class_Particles_property_draw_passes:

- :ref:`int<class_int>` **draw_passes**

+-----------+------------------------+
| *Default* | ``1``                  |
+-----------+------------------------+
| *Setter*  | set_draw_passes(value) |
+-----------+------------------------+
| *Getter*  | get_draw_passes()      |
+-----------+------------------------+

El número de pases de dibujado cuando se renderizan las partículas.

----

.. _class_Particles_property_emitting:

- :ref:`bool<class_bool>` **emitting**

+-----------+---------------------+
| *Default* | ``true``            |
+-----------+---------------------+
| *Setter*  | set_emitting(value) |
+-----------+---------------------+
| *Getter*  | is_emitting()       |
+-----------+---------------------+

Si ``true``, se están emitiendo partículas.

----

.. _class_Particles_property_explosiveness:

- :ref:`float<class_float>` **explosiveness**

+-----------+--------------------------------+
| *Default* | ``0.0``                        |
+-----------+--------------------------------+
| *Setter*  | set_explosiveness_ratio(value) |
+-----------+--------------------------------+
| *Getter*  | get_explosiveness_ratio()      |
+-----------+--------------------------------+

Ratio de tiempo entre cada emisión. Si ``0``, las partículas se emiten continuamente. Si ``1``, todas las partículas se emiten simultáneamente.

----

.. _class_Particles_property_fixed_fps:

- :ref:`int<class_int>` **fixed_fps**

+-----------+----------------------+
| *Default* | ``0``                |
+-----------+----------------------+
| *Setter*  | set_fixed_fps(value) |
+-----------+----------------------+
| *Getter*  | get_fixed_fps()      |
+-----------+----------------------+

La velocidad de fotogramas del sistema de partículas está fijada a un valor. Por ejemplo, cambiando el valor a 2 hará que las partículas se rendericen a 2 fotogramas por segundo. Ten en cuenta que esto no ralentiza la simulación del sistema de partículas en sí.

----

.. _class_Particles_property_fract_delta:

- :ref:`bool<class_bool>` **fract_delta**

+-----------+-----------------------------+
| *Default* | ``true``                    |
+-----------+-----------------------------+
| *Setter*  | set_fractional_delta(value) |
+-----------+-----------------------------+
| *Getter*  | get_fractional_delta()      |
+-----------+-----------------------------+

Si ``true``, resulta en un cálculo delta fraccionario que tiene un efecto de visualización de partículas más suave.

----

.. _class_Particles_property_lifetime:

- :ref:`float<class_float>` **lifetime**

+-----------+---------------------+
| *Default* | ``1.0``             |
+-----------+---------------------+
| *Setter*  | set_lifetime(value) |
+-----------+---------------------+
| *Getter*  | get_lifetime()      |
+-----------+---------------------+

The amount of time each particle will exist (in seconds).

----

.. _class_Particles_property_local_coords:

- :ref:`bool<class_bool>` **local_coords**

+-----------+----------------------------------+
| *Default* | ``true``                         |
+-----------+----------------------------------+
| *Setter*  | set_use_local_coordinates(value) |
+-----------+----------------------------------+
| *Getter*  | get_use_local_coordinates()      |
+-----------+----------------------------------+

Si ``true``, las partículas usan el espacio de coordenadas del nodo padre. Si ``false``, usan las coordenadas globales.

----

.. _class_Particles_property_one_shot:

- :ref:`bool<class_bool>` **one_shot**

+-----------+---------------------+
| *Default* | ``false``           |
+-----------+---------------------+
| *Setter*  | set_one_shot(value) |
+-----------+---------------------+
| *Getter*  | get_one_shot()      |
+-----------+---------------------+

Si ``true``, sólo se emitirán partículas de ``amount``.

----

.. _class_Particles_property_preprocess:

- :ref:`float<class_float>` **preprocess**

+-----------+-----------------------------+
| *Default* | ``0.0``                     |
+-----------+-----------------------------+
| *Setter*  | set_pre_process_time(value) |
+-----------+-----------------------------+
| *Getter*  | get_pre_process_time()      |
+-----------+-----------------------------+

Cantidad de tiempo para preprocesar las partículas antes de que comience la animación. Te permite iniciar la animación un tiempo después de que las partículas hayan empezado a emitir.

----

.. _class_Particles_property_process_material:

- :ref:`Material<class_Material>` **process_material**

+----------+-----------------------------+
| *Setter* | set_process_material(value) |
+----------+-----------------------------+
| *Getter* | get_process_material()      |
+----------+-----------------------------+

:ref:`Material<class_Material>` para procesar partículas. Puede ser un :ref:`ParticlesMaterial<class_ParticlesMaterial>` o un :ref:`ShaderMaterial<class_ShaderMaterial>`.

----

.. _class_Particles_property_randomness:

- :ref:`float<class_float>` **randomness**

+-----------+-----------------------------+
| *Default* | ``0.0``                     |
+-----------+-----------------------------+
| *Setter*  | set_randomness_ratio(value) |
+-----------+-----------------------------+
| *Getter*  | get_randomness_ratio()      |
+-----------+-----------------------------+

Ratio de aleatoriedad de las emisiones.

----

.. _class_Particles_property_speed_scale:

- :ref:`float<class_float>` **speed_scale**

+-----------+------------------------+
| *Default* | ``1.0``                |
+-----------+------------------------+
| *Setter*  | set_speed_scale(value) |
+-----------+------------------------+
| *Getter*  | get_speed_scale()      |
+-----------+------------------------+

Relación de escala de velocidad. Un valor de ``0`` puede ser usado para pausar las partículas.

----

.. _class_Particles_property_visibility_aabb:

- :ref:`AABB<class_AABB>` **visibility_aabb**

+-----------+---------------------------------+
| *Default* | ``AABB( -4, -4, -4, 8, 8, 8 )`` |
+-----------+---------------------------------+
| *Setter*  | set_visibility_aabb(value)      |
+-----------+---------------------------------+
| *Getter*  | get_visibility_aabb()           |
+-----------+---------------------------------+

The :ref:`AABB<class_AABB>` that determines the node's region which needs to be visible on screen for the particle system to be active.

Grow the box if particles suddenly appear/disappear when the node enters/exits the screen. The :ref:`AABB<class_AABB>` can be grown via code or with the **Particles → Generate AABB** editor tool.

\ **Note:** If the :ref:`ParticlesMaterial<class_ParticlesMaterial>` in use is configured to cast shadows, you may want to enlarge this AABB to ensure the shadow is updated when particles are off-screen.

Descripciones de Métodos
------------------------------------------------

.. _class_Particles_method_capture_aabb:

- :ref:`AABB<class_AABB>` **capture_aabb** **(** **)** |const|

Devuelve el cuadro delimitador alineado con el eje que contiene todas las partículas que están activas en el cuadro actual.

----

.. _class_Particles_method_get_draw_pass_mesh:

- :ref:`Mesh<class_Mesh>` **get_draw_pass_mesh** **(** :ref:`int<class_int>` pass **)** |const|

Devuelve la :ref:`Mesh<class_Mesh>` que se dibuja en el índice ``pass``.

----

.. _class_Particles_method_restart:

- void **restart** **(** **)**

Reinicia la emisión de partículas, limpiando las partículas existentes.

----

.. _class_Particles_method_set_draw_pass_mesh:

- void **set_draw_pass_mesh** **(** :ref:`int<class_int>` pass, :ref:`Mesh<class_Mesh>` mesh **)**

Establece la :ref:`Mesh<class_Mesh>` que se dibuja en el índice ``pass``.

.. |virtual| replace:: :abbr:`virtual (This method should typically be overridden by the user to have any effect.)`
.. |const| replace:: :abbr:`const (This method has no side effects. It doesn't modify any of the instance's member variables.)`
.. |vararg| replace:: :abbr:`vararg (This method accepts any number of arguments after the ones described here.)`
