
# 《kafka原理剖析与实战演练》最后一次大作业

 首先感谢老师耐心地回答我们的问题。
 
 作业题目每5秒输出过去1小时18岁到35岁用户所购买的商品中，每种品类销售额排名前十的订单汇总信息。
 
 解题思路：
 确定统计维度为（品类+商品名称），所以map的维度为 itemType + itemName ，

 通过进行重新map 操作，来实现按（品类+商品名称）重新映射

 然后，通过按照（品类+商品名称别）来进行group by 最后进行reduce ，将相同的维度值，进行汇总。得到结果
 
 reduce的时候定义时间窗口为一小时，每5秒钟统计一次
 
 最后的销售排名，由输出端处理。
 
 注：最主要的Kafka Stream应用的代码在PurchaseAnalysis.java文件中
