:github_url: hide

.. Generated automatically by doc/tools/make_rst.py in Godot's source tree.
.. DO NOT EDIT THIS FILE, but the Label.xml source instead.
.. The source is found in doc/classes or modules/<name>/doc_classes.

.. _class_Label:

Label
=====

**Inherits:** :ref:`Control<class_Control>` **<** :ref:`CanvasItem<class_CanvasItem>` **<** :ref:`Node<class_Node>` **<** :ref:`Object<class_Object>`

在一行中显示纯文本，或在一个矩形内包裹。对于格式化的文本，使用\ :ref:`RichTextLabel<class_RichTextLabel>`\ 。

描述
----

标签在屏幕上显示纯文本。可以控制水平和垂直的对齐方式，并且可以将文本包裹在节点的边界矩形内。它不支持粗体、斜体或其他格式。若使用，请改用 :ref:`RichTextLabel<class_RichTextLabel>`\ 。

\ **注意：** 与大多数其他 :ref:`Control<class_Control>` 不同，Label 的 :ref:`Control.mouse_filter<class_Control_property_mouse_filter>` 默认为 :ref:`Control.MOUSE_FILTER_IGNORE<class_Control_constant_MOUSE_FILTER_IGNORE>`\ ，即它不响应鼠标输入事件。这意味着标签不会显示任何已配置的 :ref:`Control.hint_tooltip<class_Control_property_hint_tooltip>`\ ，除非更改其鼠标过滤器。

\ **注意：**\ Windows 上\ *不支持* ``0xffff`` 之后的 Unicode 字符，例如大多数表情符号，它们将显示为未知字符。这将在 Godot 4.0 中解决。

教程
----

- `2D Dodge The Creeps Demo <https://godotengine.org/asset-library/asset/515>`__

属性
----

+----------------------------------------------+--------------------------------------------------------------------+------------------------------------------------------------------------------+
| :ref:`Align<enum_Label_Align>`               | :ref:`align<class_Label_property_align>`                           | ``0``                                                                        |
+----------------------------------------------+--------------------------------------------------------------------+------------------------------------------------------------------------------+
| :ref:`bool<class_bool>`                      | :ref:`autowrap<class_Label_property_autowrap>`                     | ``false``                                                                    |
+----------------------------------------------+--------------------------------------------------------------------+------------------------------------------------------------------------------+
| :ref:`bool<class_bool>`                      | :ref:`clip_text<class_Label_property_clip_text>`                   | ``false``                                                                    |
+----------------------------------------------+--------------------------------------------------------------------+------------------------------------------------------------------------------+
| :ref:`int<class_int>`                        | :ref:`lines_skipped<class_Label_property_lines_skipped>`           | ``0``                                                                        |
+----------------------------------------------+--------------------------------------------------------------------+------------------------------------------------------------------------------+
| :ref:`int<class_int>`                        | :ref:`max_lines_visible<class_Label_property_max_lines_visible>`   | ``-1``                                                                       |
+----------------------------------------------+--------------------------------------------------------------------+------------------------------------------------------------------------------+
| :ref:`MouseFilter<enum_Control_MouseFilter>` | mouse_filter                                                       | ``2`` (overrides :ref:`Control<class_Control_property_mouse_filter>`)        |
+----------------------------------------------+--------------------------------------------------------------------+------------------------------------------------------------------------------+
| :ref:`float<class_float>`                    | :ref:`percent_visible<class_Label_property_percent_visible>`       | ``1.0``                                                                      |
+----------------------------------------------+--------------------------------------------------------------------+------------------------------------------------------------------------------+
| :ref:`int<class_int>`                        | size_flags_vertical                                                | ``4`` (overrides :ref:`Control<class_Control_property_size_flags_vertical>`) |
+----------------------------------------------+--------------------------------------------------------------------+------------------------------------------------------------------------------+
| :ref:`String<class_String>`                  | :ref:`text<class_Label_property_text>`                             | ``""``                                                                       |
+----------------------------------------------+--------------------------------------------------------------------+------------------------------------------------------------------------------+
| :ref:`bool<class_bool>`                      | :ref:`uppercase<class_Label_property_uppercase>`                   | ``false``                                                                    |
+----------------------------------------------+--------------------------------------------------------------------+------------------------------------------------------------------------------+
| :ref:`VAlign<enum_Label_VAlign>`             | :ref:`valign<class_Label_property_valign>`                         | ``0``                                                                        |
+----------------------------------------------+--------------------------------------------------------------------+------------------------------------------------------------------------------+
| :ref:`int<class_int>`                        | :ref:`visible_characters<class_Label_property_visible_characters>` | ``-1``                                                                       |
+----------------------------------------------+--------------------------------------------------------------------+------------------------------------------------------------------------------+

