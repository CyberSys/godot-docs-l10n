:github_url: hide

.. Generated automatically by doc/tools/make_rst.py in Godot's source tree.
.. DO NOT EDIT THIS FILE, but the NetworkedMultiplayerENet.xml source instead.
.. The source is found in doc/classes or modules/<name>/doc_classes.

.. _class_NetworkedMultiplayerENet:

NetworkedMultiplayerENet
========================

**Inherits:** :ref:`NetworkedMultiplayerPeer<class_NetworkedMultiplayerPeer>` **<** :ref:`PacketPeer<class_PacketPeer>` **<** :ref:`Reference<class_Reference>` **<** :ref:`Object<class_Object>`

使用\ `ENet <http://enet.bespin.org/index.html>`__\ 库实现PacketPeer。

描述
----

一个 PacketPeer 实现，应该在初始化为客户端或服务器后传递给 :ref:`SceneTree.network_peer<class_SceneTree_property_network_peer>`\ 。然后可以通过连接到 :ref:`SceneTree<class_SceneTree>` 信号来处理事件。

ENet 的目的是在 UDP（用户数据报协议）之上提供一个相对简单而健全的网络通信层。

\ **注意：** ENet 只使用UDP，不使用TCP。转发服务器端口使您的服务器可以在公网上访问时，只需要将服务器端口转发为UDP即可。您可以使用 :ref:`UPNP<class_UPNP>` 类尝试在启动服务器时自动转发服务器端口。

教程
----

- :doc:`../tutorials/networking/high_level_multiplayer`

- `http://enet.bespin.org/usergroup0.html <http://enet.bespin.org/usergroup0.html>`__

属性
----

+-----------------------------------------------------------------------+-----------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------+
| :ref:`bool<class_bool>`                                               | :ref:`always_ordered<class_NetworkedMultiplayerENet_property_always_ordered>`     | ``false``                                                                                                             |
+-----------------------------------------------------------------------+-----------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------+
| :ref:`int<class_int>`                                                 | :ref:`channel_count<class_NetworkedMultiplayerENet_property_channel_count>`       | ``3``                                                                                                                 |
+-----------------------------------------------------------------------+-----------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------+
| :ref:`CompressionMode<enum_NetworkedMultiplayerENet_CompressionMode>` | :ref:`compression_mode<class_NetworkedMultiplayerENet_property_compression_mode>` | ``1``                                                                                                                 |
+-----------------------------------------------------------------------+-----------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------+
| :ref:`String<class_String>`                                           | :ref:`dtls_hostname<class_NetworkedMultiplayerENet_property_dtls_hostname>`       | ``""``                                                                                                                |
+-----------------------------------------------------------------------+-----------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------+
| :ref:`bool<class_bool>`                                               | :ref:`dtls_verify<class_NetworkedMultiplayerENet_property_dtls_verify>`           | ``true``                                                                                                              |
+-----------------------------------------------------------------------+-----------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------+
| :ref:`bool<class_bool>`                                               | refuse_new_connections                                                            | ``false`` (overrides :ref:`NetworkedMultiplayerPeer<class_NetworkedMultiplayerPeer_property_refuse_new_connections>`) |
+-----------------------------------------------------------------------+-----------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------+
| :ref:`bool<class_bool>`                                               | :ref:`server_relay<class_NetworkedMultiplayerENet_property_server_relay>`         | ``true``                                                                                                              |
+-----------------------------------------------------------------------+-----------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------+
| :ref:`int<class_int>`                                                 | :ref:`transfer_channel<class_NetworkedMultiplayerENet_property_transfer_channel>` | ``-1``                                                                                                                |
+-----------------------------------------------------------------------+-----------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------+
| :ref:`TransferMode<enum_NetworkedMultiplayerPeer_TransferMode>`       | transfer_mode                                                                     | ``2`` (overrides :ref:`NetworkedMultiplayerPeer<class_NetworkedMultiplayerPeer_property_transfer_mode>`)              |
+-----------------------------------------------------------------------+-----------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------+
| :ref:`bool<class_bool>`                                               | :ref:`use_dtls<class_NetworkedMultiplayerENet_property_use_dtls>`                 | ``false``                                                                                                             |
+-----------------------------------------------------------------------+-----------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------+

