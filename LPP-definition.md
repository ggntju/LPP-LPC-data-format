# LPP 数据格式详细定义

## 宏信息

| 字段 | 含义 |
| :-----:| :----: |
| layer_sum | 当前项目总打印层数 |
| layer_index | 当前打印层序号（以0为起始) |
| datablock_sum | 当前层包含数据块总数 |
|datablock_info| 数据块信息 |
|reserved_key| 保留字段 |

## 层SLMO监测系统增益控制参数

+ 通道0 代表可见光波段 400-700nm
+ 通道1 代表近红外波段 1000-1100nm
+ 通道2 代表反射波段 1100-1800nm

| 字段 | 含义 |
| :-----:| :----: |
| ch_0_gain | 当前层SLMO通道0增益 |
| ch_1_gain | 当前层SLMO通道1增益 |
| ch_2_gain | 当前层SLMO通道2增益 |

## 数据块信息

| 字段 | 含义 |
| :-----:| :----: |
| datablock_index | 数据块序号（以0为起始） |
| datablock_name | 数据块名称 |
| datablock_type | 数据块类型 |
| skywriting_flag | sky writing 启用标记（1为启用） |
| scan_speed | 扫描速度 |
| laser_power | 激光功率 |
| datablock_data_sum | 数据块包含向量总数 |
|reserved_key| 保留字段 |
|datablock_data| 数据块向量信息 |

+ datablock_type分为两个类型，实体型和非实体型，值分别为1和3，实体型数据块是SLMO监测系统关注的对象

### 实体型数据块向量格式

整个数据块为一个JSON数组，数据块数组中的每个条目代表一条向量，每个条目格式如下，数组中包含四个数字，按照顺序分别为起始点X坐标，起始点Y坐标，终止点X坐标，终止点Y坐标。

```
[x_start,y_start,x_end,y_end]
```

### 非实体型数据块向量格式

整个数据块为一个JSON数组，数据块数组中的每个条目代表一条向量，每个条目格式如下，数组中包含一个由若干点坐标组成的连续向量，一下为一条包含三个点的连续向量示例

```
[
	[x_0,y_0],
	[x_1,y_1],
	[x_2,y_2]
]
```