方法
----

+-----------------------+----------------------------------------------------------------------------------------------------+
| :ref:`int<class_int>` | :ref:`get_line_count<class_Label_method_get_line_count>` **(** **)** |const|                       |
+-----------------------+----------------------------------------------------------------------------------------------------+
| :ref:`int<class_int>` | :ref:`get_line_height<class_Label_method_get_line_height>` **(** **)** |const|                     |
+-----------------------+----------------------------------------------------------------------------------------------------+
| :ref:`int<class_int>` | :ref:`get_total_character_count<class_Label_method_get_total_character_count>` **(** **)** |const| |
+-----------------------+----------------------------------------------------------------------------------------------------+
| :ref:`int<class_int>` | :ref:`get_visible_line_count<class_Label_method_get_visible_line_count>` **(** **)** |const|       |
+-----------------------+----------------------------------------------------------------------------------------------------+

主题属性
--------

+---------------------------------+-----------------------------------------------------------------------------+-------------------------+
| :ref:`Color<class_Color>`       | :ref:`font_color<class_Label_theme_color_font_color>`                       | ``Color( 1, 1, 1, 1 )`` |
+---------------------------------+-----------------------------------------------------------------------------+-------------------------+
| :ref:`Color<class_Color>`       | :ref:`font_color_shadow<class_Label_theme_color_font_color_shadow>`         | ``Color( 0, 0, 0, 0 )`` |
+---------------------------------+-----------------------------------------------------------------------------+-------------------------+
| :ref:`Color<class_Color>`       | :ref:`font_outline_modulate<class_Label_theme_color_font_outline_modulate>` | ``Color( 1, 1, 1, 1 )`` |
+---------------------------------+-----------------------------------------------------------------------------+-------------------------+
| :ref:`int<class_int>`           | :ref:`line_spacing<class_Label_theme_constant_line_spacing>`                | ``3``                   |
+---------------------------------+-----------------------------------------------------------------------------+-------------------------+
| :ref:`int<class_int>`           | :ref:`shadow_as_outline<class_Label_theme_constant_shadow_as_outline>`      | ``0``                   |
+---------------------------------+-----------------------------------------------------------------------------+-------------------------+
| :ref:`int<class_int>`           | :ref:`shadow_offset_x<class_Label_theme_constant_shadow_offset_x>`          | ``1``                   |
+---------------------------------+-----------------------------------------------------------------------------+-------------------------+
| :ref:`int<class_int>`           | :ref:`shadow_offset_y<class_Label_theme_constant_shadow_offset_y>`          | ``1``                   |
+---------------------------------+-----------------------------------------------------------------------------+-------------------------+
| :ref:`Font<class_Font>`         | :ref:`font<class_Label_theme_font_font>`                                    |                         |
+---------------------------------+-----------------------------------------------------------------------------+-------------------------+
| :ref:`StyleBox<class_StyleBox>` | :ref:`normal<class_Label_theme_style_normal>`                               |                         |
+---------------------------------+-----------------------------------------------------------------------------+-------------------------+

枚举
----

.. _enum_Label_Align:

.. _class_Label_constant_ALIGN_LEFT:

.. _class_Label_constant_ALIGN_CENTER:

.. _class_Label_constant_ALIGN_RIGHT:

.. _class_Label_constant_ALIGN_FILL:

enum **Align**:

- **ALIGN_LEFT** = **0** --- 将行左对齐，默认。

- **ALIGN_CENTER** = **1** --- 居中对齐行。

- **ALIGN_RIGHT** = **2** --- 将行向右对齐。

- **ALIGN_FILL** = **3** --- 扩展行空白以适应宽度。

----

.. _enum_Label_VAlign:

.. _class_Label_constant_VALIGN_TOP:

.. _class_Label_constant_VALIGN_CENTER:

.. _class_Label_constant_VALIGN_BOTTOM:

