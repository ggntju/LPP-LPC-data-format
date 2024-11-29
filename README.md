# LPP/LPC 数据格式

## LPP 数据格式

LPP数据格式是描述增材制造过程中，层模型信息的一种数据格式。LPP基于JSON，定义了增材制造过程监测所需的字段，其中包含层宏信息，层SLMO监测系统增益控制参数和层数据块信息。

### 详细定义

[LPP definition](./LPP-definition.md)

### 示例

[LPP example](./lpp-example.json)

### 数据结构

[LPP schema](./lpp-data-schema.json)

## LPC 数据格式

LPC数据格式是增材制造过程中，打印机PLC发送控制指令给SLMO监测系统的一种数据格式，通讯使用TCP/IP协议，LPC基于JSON，定义了增材制造过程监测控制所需的字段，其中包含打印项目的开始与结束；单层监测的激活，开始与结束；监测数据与路径的逆构结果查询；SLMO监测系统IP地址查询。LPC分为请求与回复。

[LPC 请求](./lpc-request/)

[LPC 回复](./lpc-response/)