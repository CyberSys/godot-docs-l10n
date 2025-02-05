:github_url: hide

.. Generated automatically by doc/tools/make_rst.py in Godot's source tree.
.. DO NOT EDIT THIS FILE, but the Directory.xml source instead.
.. The source is found in doc/classes or modules/<name>/doc_classes.

.. _class_Directory:

Directory
=========

**Inherits:** :ref:`Reference<class_Reference>` **<** :ref:`Object<class_Object>`

Tipo utilizado para manejar el sistema de archivos.

Descripción
----------------------

Directory type. It is used to manage directories and their content (not restricted to the project folder).

When creating a new ``Directory``, its default opened directory will be ``res://``. This may change in the future, so it is advised to always use :ref:`open<class_Directory_method_open>` to initialize your ``Directory`` where you want to operate, with explicit error checking.

\ **Note:** Many resources types are imported (e.g. textures or sound files), and their source asset will not be included in the exported game, as only the imported version is used. Use :ref:`ResourceLoader<class_ResourceLoader>` to access imported resources.

Here is an example on how to iterate through the files of a directory:

::

    func dir_contents(path):
        var dir = Directory.new()
        if dir.open(path) == OK:
            dir.list_dir_begin()
            var file_name = dir.get_next()
            while file_name != "":
                if dir.current_is_dir():
                    print("Found directory: " + file_name)
                else:
                    print("Found file: " + file_name)
                file_name = dir.get_next()
        else:
            print("An error occurred when trying to access the path.")

Tutoriales
--------------------

- :doc:`../tutorials/scripting/filesystem`

Métodos
--------------

+---------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`Error<enum_@GlobalScope_Error>` | :ref:`change_dir<class_Directory_method_change_dir>` **(** :ref:`String<class_String>` todir **)**                                                                  |
+---------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`Error<enum_@GlobalScope_Error>` | :ref:`copy<class_Directory_method_copy>` **(** :ref:`String<class_String>` from, :ref:`String<class_String>` to **)**                                               |
+---------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`bool<class_bool>`               | :ref:`current_is_dir<class_Directory_method_current_is_dir>` **(** **)** |const|                                                                                    |
+---------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`bool<class_bool>`               | :ref:`dir_exists<class_Directory_method_dir_exists>` **(** :ref:`String<class_String>` path **)**                                                                   |
+---------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`bool<class_bool>`               | :ref:`file_exists<class_Directory_method_file_exists>` **(** :ref:`String<class_String>` path **)**                                                                 |
+---------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`String<class_String>`           | :ref:`get_current_dir<class_Directory_method_get_current_dir>` **(** **)**                                                                                          |
+---------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`int<class_int>`                 | :ref:`get_current_drive<class_Directory_method_get_current_drive>` **(** **)**                                                                                      |
+---------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`String<class_String>`           | :ref:`get_drive<class_Directory_method_get_drive>` **(** :ref:`int<class_int>` idx **)**                                                                            |
+---------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`int<class_int>`                 | :ref:`get_drive_count<class_Directory_method_get_drive_count>` **(** **)**                                                                                          |
+---------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`String<class_String>`           | :ref:`get_next<class_Directory_method_get_next>` **(** **)**                                                                                                        |
+---------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`int<class_int>`                 | :ref:`get_space_left<class_Directory_method_get_space_left>` **(** **)**                                                                                            |
+---------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`Error<enum_@GlobalScope_Error>` | :ref:`list_dir_begin<class_Directory_method_list_dir_begin>` **(** :ref:`bool<class_bool>` skip_navigational=false, :ref:`bool<class_bool>` skip_hidden=false **)** |
+---------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                  | :ref:`list_dir_end<class_Directory_method_list_dir_end>` **(** **)**                                                                                                |
+---------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`Error<enum_@GlobalScope_Error>` | :ref:`make_dir<class_Directory_method_make_dir>` **(** :ref:`String<class_String>` path **)**                                                                       |
+---------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`Error<enum_@GlobalScope_Error>` | :ref:`make_dir_recursive<class_Directory_method_make_dir_recursive>` **(** :ref:`String<class_String>` path **)**                                                   |
+---------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`Error<enum_@GlobalScope_Error>` | :ref:`open<class_Directory_method_open>` **(** :ref:`String<class_String>` path **)**                                                                               |
+---------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`Error<enum_@GlobalScope_Error>` | :ref:`remove<class_Directory_method_remove>` **(** :ref:`String<class_String>` path **)**                                                                           |
+---------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`Error<enum_@GlobalScope_Error>` | :ref:`rename<class_Directory_method_rename>` **(** :ref:`String<class_String>` from, :ref:`String<class_String>` to **)**                                           |
+---------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Descripciones de Métodos
------------------------------------------------

