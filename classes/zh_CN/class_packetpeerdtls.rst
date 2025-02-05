:github_url: hide

.. Generated automatically by doc/tools/make_rst.py in Godot's source tree.
.. DO NOT EDIT THIS FILE, but the PacketPeerDTLS.xml source instead.
.. The source is found in doc/classes or modules/<name>/doc_classes.

.. _class_PacketPeerDTLS:

PacketPeerDTLS
==============

**Inherits:** :ref:`PacketPeer<class_PacketPeer>` **<** :ref:`Reference<class_Reference>` **<** :ref:`Object<class_Object>`

DTLS数据包客户端。

描述
----

这个类表示DTLS对等连接。它可以用来连接到DTLS服务器，由\ :ref:`DTLSServer.take_connection<class_DTLSServer_method_take_connection>`\ 返回。

\ **警告:**\ 当前不支持SSL/TLS证书撤销和证书固定。只要撤销的证书在其他情况下是有效的，都将被接受。如果这是一个问题，您可能希望使用具有短有效期的自动管理证书。

方法
----

+-------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`Error<enum_@GlobalScope_Error>`     | :ref:`connect_to_peer<class_PacketPeerDTLS_method_connect_to_peer>` **(** :ref:`PacketPeerUDP<class_PacketPeerUDP>` packet_peer, :ref:`bool<class_bool>` validate_certs=true, :ref:`String<class_String>` for_hostname="", :ref:`X509Certificate<class_X509Certificate>` valid_certificate=null **)** |
+-------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                      | :ref:`disconnect_from_peer<class_PacketPeerDTLS_method_disconnect_from_peer>` **(** **)**                                                                                                                                                                                                             |
+-------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`Status<enum_PacketPeerDTLS_Status>` | :ref:`get_status<class_PacketPeerDTLS_method_get_status>` **(** **)** |const|                                                                                                                                                                                                                         |
+-------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                      | :ref:`poll<class_PacketPeerDTLS_method_poll>` **(** **)**                                                                                                                                                                                                                                             |
+-------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

枚举
----

.. _enum_PacketPeerDTLS_Status:

.. _class_PacketPeerDTLS_constant_STATUS_DISCONNECTED:

.. _class_PacketPeerDTLS_constant_STATUS_HANDSHAKING:

.. _class_PacketPeerDTLS_constant_STATUS_CONNECTED:

.. _class_PacketPeerDTLS_constant_STATUS_ERROR:

.. _class_PacketPeerDTLS_constant_STATUS_ERROR_HOSTNAME_MISMATCH:

enum **Status**:

- **STATUS_DISCONNECTED** = **0** --- 表示已断开连接的\ ``PacketPeerDTLS``\ 的状态。

- **STATUS_HANDSHAKING** = **1** --- 表示当前正在与远程对等方进行握手的\ ``PacketPeerDTLS``\ 的状态。

- **STATUS_CONNECTED** = **2** --- 表示连接到远程对等方的\ ``PacketPeerDTLS``\ 的状态。

- **STATUS_ERROR** = **3** --- 表示处于一般错误状态的\ ``PacketPeerDTLS``\ 的状态。

- **STATUS_ERROR_HOSTNAME_MISMATCH** = **4** --- 显示主机提供的DTLS证书域与请求验证的域不匹配的错误状态。

方法说明
--------

.. _class_PacketPeerDTLS_method_connect_to_peer:

- :ref:`Error<enum_@GlobalScope_Error>` **connect_to_peer** **(** :ref:`PacketPeerUDP<class_PacketPeerUDP>` packet_peer, :ref:`bool<class_bool>` validate_certs=true, :ref:`String<class_String>` for_hostname="", :ref:`X509Certificate<class_X509Certificate>` valid_certificate=null **)**

使用必须连接的底层\ :ref:`PacketPeerUDP<class_PacketPeerUDP>`\ （见\ :ref:`PacketPeerUDP.connect_to_host<class_PacketPeerUDP_method_connect_to_host>`\ ）连接一个\ ``peer``\ ，开始DTLS握手过程。如果\ ``validate_certs``\ 是\ ``true``\ ，\ ``PacketPeerDTLS``\ 将验证远程对等体提交的证书并与\ ``for_hostname``\ 参数匹配。你可以通过\ ``valid_certificate``\ 参数指定一个自定义的\ :ref:`X509Certificate<class_X509Certificate>`\ 来进行验证。

----

.. _class_PacketPeerDTLS_method_disconnect_from_peer:

- void **disconnect_from_peer** **(** **)**

断开此对等体的连接，终止DTLS会话。

----

.. _class_PacketPeerDTLS_method_get_status:

- :ref:`Status<enum_PacketPeerDTLS_Status>` **get_status** **(** **)** |const|

返回连接的状态。有关值，请参阅\ :ref:`Status<enum_PacketPeerDTLS_Status>`\ 。

----

.. _class_PacketPeerDTLS_method_poll:

- void **poll** **(** **)**

轮询连接以检查传入的数据包。经常调用此选项以更新状态并保持连接正常工作。

.. |virtual| replace:: :abbr:`virtual (This method should typically be overridden by the user to have any effect.)`
.. |const| replace:: :abbr:`const (This method has no side effects. It doesn't modify any of the instance's member variables.)`
.. |vararg| replace:: :abbr:`vararg (This method accepts any number of arguments after the ones described here.)`