方法
----

+---------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                  | :ref:`close_connection<class_NetworkedMultiplayerENet_method_close_connection>` **(** :ref:`int<class_int>` wait_usec=100 **)**                                                                                                                                         |
+---------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`Error<enum_@GlobalScope_Error>` | :ref:`create_client<class_NetworkedMultiplayerENet_method_create_client>` **(** :ref:`String<class_String>` address, :ref:`int<class_int>` port, :ref:`int<class_int>` in_bandwidth=0, :ref:`int<class_int>` out_bandwidth=0, :ref:`int<class_int>` client_port=0 **)** |
+---------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`Error<enum_@GlobalScope_Error>` | :ref:`create_server<class_NetworkedMultiplayerENet_method_create_server>` **(** :ref:`int<class_int>` port, :ref:`int<class_int>` max_clients=32, :ref:`int<class_int>` in_bandwidth=0, :ref:`int<class_int>` out_bandwidth=0 **)**                                     |
+---------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                  | :ref:`disconnect_peer<class_NetworkedMultiplayerENet_method_disconnect_peer>` **(** :ref:`int<class_int>` id, :ref:`bool<class_bool>` now=false **)**                                                                                                                   |
+---------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`int<class_int>`                 | :ref:`get_last_packet_channel<class_NetworkedMultiplayerENet_method_get_last_packet_channel>` **(** **)** |const|                                                                                                                                                       |
+---------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`int<class_int>`                 | :ref:`get_packet_channel<class_NetworkedMultiplayerENet_method_get_packet_channel>` **(** **)** |const|                                                                                                                                                                 |
+---------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`String<class_String>`           | :ref:`get_peer_address<class_NetworkedMultiplayerENet_method_get_peer_address>` **(** :ref:`int<class_int>` id **)** |const|                                                                                                                                            |
+---------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`int<class_int>`                 | :ref:`get_peer_port<class_NetworkedMultiplayerENet_method_get_peer_port>` **(** :ref:`int<class_int>` id **)** |const|                                                                                                                                                  |
+---------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                  | :ref:`set_bind_ip<class_NetworkedMultiplayerENet_method_set_bind_ip>` **(** :ref:`String<class_String>` ip **)**                                                                                                                                                        |
+---------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                  | :ref:`set_dtls_certificate<class_NetworkedMultiplayerENet_method_set_dtls_certificate>` **(** :ref:`X509Certificate<class_X509Certificate>` certificate **)**                                                                                                           |
+---------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                  | :ref:`set_dtls_key<class_NetworkedMultiplayerENet_method_set_dtls_key>` **(** :ref:`CryptoKey<class_CryptoKey>` key **)**                                                                                                                                               |
+---------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                  | :ref:`set_peer_timeout<class_NetworkedMultiplayerENet_method_set_peer_timeout>` **(** :ref:`int<class_int>` id, :ref:`int<class_int>` timeout_limit, :ref:`int<class_int>` timeout_min, :ref:`int<class_int>` timeout_max **)**                                         |
+---------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

枚举
----

.. _enum_NetworkedMultiplayerENet_CompressionMode:

.. _class_NetworkedMultiplayerENet_constant_COMPRESS_NONE:

.. _class_NetworkedMultiplayerENet_constant_COMPRESS_RANGE_CODER:

.. _class_NetworkedMultiplayerENet_constant_COMPRESS_FASTLZ:

.. _class_NetworkedMultiplayerENet_constant_COMPRESS_ZLIB:

.. _class_NetworkedMultiplayerENet_constant_COMPRESS_ZSTD:

enum **CompressionMode**:

- **COMPRESS_NONE** = **0** --- 无压缩。这使用最多的带宽，但具有占用最少 CPU 资源的好处。这个选项可以用于Wireshark等工具使用，更容易进行网络调试。

- **COMPRESS_RANGE_CODER** = **1** --- ENet 的内置范围编码。适用于小数据包，但对于大于 4 KB 的数据包不是最有效的算法。

