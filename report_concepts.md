# 概念

在开始创建报表之前，你需要了解下图所示相关概念。

![](media/report_concepts.png)

## 数据源

在制作报表之前，需要先进行数据准备，即指定原始数据所在的数据源。EnOS为每个开通BI & Report模块的组织，默认自动创建一个数据库Report DB。可以使用数据集成功能，将Hive中的数据同步至Report DB。

## 数据集

连接数据源后，在一张或多张数据源表的基础上，通过简单的逻辑加工，得到与源表建立连接的逻辑表，即为数据集。它在报表设计环节可直接被引用，用户无需再关心报表设计以外的底层数据表逻辑处理。

## 报表

报表支持通过所见即所得的方式，拖拽图表的设计布局，自定义报表内容。报表采用灵活的磁贴式布局来显示报表数据的交互。报表中可以包含多种分析图表和控件，并可进行过滤、多图表关联等高级操作。