.. _class_Label_constant_VALIGN_FILL:

enum **VAlign**:

- **VALIGN_TOP** = **0** --- 将整个文本对齐到顶部。

- **VALIGN_CENTER** = **1** --- 将整个文本居中对齐。

- **VALIGN_BOTTOM** = **2** --- 将整个文本与底部对齐。

- **VALIGN_FILL** = **3** --- 通过展开行来对齐整个文本。

属性说明
--------

.. _class_Label_property_align:

- :ref:`Align<enum_Label_Align>` **align**

+-----------+------------------+
| *Default* | ``0``            |
+-----------+------------------+
| *Setter*  | set_align(value) |
+-----------+------------------+
| *Getter*  | get_align()      |
+-----------+------------------+

控制文本的水平对齐。支持左对齐、居中对齐、右对齐和填充，或者两端对齐。把它设置为\ :ref:`Align<enum_Label_Align>`\ 常量之一。

----

.. _class_Label_property_autowrap:

- :ref:`bool<class_bool>` **autowrap**

+-----------+---------------------+
| *Default* | ``false``           |
+-----------+---------------------+
| *Setter*  | set_autowrap(value) |
+-----------+---------------------+
| *Getter*  | has_autowrap()      |
+-----------+---------------------+

如果\ ``true``\ ，则将文本包裹在节点的边界矩形内。如果你调整节点的大小，它将自动改变其高度以显示所有的文本。

----

.. _class_Label_property_clip_text:

- :ref:`bool<class_bool>` **clip_text**

+-----------+----------------------+
| *Default* | ``false``            |
+-----------+----------------------+
| *Setter*  | set_clip_text(value) |
+-----------+----------------------+
| *Getter*  | is_clipping_text()   |
+-----------+----------------------+

如果 ``true``\ ，则标签仅显示适合其边界矩形的文本，并将水平剪切文本。

----

.. _class_Label_property_lines_skipped:

- :ref:`int<class_int>` **lines_skipped**

+-----------+--------------------------+
| *Default* | ``0``                    |
+-----------+--------------------------+
| *Setter*  | set_lines_skipped(value) |
+-----------+--------------------------+
| *Getter*  | get_lines_skipped()      |
+-----------+--------------------------+

该节点在开始显示文本之前会忽略前 ``lines_skipped`` 行。

----

.. _class_Label_property_max_lines_visible:

- :ref:`int<class_int>` **max_lines_visible**

+-----------+------------------------------+
| *Default* | ``-1``                       |
+-----------+------------------------------+
| *Setter*  | set_max_lines_visible(value) |
+-----------+------------------------------+
| *Getter*  | get_max_lines_visible()      |
+-----------+------------------------------+

限制节点在屏幕上显示的文本行数。

----

.. _class_Label_property_percent_visible:

- :ref:`float<class_float>` **percent_visible**

+-----------+----------------------------+
| *Default* | ``1.0``                    |
+-----------+----------------------------+
| *Setter*  | set_percent_visible(value) |
+-----------+----------------------------+
| *Getter*  | get_percent_visible()      |
+-----------+----------------------------+

限制可见字符的数量。如果你把\ ``%_visible``\ 设置为0.5，屏幕上最多只能显示文本的一半字符。这在对话框中对文本进行动画处理很有用。

----

.. _class_Label_property_text:

- :ref:`String<class_String>` **text**

+-----------+-----------------+
| *Default* | ``""``          |
+-----------+-----------------+
| *Setter*  | set_text(value) |
+-----------+-----------------+
| *Getter*  | get_text()      |
+-----------+-----------------+

要在屏幕上显示的文本。

----

.. _class_Label_property_uppercase:

- :ref:`bool<class_bool>` **uppercase**

+-----------+----------------------+
| *Default* | ``false``            |
+-----------+----------------------+
| *Setter*  | set_uppercase(value) |
+-----------+----------------------+
| *Getter*  | is_uppercase()       |
+-----------+----------------------+

如果 ``true``\ ，则所有文本都显示为大写。

----

.. _class_Label_property_valign:

- :ref:`VAlign<enum_Label_VAlign>` **valign**

+-----------+-------------------+
| *Default* | ``0``             |
+-----------+-------------------+
| *Setter*  | set_valign(value) |
+-----------+-------------------+
| *Getter*  | get_valign()      |
+-----------+-------------------+

