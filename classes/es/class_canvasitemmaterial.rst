:github_url: hide

.. Generated automatically by doc/tools/make_rst.py in Godot's source tree.
.. DO NOT EDIT THIS FILE, but the CanvasItemMaterial.xml source instead.
.. The source is found in doc/classes or modules/<name>/doc_classes.

.. _class_CanvasItemMaterial:

CanvasItemMaterial
==================

**Inherits:** :ref:`Material<class_Material>` **<** :ref:`Resource<class_Resource>` **<** :ref:`Reference<class_Reference>` **<** :ref:`Object<class_Object>`

Un material para :ref:`CanvasItem<class_CanvasItem>`\ s.

Descripción
----------------------

Los ``CanvasItemMaterial``\ s proporcionan un medio de modificar las texturas asociadas a un CanvasItem. Se especializan en describir los comportamientos de mezcla e iluminación de las texturas. Utiliza un :ref:`ShaderMaterial<class_ShaderMaterial>` para personalizar más completamente las interacciones de un material con un :ref:`CanvasItem<class_CanvasItem>`.

Propiedades
----------------------

+-----------------------------------------------------+-------------------------------------------------------------------------------------------+-----------+
| :ref:`BlendMode<enum_CanvasItemMaterial_BlendMode>` | :ref:`blend_mode<class_CanvasItemMaterial_property_blend_mode>`                           | ``0``     |
+-----------------------------------------------------+-------------------------------------------------------------------------------------------+-----------+
| :ref:`LightMode<enum_CanvasItemMaterial_LightMode>` | :ref:`light_mode<class_CanvasItemMaterial_property_light_mode>`                           | ``0``     |
+-----------------------------------------------------+-------------------------------------------------------------------------------------------+-----------+
| :ref:`int<class_int>`                               | :ref:`particles_anim_h_frames<class_CanvasItemMaterial_property_particles_anim_h_frames>` |           |
+-----------------------------------------------------+-------------------------------------------------------------------------------------------+-----------+
| :ref:`bool<class_bool>`                             | :ref:`particles_anim_loop<class_CanvasItemMaterial_property_particles_anim_loop>`         |           |
+-----------------------------------------------------+-------------------------------------------------------------------------------------------+-----------+
| :ref:`int<class_int>`                               | :ref:`particles_anim_v_frames<class_CanvasItemMaterial_property_particles_anim_v_frames>` |           |
+-----------------------------------------------------+-------------------------------------------------------------------------------------------+-----------+
| :ref:`bool<class_bool>`                             | :ref:`particles_animation<class_CanvasItemMaterial_property_particles_animation>`         | ``false`` |
+-----------------------------------------------------+-------------------------------------------------------------------------------------------+-----------+

Enumeraciones
--------------------------

.. _enum_CanvasItemMaterial_BlendMode:

.. _class_CanvasItemMaterial_constant_BLEND_MODE_MIX:

.. _class_CanvasItemMaterial_constant_BLEND_MODE_ADD:

.. _class_CanvasItemMaterial_constant_BLEND_MODE_SUB:

.. _class_CanvasItemMaterial_constant_BLEND_MODE_MUL:

.. _class_CanvasItemMaterial_constant_BLEND_MODE_PREMULT_ALPHA:

enum **BlendMode**:

- **BLEND_MODE_MIX** = **0** --- Modo de mezcla. Se supone que los colores son independientes del valor alfa (opacidad).

- **BLEND_MODE_ADD** = **1** --- Modo de mezcla de añadidos.

- **BLEND_MODE_SUB** = **2** --- Modo de mezcla de substracción.

- **BLEND_MODE_MUL** = **3** --- Modo de mezcla multiplicativo.

- **BLEND_MODE_PREMULT_ALPHA** = **4** --- Modo de mezcla Mix. Se supone que los colores se premultiplican por el valor alfa (opacidad).

----

.. _enum_CanvasItemMaterial_LightMode:

.. _class_CanvasItemMaterial_constant_LIGHT_MODE_NORMAL:

.. _class_CanvasItemMaterial_constant_LIGHT_MODE_UNSHADED:

.. _class_CanvasItemMaterial_constant_LIGHT_MODE_LIGHT_ONLY:

enum **LightMode**:

- **LIGHT_MODE_NORMAL** = **0** --- Renderizar el material utilizando tanto las propiedades de los materiales sensibles a la luz como las que no lo son.

