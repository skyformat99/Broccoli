#Broccoli
这是一个基于LoRa的无线通讯协议，有协调器（BROCCOLI_COORDINATOR），路由器（BROCCOLI_ROUTER），终端节点（BROCCOLI_ENDDEVICE）。结构简单，无需RTOS操作系统。
协调器可以连接多个路由器，路由器可以连接多个终端节点，终端节点不可以直接连接协调器。
如果网络只有两级可以使用路由器（BROCCOLI_FREE_ROUTER）和终端节点（BROCCOLI_ENDDEVICE），也可以使用协调器（BROCCOLI_COORDINATOR）和路由器（BROCCOLI_ROUTER）。
为了避免产生僵尸网络，路由节点不能接力。

单片机和LoRa模块接口代码在level0.c中
测试代码使用了stm32f030f4p6单片机的硬件SPI和sx1278相连

单片机	SX1278
PA0	->	DIO0
PA3	->	RESET
PA4	->	NSS
PA5	->	SCK
PA6	->	MISO
PA7	->	MOSI
