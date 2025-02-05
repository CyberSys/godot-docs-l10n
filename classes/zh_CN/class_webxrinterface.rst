:github_url: hide

.. Generated automatically by doc/tools/make_rst.py in Godot's source tree.
.. DO NOT EDIT THIS FILE, but the WebXRInterface.xml source instead.
.. The source is found in doc/classes or modules/<name>/doc_classes.

.. _class_WebXRInterface:

WebXRInterface
==============

**Inherits:** :ref:`ARVRInterface<class_ARVRInterface>` **<** :ref:`Reference<class_Reference>` **<** :ref:`Object<class_Object>`

使用 WebXR 的 AR/VR 接口。

描述
----

WebXR是一个开放标准，允许创建在网络浏览器中运行的VR和AR应用程序。

因此，这个界面只有在HTML5导出中运行时才能使用。

WebXR支持广泛的设备，从能力很强的设备（如Valve Index、HTC Vive、Oculus Rift和Quest）到能力较弱的设备（如Google Cardboard、Oculus Go、GearVR或普通智能手机）。

由于WebXR是基于Javascript的，它大量使用回调，这意味着\ ``WebXRInterface``\ 被迫使用信号，而其他AR/VR界面会使用立即返回结果的函数。这使得\ ``WebXRInterface``\ 的初始化比其他AR/VR接口要复杂很多。

下面是启动一个沉浸式VR会话所需的最小代码。

::

    extends Spatial
    
    var webxr_interface
    var vr_supported = false
    
    func _ready():
        # 我们假设这个节点有一个按钮作为子节点。
        # 这个按钮是让用户同意进入沉浸式VR模式。
        $Button.connect("pressed", self, "_on_Button_pressed")
    
        webxr_interface = ARVRServer.find_interface("WebXR")
        if webxr_interface:
            # WebXR使用了大量的异步回调，
            # 所以我们要连接各种信号来接收它们。  
            webxr_interface.connect("session_supported", self, "_webxr_session_supported")
            webxr_interface.connect("session_started", self, "_webxr_session_started")
            webxr_interface.connect("session_ended", self, "_webxr_session_ended")
            webxr_interface.connect("session_failed", self, "_webxr_session_failed")
    
            # 这将立即返回——自身的_webxr_session_supported()方法
            # (我们在上面连接了'session_supported' 信号)将在稍后被调用
            # 让我们知道它是否被支持。  
            webxr_interface.is_session_supported("immersive-vr")
    
    func _webxr_session_supported(session_mode, supported):
        if session_mode == 'immersive-vr':
            vr_supported = supported
    
    func _on_Button_pressed():
        if not vr_supported:
            OS.alert("Your browser doesn't support VR")
            return
    
        # 获得沉浸式的VR体验，而不是AR（'immersive-ar'）
        # 或一个简单的3DoF查看器（'viewer'）。   
        webxr_interface.session_mode = 'immersive-vr'
        # 'bounded-floor'是房间大小，'local-floor'是站着或坐着的
        # 体验（如果你有3DoF耳机，它会让你离地面1.6米）。
        # 而'local'则是让你在ARVROrigin处。
        # 这个列表意味着它将首先尝试请求 "bounded-floor"，
        # 如果没有其他支持的话，就退而求其次，选择 "local-floor"，
        # 如果没有别的就选 "local" 支持。
        webxr_interface.requested_reference_space_types = 'bounded-floor, local-floor, local'
        # 为了使用'local-floor'或'bounded-floor'，
        # 我们须标记这些特征。
        webxr_interface.required_features = 'local-floor'
        webxr_interface.optional_features = 'bounded-floor'
    
        # 如果无法请求会话，这将返回false。
        # 然而，在这个过程中，它仍然可能异步失败
        # 只有在
        # _webxr_session_started()或_webxr_session_failed()方法被调用时，才知道它是否真的成功或失败。
        if not webxr_interface.initialize():
            OS.alert("Failed to initialize")
            return
    
    func _webxr_session_started():
        $Button.visible = false
        # 这告诉Godot开始进行渲染。
        get_viewport().arvr = true
        # 这将是您从上面请求的类型中最终得到的引用空间类型。
        # 如果你想让游戏在'bounded-floor'和 'local-floor' 中有一点不同，
        # 这是很有用的。  
        print ("Reference space type: " + webxr_interface.reference_space_type)
    
    func _webxr_session_ended():
        $Button.visible = true
        # 如果用户退出沉浸模式，
        # 我们就会告诉Godot重新渲染到网页上。
        get_viewport().arvr = false
    
    func _webxr_session_failed(message):
        OS.alert("Failed to initialize: " + message)