- **COMPRESS_FASTLZ** = **2** --- `FastLZ <http://fastlz.org/>`__ 压缩。与 :ref:`COMPRESS_ZLIB<class_NetworkedMultiplayerENet_constant_COMPRESS_ZLIB>` 相比，该选项使用的 CPU 资源更少，但使用的带宽更多。

- **COMPRESS_ZLIB** = **3** --- `Zlib <https://www.zlib.net/>`__\ 压缩。与 :ref:`COMPRESS_FASTLZ<class_NetworkedMultiplayerENet_constant_COMPRESS_FASTLZ>` 相比，这个选项使用较少的带宽，但代价是使用更多的 CPU 资源。请注意，这种算法对小于4KB的数据包不是很有效。因此，建议在大多数情况下使用其他压缩算法。

- **COMPRESS_ZSTD** = **4** --- `Zstandard <https://facebook.github.io/zstd/>`__\ 压缩。

属性说明
--------

.. _class_NetworkedMultiplayerENet_property_always_ordered:

- :ref:`bool<class_bool>` **always_ordered**

+-----------+---------------------------+
| *Default* | ``false``                 |
+-----------+---------------------------+
| *Setter*  | set_always_ordered(value) |
+-----------+---------------------------+
| *Getter*  | is_always_ordered()       |
+-----------+---------------------------+

在使用 :ref:`NetworkedMultiplayerPeer.TRANSFER_MODE_UNRELIABLE<class_NetworkedMultiplayerPeer_constant_TRANSFER_MODE_UNRELIABLE>` 时强制命令包。（因此行为类似于 :ref:`NetworkedMultiplayerPeer.TRANSFER_MODE_UNRELIABLE_ORDERED<class_NetworkedMultiplayerPeer_constant_TRANSFER_MODE_UNRELIABLE_ORDERED>`\ ）。这是在 RPC 系统中使用排序的唯一方法。

----

.. _class_NetworkedMultiplayerENet_property_channel_count:

- :ref:`int<class_int>` **channel_count**

+-----------+--------------------------+
| *Default* | ``3``                    |
+-----------+--------------------------+
| *Setter*  | set_channel_count(value) |
+-----------+--------------------------+
| *Getter*  | get_channel_count()      |
+-----------+--------------------------+

ENet要使用的信道数量。通道用于分离不同类型的数据。例如，在可靠或有序模式下，包交付顺序是在每个通道的基础上保证的。这样做是为了消除延迟并减少对数据包的排序限制。在一个通道中的包的交付状态不会停止在另一个通道中的其他包的交付。

----

.. _class_NetworkedMultiplayerENet_property_compression_mode:

- :ref:`CompressionMode<enum_NetworkedMultiplayerENet_CompressionMode>` **compression_mode**

+-----------+-----------------------------+
| *Default* | ``1``                       |
+-----------+-----------------------------+
| *Setter*  | set_compression_mode(value) |
+-----------+-----------------------------+
| *Getter*  | get_compression_mode()      |
+-----------+-----------------------------+

用于网络数据包的压缩方法。这些在压缩速度与带宽之间有不同的权衡，如果您完全使用压缩，您可能需要测试哪一种最适合您的用例。

\ **注：**\ 大多数游戏的网络设计都涉及频繁发送许多小数据包（每个小于4 KB）。如果有疑问，建议保留默认压缩算法，因为它对这些小数据包效果最好。

\ **注意：** :ref:`compression_mode<class_NetworkedMultiplayerENet_property_compression_mode>` 必须在服务器及其所有客户端上设置为相同的值。如果客户端上设置的 :ref:`compression_mode<class_NetworkedMultiplayerENet_property_compression_mode>` 与服务器上设置的不同，则客户端将无法连接。在 Godot 3.4 之前，默认的 :ref:`compression_mode<class_NetworkedMultiplayerENet_property_compression_mode>` 是 :ref:`COMPRESS_NONE<class_NetworkedMultiplayerENet_constant_COMPRESS_NONE>`\ 。尽管如此，不建议在客户端和服务器之间混合引擎版本，也不受官方支持。

----

.. _class_NetworkedMultiplayerENet_property_dtls_hostname:

