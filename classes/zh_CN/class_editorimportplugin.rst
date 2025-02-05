:github_url: hide

.. Generated automatically by doc/tools/make_rst.py in Godot's source tree.
.. DO NOT EDIT THIS FILE, but the EditorImportPlugin.xml source instead.
.. The source is found in doc/classes or modules/<name>/doc_classes.

.. _class_EditorImportPlugin:

EditorImportPlugin
==================

**Inherits:** :ref:`ResourceImporter<class_ResourceImporter>` **<** :ref:`Reference<class_Reference>` **<** :ref:`Object<class_Object>`

在编辑器中注册一个自定义资源导入器。使用该类来解析任何文件，并将其作为新的资源类型导入。

描述
----

EditorImportPlugins提供了一种扩展编辑器资源导入功能的方法。使用它们来导入自定义文件中的资源，或成为编辑器现有导入器的替代品。用\ :ref:`EditorPlugin.add_import_plugin<class_EditorPlugin_method_add_import_plugin>`\ 注册你的\ :ref:`EditorPlugin<class_EditorPlugin>`\ 。

EditorImportPlugins通过与特定的文件扩展名和资源类型相关联来工作。参阅 :ref:`get_recognized_extensions<class_EditorImportPlugin_method_get_recognized_extensions>` 和 :ref:`get_resource_type<class_EditorImportPlugin_method_get_resource_type>`\ 。其可以选择性地指定一些影响导入过程的导入预置。EditorImportPlugins负责创建资源并将其保存在\ ``.import``\ 目录中，参阅\ :ref:`ProjectSettings.application/config/use_hidden_project_data_directory<class_ProjectSettings_property_application/config/use_hidden_project_data_directory>`\ 。

下面是一个EditorImportPlugin的例子，它从扩展名为 ".special" 或 ".spec" 的文件中导入一个\ :ref:`Mesh<class_Mesh>`:

::

    tool
    extends EditorImportPlugin
    
    func get_importer_name():
        return "my.special.plugin"
    
    func get_visible_name():
        return "Special Mesh"
    
    func get_recognized_extensions():
        return ["special", "spec"]
    
    func get_save_extension():
        return "mesh"
    
    func get_resource_type():
        return "Mesh"
    
    func get_preset_count():
        return 1
    
    func get_preset_name(i):
        return "Default"
    
    func get_import_options(i):
        return [{"name": "my_option", "default_value": false}]
    
    func import(source_file, save_path, options, platform_variants, gen_files):
        var file = File.new()
        if file.open(source_file, File.READ) != OK:
            return FAILED
    
        var mesh = Mesh.new()
        # Fill the Mesh with data read in "file", left as an exercise to the reader
    
        var filename = save_path + "." + get_save_extension()
        return ResourceSaver.save(filename, mesh)

教程
----

- :doc:`../tutorials/plugins/editor/import_plugins`

方法
----

+-----------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`Array<class_Array>`   | :ref:`get_import_options<class_EditorImportPlugin_method_get_import_options>` **(** :ref:`int<class_int>` preset **)** |virtual|                                                                                                                                                          |
+-----------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`int<class_int>`       | :ref:`get_import_order<class_EditorImportPlugin_method_get_import_order>` **(** **)** |virtual|                                                                                                                                                                                           |
+-----------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`String<class_String>` | :ref:`get_importer_name<class_EditorImportPlugin_method_get_importer_name>` **(** **)** |virtual|                                                                                                                                                                                         |
+-----------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`bool<class_bool>`     | :ref:`get_option_visibility<class_EditorImportPlugin_method_get_option_visibility>` **(** :ref:`String<class_String>` option, :ref:`Dictionary<class_Dictionary>` options **)** |virtual|                                                                                                 |
+-----------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`int<class_int>`       | :ref:`get_preset_count<class_EditorImportPlugin_method_get_preset_count>` **(** **)** |virtual|                                                                                                                                                                                           |
+-----------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`String<class_String>` | :ref:`get_preset_name<class_EditorImportPlugin_method_get_preset_name>` **(** :ref:`int<class_int>` preset **)** |virtual|                                                                                                                                                                |
+-----------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`float<class_float>`   | :ref:`get_priority<class_EditorImportPlugin_method_get_priority>` **(** **)** |virtual|                                                                                                                                                                                                   |
+-----------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`Array<class_Array>`   | :ref:`get_recognized_extensions<class_EditorImportPlugin_method_get_recognized_extensions>` **(** **)** |virtual|                                                                                                                                                                         |
+-----------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`String<class_String>` | :ref:`get_resource_type<class_EditorImportPlugin_method_get_resource_type>` **(** **)** |virtual|                                                                                                                                                                                         |
+-----------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`String<class_String>` | :ref:`get_save_extension<class_EditorImportPlugin_method_get_save_extension>` **(** **)** |virtual|                                                                                                                                                                                       |
+-----------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`String<class_String>` | :ref:`get_visible_name<class_EditorImportPlugin_method_get_visible_name>` **(** **)** |virtual|                                                                                                                                                                                           |
+-----------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`int<class_int>`       | :ref:`import<class_EditorImportPlugin_method_import>` **(** :ref:`String<class_String>` source_file, :ref:`String<class_String>` save_path, :ref:`Dictionary<class_Dictionary>` options, :ref:`Array<class_Array>` platform_variants, :ref:`Array<class_Array>` gen_files **)** |virtual| |
+-----------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