有几种方法来处理 "controller" 控制器的输入。

- 使用\ :ref:`ARVRController<class_ARVRController>`\ 节点和它们的\ :ref:`ARVRController.button_pressed<class_ARVRController_signal_button_pressed>`\ 和\ :ref:`ARVRController.button_release<class_ARVRController_signal_button_release>`\ 信号。这是Godot的AR/VR应用中通常处理控制器的方式，然而，这只适用于高级VR控制器，例如Oculus Touch或Index控制器。按钮代码由\ `WebXR Gamepads模块 <https://immersive-web.github.io/webxr-gamepads-module/#xr-standard-gamepad-mapping>`__\ 的3.3节定义。

- 使用\ :ref:`Node._unhandled_input<class_Node_method__unhandled_input>`\ 和\ :ref:`InputEventJoypadButton<class_InputEventJoypadButton>`\ 或\ :ref:`InputEventJoypadMotion<class_InputEventJoypadMotion>`\ 。这和普通的游戏手柄工作原理一样，只是\ :ref:`InputEvent.device<class_InputEvent_property_device>`\ 从100开始，所以左边的控制器是100，右边的控制器是101，按钮代码由\ `WebXR Gamepads模块 <https://immersive-web.github.io/webxr-gamepads-module/#xr-standard-gamepad-mapping>`__\ 的3.3节定义。

- 使用\ :ref:`select<class_WebXRInterface_signal_select>`\ 、\ :ref:`squeeze<class_WebXRInterface_signal_squeeze>`\ 和相关信号。这种方法既适用于高级的VR控制器，也适用于非传统的 "controller" 控制器，如在屏幕上的点击、口语化的语音命令或设备本身的按键。传递给这些信号的\ ``controller_id``\ 是与\ :ref:`ARVRController.controller_id<class_ARVRController_property_controller_id>`\ 中使用的id相同。

你可以使用这些方法中的一个或全部，让你的游戏或应用程序支持更广泛或更窄的设备和输入方法，或者允许与更高级的设备进行更高级的交互。

教程
----

- `How to make a VR game for WebXR with Godot <https://www.snopekgames.com/blog/2020/how-make-vr-game-webxr-godot>`__

属性
----

+-------------------------------------------------+-------------------------------------------------------------------------------------------------------+
| :ref:`PoolVector3Array<class_PoolVector3Array>` | :ref:`bounds_geometry<class_WebXRInterface_property_bounds_geometry>`                                 |
+-------------------------------------------------+-------------------------------------------------------------------------------------------------------+
| :ref:`String<class_String>`                     | :ref:`optional_features<class_WebXRInterface_property_optional_features>`                             |
+-------------------------------------------------+-------------------------------------------------------------------------------------------------------+
| :ref:`String<class_String>`                     | :ref:`reference_space_type<class_WebXRInterface_property_reference_space_type>`                       |
+-------------------------------------------------+-------------------------------------------------------------------------------------------------------+
| :ref:`String<class_String>`                     | :ref:`requested_reference_space_types<class_WebXRInterface_property_requested_reference_space_types>` |
+-------------------------------------------------+-------------------------------------------------------------------------------------------------------+
| :ref:`String<class_String>`                     | :ref:`required_features<class_WebXRInterface_property_required_features>`                             |
+-------------------------------------------------+-------------------------------------------------------------------------------------------------------+
| :ref:`String<class_String>`                     | :ref:`session_mode<class_WebXRInterface_property_session_mode>`                                       |
+-------------------------------------------------+-------------------------------------------------------------------------------------------------------+
| :ref:`String<class_String>`                     | :ref:`visibility_state<class_WebXRInterface_property_visibility_state>`                               |
+-------------------------------------------------+-------------------------------------------------------------------------------------------------------+

方法
----