控制文本的垂直对齐。支持顶部、中心、底部和填充。参阅\ :ref:`VAlign<enum_Label_VAlign>`\ 常数。

----

.. _class_Label_property_visible_characters:

- :ref:`int<class_int>` **visible_characters**

+-----------+-------------------------------+
| *Default* | ``-1``                        |
+-----------+-------------------------------+
| *Setter*  | set_visible_characters(value) |
+-----------+-------------------------------+
| *Getter*  | get_visible_characters()      |
+-----------+-------------------------------+

限制显示的字符数。设置为-1表示禁用限制。

方法说明
--------

.. _class_Label_method_get_line_count:

- :ref:`int<class_int>` **get_line_count** **(** **)** |const|

返回Label标签的文本行数。

----

.. _class_Label_method_get_line_height:

- :ref:`int<class_int>` **get_line_height** **(** **)** |const|

返回字体大小，单位是像素。

----

.. _class_Label_method_get_total_character_count:

- :ref:`int<class_int>` **get_total_character_count** **(** **)** |const|

返回文本中可打印的字符总数，不包括空格和换行符。

----

.. _class_Label_method_get_visible_line_count:

- :ref:`int<class_int>` **get_visible_line_count** **(** **)** |const|

返回显示的行数。如果\ ``Label``\ 的高度目前无法显示所有的行数，将会有用。

Theme Property Descriptions
---------------------------

.. _class_Label_theme_color_font_color:

- :ref:`Color<class_Color>` **font_color**

+-----------+-------------------------+
| *Default* | ``Color( 1, 1, 1, 1 )`` |
+-----------+-------------------------+

``Label``\ 标签的默认文本颜色\ :ref:`Color<class_Color>`\ 。

----

.. _class_Label_theme_color_font_color_shadow:

- :ref:`Color<class_Color>` **font_color_shadow**

+-----------+-------------------------+
| *Default* | ``Color( 0, 0, 0, 0 )`` |
+-----------+-------------------------+

文本阴影效果的颜色\ :ref:`Color<class_Color>`\ 。

----

.. _class_Label_theme_color_font_outline_modulate:

- :ref:`Color<class_Color>` **font_outline_modulate**

+-----------+-------------------------+
| *Default* | ``Color( 1, 1, 1, 1 )`` |
+-----------+-------------------------+

:ref:`Font<class_Font>`\ 轮廓的色调。参阅\ :ref:`DynamicFont.outline_color<class_DynamicFont_property_outline_color>`\ 。

----

.. _class_Label_theme_constant_line_spacing:

- :ref:`int<class_int>` **line_spacing**

+-----------+-------+
| *Default* | ``3`` |
+-----------+-------+

多行\ ``Label``\ 中各行之间的垂直空间。

----

.. _class_Label_theme_constant_shadow_as_outline:

- :ref:`int<class_int>` **shadow_as_outline**

+-----------+-------+
| *Default* | ``0`` |
+-----------+-------+

布尔值。如果设置为1，即\ ``true``\ ，整个文本周围显示阴影轮廓。

----

.. _class_Label_theme_constant_shadow_offset_x:

- :ref:`int<class_int>` **shadow_offset_x**

+-----------+-------+
| *Default* | ``1`` |
+-----------+-------+

文本阴影的水平偏移。

----

.. _class_Label_theme_constant_shadow_offset_y:

- :ref:`int<class_int>` **shadow_offset_y**

+-----------+-------+
| *Default* | ``1`` |
+-----------+-------+

文本阴影的垂直偏移。

----

.. _class_Label_theme_font_font:

- :ref:`Font<class_Font>` **font**

用于标签\ ``Label``\ 文本的字体\ :ref:`Font<class_Font>`\ 。

----

.. _class_Label_theme_style_normal:

- :ref:`StyleBox<class_StyleBox>` **normal**

为\ ``Label``\ 设置背景样式\ :ref:`StyleBox<class_StyleBox>`\ 。

.. |virtual| replace:: :abbr:`virtual (This method should typically be overridden by the user to have any effect.)`
.. |const| replace:: :abbr:`const (This method has no side effects. It doesn't modify any of the instance's member variables.)`
.. |vararg| replace:: :abbr:`vararg (This method accepts any number of arguments after the ones described here.)`