- **LIGHT_MODE_UNSHADED** = **1** --- Renderiza el material como si no hubiera luz.

- **LIGHT_MODE_LIGHT_ONLY** = **2** --- Renderizar el material como si sólo hubiera luz.

Descripciones de Propiedades
--------------------------------------------------------

.. _class_CanvasItemMaterial_property_blend_mode:

- :ref:`BlendMode<enum_CanvasItemMaterial_BlendMode>` **blend_mode**

+-----------+-----------------------+
| *Default* | ``0``                 |
+-----------+-----------------------+
| *Setter*  | set_blend_mode(value) |
+-----------+-----------------------+
| *Getter*  | get_blend_mode()      |
+-----------+-----------------------+

La manera en que la representación de un material se aplica a las texturas inferiores.

----

.. _class_CanvasItemMaterial_property_light_mode:

- :ref:`LightMode<enum_CanvasItemMaterial_LightMode>` **light_mode**

+-----------+-----------------------+
| *Default* | ``0``                 |
+-----------+-----------------------+
| *Setter*  | set_light_mode(value) |
+-----------+-----------------------+
| *Getter*  | get_light_mode()      |
+-----------+-----------------------+

La manera en que el material reacciona a la iluminación.

----

.. _class_CanvasItemMaterial_property_particles_anim_h_frames:

- :ref:`int<class_int>` **particles_anim_h_frames**

+----------+------------------------------------+
| *Setter* | set_particles_anim_h_frames(value) |
+----------+------------------------------------+
| *Getter* | get_particles_anim_h_frames()      |
+----------+------------------------------------+

The number of columns in the spritesheet assigned as :ref:`Texture<class_Texture>` for a :ref:`Particles2D<class_Particles2D>` or :ref:`CPUParticles2D<class_CPUParticles2D>`.

\ **Note:** This property is only used and visible in the editor if :ref:`particles_animation<class_CanvasItemMaterial_property_particles_animation>` is ``true``.

----

.. _class_CanvasItemMaterial_property_particles_anim_loop:

- :ref:`bool<class_bool>` **particles_anim_loop**

+----------+--------------------------------+
| *Setter* | set_particles_anim_loop(value) |
+----------+--------------------------------+
| *Getter* | get_particles_anim_loop()      |
+----------+--------------------------------+

Si ``true``, la animación de las partículas se hará en bucle.

\ **Nota:** Esta propiedad sólo se usa y es visible en el editor si :ref:`particles_animation<class_CanvasItemMaterial_property_particles_animation>` es ``true``.

----

.. _class_CanvasItemMaterial_property_particles_anim_v_frames:

- :ref:`int<class_int>` **particles_anim_v_frames**

+----------+------------------------------------+
| *Setter* | set_particles_anim_v_frames(value) |
+----------+------------------------------------+
| *Getter* | get_particles_anim_v_frames()      |
+----------+------------------------------------+

The number of rows in the spritesheet assigned as :ref:`Texture<class_Texture>` for a :ref:`Particles2D<class_Particles2D>` or :ref:`CPUParticles2D<class_CPUParticles2D>`.

\ **Note:** This property is only used and visible in the editor if :ref:`particles_animation<class_CanvasItemMaterial_property_particles_animation>` is ``true``.

----

.. _class_CanvasItemMaterial_property_particles_animation:

- :ref:`bool<class_bool>` **particles_animation**

+-----------+--------------------------------+
| *Default* | ``false``                      |
+-----------+--------------------------------+
| *Setter*  | set_particles_animation(value) |
+-----------+--------------------------------+
| *Getter*  | get_particles_animation()      |
+-----------+--------------------------------+

If ``true``, enable spritesheet-based animation features when assigned to :ref:`Particles2D<class_Particles2D>` and :ref:`CPUParticles2D<class_CPUParticles2D>` nodes. The :ref:`ParticlesMaterial.anim_speed<class_ParticlesMaterial_property_anim_speed>` or :ref:`CPUParticles2D.anim_speed<class_CPUParticles2D_property_anim_speed>` should also be set to a positive value for the animation to play.

This property (and other ``particles_anim_*`` properties that depend on it) has no effect on other types of nodes.

.. |virtual| replace:: :abbr:`virtual (This method should typically be overridden by the user to have any effect.)`
.. |const| replace:: :abbr:`const (This method has no side effects. It doesn't modify any of the instance's member variables.)`
.. |vararg| replace:: :abbr:`vararg (This method accepts any number of arguments after the ones described here.)`