+-----------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`ARVRPositionalTracker<class_ARVRPositionalTracker>` | :ref:`get_controller<class_WebXRInterface_method_get_controller>` **(** :ref:`int<class_int>` controller_id **)** |const|          |
+-----------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+
| void                                                      | :ref:`is_session_supported<class_WebXRInterface_method_is_session_supported>` **(** :ref:`String<class_String>` session_mode **)** |
+-----------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+

信号
----

.. _class_WebXRInterface_signal_reference_space_reset:

- **reference_space_reset** **(** **)**

发出该消息以表明引用空间已被重置或重新配置。

何时或是否发出取决于用户的浏览器或设备，但可能包括当用户改变了他们的游戏空间的尺寸，你可以通过\ :ref:`bounds_geometry<class_WebXRInterface_property_bounds_geometry>`\ 访问，或按下/按住一个按钮来重新定位他们的位置。

参阅\ `WebXR的XRReferenceSpace重置事件 <https://developer.mozilla.org/en-US/docs/Web/API/XRReferenceSpace/reset_event>`__\ 。

----

.. _class_WebXRInterface_signal_select:

- **select** **(** :ref:`int<class_int>` controller_id **)**

当一个“controller”控制器完成其“primary action”主要动作后触发。

使用 :ref:`get_controller<class_WebXRInterface_method_get_controller>` 来获得更多关于控制器的信息。

----

.. _class_WebXRInterface_signal_selectend:

- **selectend** **(** :ref:`int<class_int>` controller_id **)**

当一个“controller”控制器完成其“primary action”主要动作时触发。

使用 :ref:`get_controller<class_WebXRInterface_method_get_controller>` 来获得更多关于控制器的信息。

----

.. _class_WebXRInterface_signal_selectstart:

- **selectstart** **(** :ref:`int<class_int>` controller_id **)**

当一个“controller”控制器开始其“primary action”主要动作时触发。

使用 :ref:`get_controller<class_WebXRInterface_method_get_controller>` 来获得更多关于控制器的信息。

----

.. _class_WebXRInterface_signal_session_ended:

- **session_ended** **(** **)**

当用户结束WebXR会话时触发，可以使用浏览器或设备的用户界面来完成。

此时，你应该执行\ ``get_viewport().arvr = false``\ 来指示Godot恢复对屏幕的渲染。

----

.. _class_WebXRInterface_signal_session_failed:

- **session_failed** **(** :ref:`String<class_String>` message **)**

如果会话启动失败，由\ :ref:`ARVRInterface.initialize<class_ARVRInterface_method_initialize>`\ 触发。

\ ``message``\ 可以选择包含一个来自WebXR的错误信息，如果没有信息，则为空字符串。

----

.. _class_WebXRInterface_signal_session_started:

- **session_started** **(** **)**

如果会话成功启动，由\ :ref:`ARVRInterface.initialize<class_ARVRInterface_method_initialize>`\ 触发。

此时，应该执行\ ``get_viewport().arvr = true``\ 来指示Godot开始向AR/VR设备进行渲染是安全的。

----

.. _class_WebXRInterface_signal_session_supported:

- **session_supported** **(** :ref:`String<class_String>` session_mode, :ref:`bool<class_bool>` supported **)**

由\ :ref:`is_session_supported<class_WebXRInterface_method_is_session_supported>`\ 触发，表示是否支持指定的\ ``session_mode``\ 。

----

.. _class_WebXRInterface_signal_squeeze:

- **squeeze** **(** :ref:`int<class_int>` controller_id **)**

当其中一个“controller”控制器完成其“primary squeeze action”主要按压动作后触发。

使用 :ref:`get_controller<class_WebXRInterface_method_get_controller>` 来获得更多关于控制器的信息。

----

.. _class_WebXRInterface_signal_squeezeend:

- **squeezeend** **(** :ref:`int<class_int>` controller_id **)**

当其中一个“controller”控制器完成其“primary squeeze action”主要按压动作时触发。

使用 :ref:`get_controller<class_WebXRInterface_method_get_controller>` 来获得更多关于控制器的信息。

----

.. _class_WebXRInterface_signal_squeezestart:

- **squeezestart** **(** :ref:`int<class_int>` controller_id **)**

当其中一个“controller”控制器开始其“primary squeeze action”主要按压动作时触发。

使用 :ref:`get_controller<class_WebXRInterface_method_get_controller>` 来获得更多关于控制器的信息。