- :ref:`String<class_String>` **dtls_hostname**

+-----------+--------------------------+
| *Default* | ``""``                   |
+-----------+--------------------------+
| *Setter*  | set_dtls_hostname(value) |
+-----------+--------------------------+
| *Getter*  | get_dtls_hostname()      |
+-----------+--------------------------+

用于 DTLS 验证的主机名，与服务器提供的证书中的“CN”值进行比较。

当设置为空字符串时，将使用传递给 :ref:`create_client<class_NetworkedMultiplayerENet_method_create_client>` 的 ``address`` 参数。

----

.. _class_NetworkedMultiplayerENet_property_dtls_verify:

- :ref:`bool<class_bool>` **dtls_verify**

+-----------+--------------------------------+
| *Default* | ``true``                       |
+-----------+--------------------------------+
| *Setter*  | set_dtls_verify_enabled(value) |
+-----------+--------------------------------+
| *Getter*  | is_dtls_verify_enabled()       |
+-----------+--------------------------------+

当\ :ref:`use_dtls<class_NetworkedMultiplayerENet_property_use_dtls>` ``true``\ 时启用或禁用证书验证。

----

.. _class_NetworkedMultiplayerENet_property_server_relay:

- :ref:`bool<class_bool>` **server_relay**

+-----------+---------------------------------+
| *Default* | ``true``                        |
+-----------+---------------------------------+
| *Setter*  | set_server_relay_enabled(value) |
+-----------+---------------------------------+
| *Getter*  | is_server_relay_enabled()       |
+-----------+---------------------------------+

启用或禁用服务器特性，该特性通知客户端其他对等体的连接/断开，并在它们之间转发消息。当此选项为\ ``false``\ 时，客户端将不会自动收到其他对等体的通知，也无法通过服务器向他们发送数据包。

----

.. _class_NetworkedMultiplayerENet_property_transfer_channel:

- :ref:`int<class_int>` **transfer_channel**

+-----------+-----------------------------+
| *Default* | ``-1``                      |
+-----------+-----------------------------+
| *Setter*  | set_transfer_channel(value) |
+-----------+-----------------------------+
| *Getter*  | get_transfer_channel()      |
+-----------+-----------------------------+

设置用于传输数据的默认通道。缺省情况下，该值为\ ``-1``\ ，表示ENet只使用2个通道:一个用于可靠报文，一个用于不可靠报文。通道\ ``0``\ 被保留，不能使用。将该成员设置为\ ``0``\ 和\ :ref:`channel_count<class_NetworkedMultiplayerENet_property_channel_count>`\ (不包括)之间的任何值将强制ENet使用该通道发送数据。有关ENet通道的更多信息，请参阅\ :ref:`channel_count<class_NetworkedMultiplayerENet_property_channel_count>`\ 。

----

.. _class_NetworkedMultiplayerENet_property_use_dtls:

- :ref:`bool<class_bool>` **use_dtls**

+-----------+-------------------------+
| *Default* | ``false``               |
+-----------+-------------------------+
| *Setter*  | set_dtls_enabled(value) |
+-----------+-------------------------+
| *Getter*  | is_dtls_enabled()       |
+-----------+-------------------------+

启用后，由该对等体创建的客户端或服务器将使用\ :ref:`PacketPeerDTLS<class_PacketPeerDTLS>`\ ，而不是原始UDP套接字与远程对等体进行通信。通信使用DTLS加密，代价是更高的资源占用和可能更大的数据包。

\ **注意：** 当创建DTLS服务器时，确保用\ :ref:`set_dtls_key<class_NetworkedMultiplayerENet_method_set_dtls_key>`\ 和\ :ref:`set_dtls_certificate<class_NetworkedMultiplayerENet_method_set_dtls_certificate>`\ 设置密钥/证书对。对于DTLS客户端，查看\ :ref:`dtls_verify<class_NetworkedMultiplayerENet_property_dtls_verify>`\ 选项，用\ :ref:`set_dtls_certificate<class_NetworkedMultiplayerENet_method_set_dtls_certificate>`\ 配置相应的证书。

方法说明
--------

.. _class_NetworkedMultiplayerENet_method_close_connection:

- void **close_connection** **(** :ref:`int<class_int>` wait_usec=100 **)**

关闭连接。如果当前没有建立连接，则忽略不计。如果这是一个服务器，它将试图在强行断开连接之前通知所有客户端。如果这是一个客户端，它只是关闭与服务器的连接。

----

.. _class_NetworkedMultiplayerENet_method_create_client:

- :ref:`Error<enum_@GlobalScope_Error>` **create_client** **(** :ref:`String<class_String>` address, :ref:`int<class_int>` port, :ref:`int<class_int>` in_bandwidth=0, :ref:`int<class_int>` out_bandwidth=0, :ref:`int<class_int>` client_port=0 **)**

创建客户端，使用指定的\ ``端口``\ 连接到\ ``地址``\ 的服务器上。给定的地址需要是一个完全合格的域名（例如，\ ``"www.example.com"``\ ）或一个IPv4或IPv6格式的IP地址（例如，\ ``"192.168.1.1"``\ ）。\ ``port``\ 是服务器所监听的端口。\ ``in_bandwidth``\ 和\ ``out_bandwidth``\ 参数可用于将传入和传出的带宽限制在给定的字节数/秒。默认的0意味着无限的带宽。请注意，ENet会在对等体之间连接的特定一侧战略性地丢弃数据包，以确保对等体的带宽不被淹没。带宽参数也决定了连接的窗口大小，它限制了在任何给定时间内可能正在传输的可靠数据包的数量。如果创建了一个客户端，返回\ :ref:`@GlobalScope.OK<class_@GlobalScope_constant_OK>`\ ；如果这个NetworkedMultiplayerENet实例已经有一个开放的连接（在这种情况下，你需要先调用\ :ref:`close_connection<class_NetworkedMultiplayerENet_method_close_connection>`\ ），返回\ :ref:`@GlobalScope.ERR_CANT_CREATE<class_@GlobalScope_constant_ERR_CANT_CREATE>`\ ；如果不能创建客户端，返回\ :ref:`@GlobalScope.ERR_CANT_CREATE<class_@GlobalScope_constant_ERR_CANT_CREATE>`\ 。如果指定了\ ``client_port``\ ，客户端也将监听给定的端口；这对一些NAT穿越技术很有用。

----

.. _class_NetworkedMultiplayerENet_method_create_server:

- :ref:`Error<enum_@GlobalScope_Error>` **create_server** **(** :ref:`int<class_int>` port, :ref:`int<class_int>` max_clients=32, :ref:`int<class_int>` in_bandwidth=0, :ref:`int<class_int>` out_bandwidth=0 **)**

创建服务器，通过\ ``port``\ 监听连接。该端口需要是一个可用的、未使用的端口，在0到65535之间。注意，低于1024的端口是特权端口，根据平台的不同可能需要提高权限。要改变服务器监听的接口，请使用\ :ref:`set_bind_ip<class_NetworkedMultiplayerENet_method_set_bind_ip>`\ 。默认IP是通配符\ ``"*"``\ ，它监听所有可用的接口。\ ``max_clients``\ 是允许同时进行的最大客户数，可以使用任何数字，最高可达4095，尽管可实现的同时进行的客户数可能要低得多，并且取决于应用。关于带宽参数的其他细节，见\ :ref:`create_client<class_NetworkedMultiplayerENet_method_create_client>`\ 。如果服务器被创建，返回\ :ref:`@GlobalScope.OK<class_@GlobalScope_constant_OK>`\ ；如果这个NetworkedMultiplayerENet实例已经有一个开放的连接（在这种情况下，你需要先调用\ :ref:`close_connection<class_NetworkedMultiplayerENet_method_close_connection>`\ ），返回\ :ref:`@GlobalScope.ERR_CANT_CREATE<class_@GlobalScope_constant_ERR_CANT_CREATE>`\ ；如果服务器不能被创建，返回\ :ref:`@GlobalScope.ERR_CANT_CREATE<class_@GlobalScope_constant_ERR_CANT_CREATE>`\ 。

----

.. _class_NetworkedMultiplayerENet_method_disconnect_peer:

- void **disconnect_peer** **(** :ref:`int<class_int>` id, :ref:`bool<class_bool>` now=false **)**

断开给定对等体的连接。如果 "now "被设置为\ ``true``\ ，连接将被立即关闭而不冲刷队列中的消息。

----

.. _class_NetworkedMultiplayerENet_method_get_last_packet_channel:

- :ref:`int<class_int>` **get_last_packet_channel** **(** **)** |const|

返回通过\ :ref:`PacketPeer.get_packet<class_PacketPeer_method_get_packet>`\ 获取的最后一个包的Channel。

----

.. _class_NetworkedMultiplayerENet_method_get_packet_channel:

- :ref:`int<class_int>` **get_packet_channel** **(** **)** |const|

返回将通过\ :ref:`PacketPeer.get_packet<class_PacketPeer_method_get_packet>`\ 获取的下一个数据包的Channel。

----

.. _class_NetworkedMultiplayerENet_method_get_peer_address:

- :ref:`String<class_String>` **get_peer_address** **(** :ref:`int<class_int>` id **)** |const|

返回给定对等体的IP地址。

----

.. _class_NetworkedMultiplayerENet_method_get_peer_port:

- :ref:`int<class_int>` **get_peer_port** **(** :ref:`int<class_int>` id **)** |const|

返回给定对等体的远程端口。

----

.. _class_NetworkedMultiplayerENet_method_set_bind_ip:

- void **set_bind_ip** **(** :ref:`String<class_String>` ip **)**

创建服务器时使用的IP。默认情况下，这被设置为通配符\ ``"*"``\ ，它绑定到所有可用的接口。IP地址格式为IPv4或IPv6，例如:``"192.168.1.1"``\ 。

----

.. _class_NetworkedMultiplayerENet_method_set_dtls_certificate:

- void **set_dtls_certificate** **(** :ref:`X509Certificate<class_X509Certificate>` certificate **)**

当\ :ref:`use_dtls<class_NetworkedMultiplayerENet_property_use_dtls>`\ 为\ ``true``\ 时，配置\ :ref:`X509Certificate<class_X509Certificate>`\ 使用。对于服务器，您还必须通过\ :ref:`set_dtls_key<class_NetworkedMultiplayerENet_method_set_dtls_key>`\ 设置\ :ref:`CryptoKey<class_CryptoKey>`\ 。

----

.. _class_NetworkedMultiplayerENet_method_set_dtls_key:

- void **set_dtls_key** **(** :ref:`CryptoKey<class_CryptoKey>` key **)**

当\ :ref:`use_dtls<class_NetworkedMultiplayerENet_property_use_dtls>`\ 为\ ``true``\ 时，配置\ :ref:`CryptoKey<class_CryptoKey>`\ 来使用。记住也要调用\ :ref:`set_dtls_certificate<class_NetworkedMultiplayerENet_method_set_dtls_certificate>`\ 来设置\ :ref:`X509Certificate<class_X509Certificate>`\ 。

----

.. _class_NetworkedMultiplayerENet_method_set_peer_timeout:

- void **set_peer_timeout** **(** :ref:`int<class_int>` id, :ref:`int<class_int>` timeout_limit, :ref:`int<class_int>` timeout_min, :ref:`int<class_int>` timeout_max **)**

Sets the timeout parameters for a peer.	The timeout parameters control how and when a peer will timeout from a failure to acknowledge reliable traffic. Timeout values are expressed in milliseconds.

The ``timeout_limit`` is a factor that, multiplied by a value based on the average round trip time, will determine the timeout limit for a reliable packet. When that limit is reached, the timeout will be doubled, and the peer will be disconnected if that limit has reached ``timeout_min``. The ``timeout_max`` parameter, on the other hand, defines a fixed timeout for which any packet must be acknowledged or the peer will be dropped.

.. |virtual| replace:: :abbr:`virtual (This method should typically be overridden by the user to have any effect.)`
.. |const| replace:: :abbr:`const (This method has no side effects. It doesn't modify any of the instance's member variables.)`
.. |vararg| replace:: :abbr:`vararg (This method accepts any number of arguments after the ones described here.)`
