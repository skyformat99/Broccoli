#Broccoli
这是一个基于LoRa的无线通讯协议，有协调器（BROCCOLI_COORDINATOR），路由器（BROCCOLI_ROUTER），终端节点（BROCCOLI_ENDDEVICE）。结构简单，无需RTOS操作系统。
协调器可以连接多个路由器，路由器可以连接多个终端节点，终端节点不可以直接连接协调器。
如果网络只有两级可以使用路由器（BROCCOLI_FREE_ROUTER）和终端节点（BROCCOLI_ENDDEVICE），也可以使用协调器（BROCCOLI_COORDINATOR）和路由器（BROCCOLI_ROUTER）。
为了避免产生僵尸网络，路由节点不能接力。

本协议适合区域型物联网使用，比如智能水表系统。每个小区内放置一个协调器，每栋楼放置一个路由器，每户水表使用一个终端节点。终端节点可以使用锂亚电池供电，只要通讯不是特别频繁可以使用几年。

LoRa在比较密集传输数据时功耗不太理想，考虑加入2.4G通讯。目前考虑使用NRF51822，廉价2.4G射频带有32位低功耗单片机，并具有64位地址。