----

.. _class_WebXRInterface_signal_visibility_state_changed:

- **visibility_state_changed** **(** **)**

当\ :ref:`visibility_state<class_WebXRInterface_property_visibility_state>`\ 已更改时触发。

属性说明
--------

.. _class_WebXRInterface_property_bounds_geometry:

- :ref:`PoolVector3Array<class_PoolVector3Array>` **bounds_geometry**

+----------+-----------------------+
| *Getter* | get_bounds_geometry() |
+----------+-----------------------+

定义用户游戏区域边界的多边形的顶点。

这仅在 :ref:`reference_space_type<class_WebXRInterface_property_reference_space_type>` 是 ``"bounded-floor"`` ，并且仅在支持它的某些浏览器和设备上可用。

\ :ref:`reference_space_reset<class_WebXRInterface_signal_reference_space_reset>` 信号可以指示何时改变。

----

.. _class_WebXRInterface_property_optional_features:

- :ref:`String<class_String>` **optional_features**

+----------+------------------------------+
| *Setter* | set_optional_features(value) |
+----------+------------------------------+
| *Getter* | get_optional_features()      |
+----------+------------------------------+

:ref:`ARVRInterface.initialize<class_ARVRInterface_method_initialize>` 设置 WebXR 会话时使用的可选功能的逗号分隔列表。

如果用户的浏览器或设备不支持指定的功能，初始化将继续，但您将无法使用请求的功能。

这对已经初始化的接口没有任何影响。

可能的值来自 `WebXR 的 XRReferenceSpaceType <https://developer.mozilla.org/en-US/docs/Web/API/XRReferenceSpaceType>`__\ 。如果要使用特定的引用空间类型，则必须将其列在 :ref:`required_features<class_WebXRInterface_property_required_features>` 或 :ref:`optional_features<class_WebXRInterface_property_optional_features>` 中。

----

.. _class_WebXRInterface_property_reference_space_type:

- :ref:`String<class_String>` **reference_space_type**

+----------+----------------------------+
| *Getter* | get_reference_space_type() |
+----------+----------------------------+

引用空间类型，来自\ :ref:`requested_reference_space_types<class_WebXRInterface_property_requested_reference_space_types>`\ 属性中设置的请求类型列表，最终由\ :ref:`ARVRInterface.initialize<class_ARVRInterface_method_initialize>`\ 在设置WebXR会话时使用。

可能的值来自\ `WebXR的XRReferenceSpaceType <https://developer.mozilla.org/en-US/docs/Web/API/XRReferenceSpaceType>`__\ 。如果你想使用一个特定的引用空间类型，它必须被列入\ :ref:`required_features<class_WebXRInterface_property_required_features>`\ 或\ :ref:`optional_features<class_WebXRInterface_property_optional_features>`\ 中。

----

.. _class_WebXRInterface_property_requested_reference_space_types:

- :ref:`String<class_String>` **requested_reference_space_types**

+----------+--------------------------------------------+
| *Setter* | set_requested_reference_space_types(value) |
+----------+--------------------------------------------+
| *Getter* | get_requested_reference_space_types()      |
+----------+--------------------------------------------+

:ref:`ARVRInterface.initialize<class_ARVRInterface_method_initialize>` 设置 WebXR 会话时使用的引用空间类型的逗号分隔列表。

按顺序请求引用空间类型，将使用用户设备或浏览器支持的第一个。 :ref:`reference_space_type<class_WebXRInterface_property_reference_space_type>` 属性包含最终使用的引用空间类型。

这对已经初始化的接口没有任何影响。

可能的值来自 `WebXR 的 XRReferenceSpaceType <https://developer.mozilla.org/en-US/docs/Web/API/XRReferenceSpaceType>`__\ 。如果要使用特定的参考空间类型，则必须将其列入 :ref:`required_features<class_WebXRInterface_property_required_features>` 或 :ref:`optional_features<class_WebXRInterface_property_optional_features>` 中。

----

.. _class_WebXRInterface_property_required_features:

- :ref:`String<class_String>` **required_features**

+----------+------------------------------+
| *Setter* | set_required_features(value) |
+----------+------------------------------+
| *Getter* | get_required_features()      |
+----------+------------------------------+