方法说明
--------

.. _class_EditorImportPlugin_method_get_import_options:

- :ref:`Array<class_Array>` **get_import_options** **(** :ref:`int<class_int>` preset **)** |virtual|

获取该索引下预设的选项和默认值。返回一个字典数组，包含以下键名：\ ``name``\ 、\ ``default_value``\ 、\ ``property_hint``\ （可选）、\ ``hint_string``\ （可选）、\ ``usage``\ （可选）。

----

.. _class_EditorImportPlugin_method_get_import_order:

- :ref:`int<class_int>` **get_import_order** **(** **)** |virtual|

获取该导入器在导入资源时的运行顺序。具有\ *较低*\ 导入顺序的导入器将被首先调用，较高值的将被其后调用。使用这个来确保导入器在依赖项已经被导入后执行。默认的导入顺序是 ``0``\ ，除非被指定的导入器重写。参阅 :ref:`ImportOrder<enum_ResourceImporter_ImportOrder>` 了解相关预定义的值。

----

.. _class_EditorImportPlugin_method_get_importer_name:

- :ref:`String<class_String>` **get_importer_name** **(** **)** |virtual|

获取导入者的唯一名称。

----

.. _class_EditorImportPlugin_method_get_option_visibility:

- :ref:`bool<class_bool>` **get_option_visibility** **(** :ref:`String<class_String>` option, :ref:`Dictionary<class_Dictionary>` options **)** |virtual|

这个方法可以在满足条件的情况下重写隐藏特定的导入选项。这主要适用于隐藏依赖于其他选项的选项，如果其中一个选项被禁用。例如：

::

    func get_option_visibility(option, options):
        # Only show the lossy quality setting if the compression mode is set to "Lossy".
        if option == "compress/lossy_quality" and options.has("compress/mode"):
            return int(options["compress/mode"]) == COMPRESS_LOSSY
    
        return true

返回\ ``true``\ ，使所有选项始终可见。

----

.. _class_EditorImportPlugin_method_get_preset_count:

- :ref:`int<class_int>` **get_preset_count** **(** **)** |virtual|

获取插件定义的初始预置数量。使用\ :ref:`get_import_options<class_EditorImportPlugin_method_get_import_options>`\ 获取预设的默认选项，使用\ :ref:`get_preset_name<class_EditorImportPlugin_method_get_preset_name>`\ 获取预设的名称。

----

.. _class_EditorImportPlugin_method_get_preset_name:

- :ref:`String<class_String>` **get_preset_name** **(** :ref:`int<class_int>` preset **)** |virtual|

获取该索引处预设的选项名称。

----

.. _class_EditorImportPlugin_method_get_priority:

- :ref:`float<class_float>` **get_priority** **(** **)** |virtual|

获取该插件对识别的扩展的优先级。优先级越高的插件会被优先选择。默认的优先级是\ ``1.0``\ 。

----

.. _class_EditorImportPlugin_method_get_recognized_extensions:

- :ref:`Array<class_Array>` **get_recognized_extensions** **(** **)** |virtual|

获取与该加载器相关联的文件扩展名列表（不区分大小写），例如 ``["obj"]``\ 。

----

.. _class_EditorImportPlugin_method_get_resource_type:

- :ref:`String<class_String>` **get_resource_type** **(** **)** |virtual|

获取与此加载程序关联的Godot资源类型，例如 ``"Mesh"`` 或 ``"Animation"``\ 。

----

.. _class_EditorImportPlugin_method_get_save_extension:

- :ref:`String<class_String>` **get_save_extension** **(** **)** |virtual|

获取用于在\ ``.import``\ 目录中保存此资源的扩展名，参阅\ :ref:`ProjectSettings.application/config/use_hidden_project_data_directory<class_ProjectSettings_property_application/config/use_hidden_project_data_directory>`\ 。

----

.. _class_EditorImportPlugin_method_get_visible_name:

- :ref:`String<class_String>` **get_visible_name** **(** **)** |virtual|

获取在导入窗口中显示的名称。你应该选择这个名字作为 "Import as" 的延续，例如 "Import as Special Mesh"。

----

.. _class_EditorImportPlugin_method_import:

- :ref:`int<class_int>` **import** **(** :ref:`String<class_String>` source_file, :ref:`String<class_String>` save_path, :ref:`Dictionary<class_Dictionary>` options, :ref:`Array<class_Array>` platform_variants, :ref:`Array<class_Array>` gen_files **)** |virtual|

使用指定的导入选项 ``options`` 将 ``source_file`` 导入到 ``save_path`` 中。\ ``platform_variants`` 和 ``gen_files`` 数组将被此函数修改。

这个方法必须被重写才能完成实际的导入工作。参阅本类的描述以了解如何重写该方法。

.. |virtual| replace:: :abbr:`virtual (This method should typically be overridden by the user to have any effect.)`
.. |const| replace:: :abbr:`const (This method has no side effects. It doesn't modify any of the instance's member variables.)`
.. |vararg| replace:: :abbr:`vararg (This method accepts any number of arguments after the ones described here.)`