.. _class_Directory_method_change_dir:

- :ref:`Error<enum_@GlobalScope_Error>` **change_dir** **(** :ref:`String<class_String>` todir **)**

Cambia el directorio actualmente abierto por el que se pasa como argumento. El argumento puede ser una ruta relativa al directorio actual (por ejemplo, ``newdir`` o ``../newdir``), o una ruta absoluta (por ejemplo, ``/tmp/newdir`` o ``res://somedir/newdir``).

Devuelve una de las constantes del código :ref:`Error<enum_@GlobalScope_Error>` o si tiene éxito ``OK``.

----

.. _class_Directory_method_copy:

- :ref:`Error<enum_@GlobalScope_Error>` **copy** **(** :ref:`String<class_String>` from, :ref:`String<class_String>` to **)**

Copia el archivo ``from`` al destino ``to``. Ambos argumentos deben ser rutas de acceso a los archivos, ya sea relativas o absolutas. Si el archivo de destino existe y no está protegido contra el acceso, será sobrescrito.

Devuelve una de las constantes del código :ref:`Error<enum_@GlobalScope_Error>` o en caso de éxito ``OK``.

----

.. _class_Directory_method_current_is_dir:

- :ref:`bool<class_bool>` **current_is_dir** **(** **)** |const|

Devuelve si el objeto actual procesado con la última llamada a :ref:`get_next<class_Directory_method_get_next>` es un directorio. ``.`` y ``..`` son considerados directorios.

----

.. _class_Directory_method_dir_exists:

- :ref:`bool<class_bool>` **dir_exists** **(** :ref:`String<class_String>` path **)**

Returns whether the target directory exists. The argument can be relative to the current directory, or an absolute path.

----

.. _class_Directory_method_file_exists:

- :ref:`bool<class_bool>` **file_exists** **(** :ref:`String<class_String>` path **)**

Returns whether the target file exists. The argument can be relative to the current directory, or an absolute path.

----

.. _class_Directory_method_get_current_dir:

- :ref:`String<class_String>` **get_current_dir** **(** **)**

Returns the absolute path to the currently opened directory (e.g. ``res://folder`` or ``C:\tmp\folder``).

----

.. _class_Directory_method_get_current_drive:

- :ref:`int<class_int>` **get_current_drive** **(** **)**

Devuelve el índice de la unidad de disco del directorio abierto actualmente. Vea :ref:`get_drive<class_Directory_method_get_drive>` para convertir el índice devuelto al nombre de la unidad.

----

.. _class_Directory_method_get_drive:

- :ref:`String<class_String>` **get_drive** **(** :ref:`int<class_int>` idx **)**

On Windows, returns the name of the drive (partition) passed as an argument (e.g. ``C:``).

On macOS, returns the path to the mounted volume passed as an argument.

On Linux, returns the path to the mounted volume or GTK 3 bookmark passed as an argument.

On other platforms, or if the requested drive does not exist, the method returns an empty String.

----

.. _class_Directory_method_get_drive_count:

- :ref:`int<class_int>` **get_drive_count** **(** **)**

On Windows, returns the number of drives (partitions) mounted on the current filesystem.

On macOS, returns the number of mounted volumes.

On Linux, returns the number of mounted volumes and GTK 3 bookmarks.

On other platforms, the method returns 0.

----

.. _class_Directory_method_get_next:

- :ref:`String<class_String>` **get_next** **(** **)**

Devuelve el siguiente elemento (archivo o directorio) en el directorio actual (incluyendo ``.`` y ``..``, a menos que ``skip_navigational`` haya sido dado a :ref:`list_dir_begin<class_Directory_method_list_dir_begin>`).

Se devuelve el nombre del archivo o directorio (y no su ruta completa). Una vez que la secuencia se ha procesado completamente, el método devuelve una cadena vacía y cierra la secuencia automáticamente (es decir, :ref:`list_dir_end<class_Directory_method_list_dir_end>` no sería obligatorio en tal caso).

----

.. _class_Directory_method_get_space_left:

- :ref:`int<class_int>` **get_space_left** **(** **)**

En los sistemas de escritorio UNIX, devuelve el espacio disponible en el disco del directorio actual. En otras plataformas, esta información no está disponible y el método devuelve 0 o -1.

----

.. _class_Directory_method_list_dir_begin:

- :ref:`Error<enum_@GlobalScope_Error>` **list_dir_begin** **(** :ref:`bool<class_bool>` skip_navigational=false, :ref:`bool<class_bool>` skip_hidden=false **)**

Initializes the stream used to list all files and directories using the :ref:`get_next<class_Directory_method_get_next>` function, closing the currently opened stream if needed. Once the stream has been processed, it should typically be closed with :ref:`list_dir_end<class_Directory_method_list_dir_end>`.

If ``skip_navigational`` is ``true``, ``.`` and ``..`` are filtered out.

If ``skip_hidden`` is ``true``, hidden files are filtered out.

----

.. _class_Directory_method_list_dir_end:

- void **list_dir_end** **(** **)**

Closes the current stream opened with :ref:`list_dir_begin<class_Directory_method_list_dir_begin>` (whether it has been fully processed with :ref:`get_next<class_Directory_method_get_next>` does not matter).

----

.. _class_Directory_method_make_dir:

- :ref:`Error<enum_@GlobalScope_Error>` **make_dir** **(** :ref:`String<class_String>` path **)**

Crea un directorio. El argumento puede ser relativo al directorio actual, o una ruta absoluta. El directorio de destino debe colocarse en un directorio ya existente (para crear la ruta completa de forma recursiva, véase :ref:`make_dir_recursive<class_Directory_method_make_dir_recursive>`).

Devuelve una de las constantes de código de :ref:`Error<enum_@GlobalScope_Error>` (``OK`` en el éxito).

----

.. _class_Directory_method_make_dir_recursive:

- :ref:`Error<enum_@GlobalScope_Error>` **make_dir_recursive** **(** :ref:`String<class_String>` path **)**

Crea un directorio de destino y todos los directorios intermedios necesarios en su camino, llamando a :ref:`make_dir<class_Directory_method_make_dir>` recursivamente. El argumento puede ser relativo al directorio actual, o un camino absoluto.

Devuelve una de las constantes de código de :ref:`Error<enum_@GlobalScope_Error>` (``OK`` en el éxito).

----

.. _class_Directory_method_open:

- :ref:`Error<enum_@GlobalScope_Error>` **open** **(** :ref:`String<class_String>` path **)**

Opens an existing directory of the filesystem. The ``path`` argument can be within the project tree (``res://folder``), the user directory (``user://folder``) or an absolute path of the user filesystem (e.g. ``/tmp/folder`` or ``C:\tmp\folder``).

Returns one of the :ref:`Error<enum_@GlobalScope_Error>` code constants (``OK`` on success).

----

.. _class_Directory_method_remove:

- :ref:`Error<enum_@GlobalScope_Error>` **remove** **(** :ref:`String<class_String>` path **)**

Borra el archivo de destino o un directorio vacío. El argumento puede ser relativo al directorio actual, o una ruta absoluta. Si el directorio de destino no está vacío, la operación fallará.

Devuelve una de las constantes del código :ref:`Error<enum_@GlobalScope_Error>` (``OK`` en caso de éxito).

----

.. _class_Directory_method_rename:

- :ref:`Error<enum_@GlobalScope_Error>` **rename** **(** :ref:`String<class_String>` from, :ref:`String<class_String>` to **)**

Renames (move) the ``from`` file or directory to the ``to`` destination. Both arguments should be paths to files or directories, either relative or absolute. If the destination file or directory exists and is not access-protected, it will be overwritten.

Returns one of the :ref:`Error<enum_@GlobalScope_Error>` code constants (``OK`` on success).

.. |virtual| replace:: :abbr:`virtual (This method should typically be overridden by the user to have any effect.)`
.. |const| replace:: :abbr:`const (This method has no side effects. It doesn't modify any of the instance's member variables.)`
.. |vararg| replace:: :abbr:`vararg (This method accepts any number of arguments after the ones described here.)`