:ref:`ARVRInterface.initialize<class_ARVRInterface_method_initialize>` 设置 WebXR 会话时使用的所需功能的逗号分隔列表。

如果用户的浏览器或设备不支持指定的功能，初始化将失败并发出 :ref:`session_failed<class_WebXRInterface_signal_session_failed>`\ 。

这对已经初始化的接口没有任何影响。

可能的值来自 `WebXR 的 XRReferenceSpaceType <https://developer.mozilla.org/en-US/docs/Web/API/XRReferenceSpaceType>`__\ 。如果要使用特定的参考空间类型，则必须将其列入 :ref:`required_features<class_WebXRInterface_property_required_features>` 或 :ref:`optional_features<class_WebXRInterface_property_optional_features>` 中。

----

.. _class_WebXRInterface_property_session_mode:

- :ref:`String<class_String>` **session_mode**

+----------+-------------------------+
| *Setter* | set_session_mode(value) |
+----------+-------------------------+
| *Getter* | get_session_mode()      |
+----------+-------------------------+

设置WebXR会话时，\ :ref:`ARVRInterface.initialize<class_ARVRInterface_method_initialize>`\ 所使用的会话模式。

在已经初始化的情况下，这对接口没有任何影响。

可能的值来自\ `WebXR的XRSessionMode <https://developer.mozilla.org/en-US/docs/Web/API/XRSessionMode>`__\ ，包括:``"immersive-vr"``, ``"immersive-ar"``, 和\ ``"inline"``\ 。

----

.. _class_WebXRInterface_property_visibility_state:

- :ref:`String<class_String>` **visibility_state**

+----------+------------------------+
| *Getter* | get_visibility_state() |
+----------+------------------------+

指示用户是否可以看到 WebXR 会话的图像。

可能的值来自 `WebXR 的 XRVisibilityState <https://developer.mozilla.org/en-US/docs/Web/API/XRVisibilityState>`__\ ，包括 ``"hidden"``, ``"visible"``, 和 ``"visible-blurred"``\ 。

方法说明
--------

.. _class_WebXRInterface_method_get_controller:

- :ref:`ARVRPositionalTracker<class_ARVRPositionalTracker>` **get_controller** **(** :ref:`int<class_int>` controller_id **)** |const|

获取给定 ``controller_id`` 的 :ref:`ARVRPositionalTracker<class_ARVRPositionalTracker>`\ 。

在 WebXR 的上下文中， "controller"控制器可以是高级 VR 控制器，如 Oculus Touch 或 Index 控制器，甚至可以是屏幕上的点击、语音命令或设备本身的按钮按下。当使用非传统控制器时，将 :ref:`ARVRPositionalTracker<class_ARVRPositionalTracker>` 的位置和方向解释为指向用户希望与之交互的对象的射线。

使用此方法获取有关触发以下信号之一的控制器的信息：

- :ref:`selectstart<class_WebXRInterface_signal_selectstart>`\ 

- :ref:`select<class_WebXRInterface_signal_select>`\ 

- :ref:`selectend<class_WebXRInterface_signal_selectend>`\ 

- :ref:`squeezestart<class_WebXRInterface_signal_squeezestart>`\ 

- :ref:`squeeze<class_WebXRInterface_signal_squeeze>`\ 

- :ref:`squeezestart<class_WebXRInterface_signal_squeezestart>`

----

.. _class_WebXRInterface_method_is_session_supported:

- void **is_session_supported** **(** :ref:`String<class_String>` session_mode **)**

检查给定的\ ``session_mode``\ 是否被用户的浏览器支持。

可能的值来自\ `WebXR的XRSessionMode <https://developer.mozilla.org/en-US/docs/Web/API/XRSessionMode>`__\ ，包括:``"immersive-vr"``, ``"immersive-ar"``, 和\ ``"inline"``\ 。

此方法不返回任何东西，而是将结果发送给\ :ref:`session_supported<class_WebXRInterface_signal_session_supported>`\ 信号。

.. |virtual| replace:: :abbr:`virtual (This method should typically be overridden by the user to have any effect.)`
.. |const| replace:: :abbr:`const (This method has no side effects. It doesn't modify any of the instance's member variables.)`
.. |vararg| replace:: :abbr:`vararg (This method accepts any number of arguments after the ones described here.)`
