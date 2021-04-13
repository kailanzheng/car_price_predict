### Task 1  -- 赛题理解

本文为学习笔记，原文章详见：https://tianchi.aliyun.com/notebook-ai/detail?postId=95456

------



1. 比赛基本信息：

   - 赛题：二手车交易价格预测，赛题以预测二手车的交易价格为任务

   - 地址：https://tianchi.aliyun.com/competition/entrance/231784/introduction?spm=5176.12281957.1004.1.38b02448ausjSX

     

2. 比赛的数据概况：

   - 该数据来自某交易平台的二手车交易记录，总数据量超过40w，包含31列变量信息，其中15列为匿名变量。为了保证比赛的公平性，将会从中抽取15万条作为训练集，5万条作为测试集A，5万条作为测试集B，同时会对name、model、brand和regionCode等信息进行脱敏。

   - 以下为训练数据train.csv的列的概况**train.csv**

     - SaleID - 销售样本ID
     - name - 汽车编码
     - regDate - 汽车注册时间
     - model - 车型编码
     - brand - 品牌
     - bodyType - 车身类型
     - fuelType - 燃油类型
     - gearbox - 变速箱
     - power - 汽车功率
     - kilometer - 汽车行驶公里
     - notRepairedDamage - 汽车有尚未修复的损坏
     - regionCode - 看车地区编码
     - seller - 销售方
     - offerType - 报价类型
     - creatDate - 广告发布时间
     - price - 汽车价格
     - v_0', 'v_1', 'v_2', 'v_3', 'v_4', 'v_5', 'v_6', 'v_7', 'v_8', 'v_9', 'v_10', 'v_11', 'v_12', 'v_13','v_14' 【匿名特征，包含v0-14在内15个匿名特征】 　

     备注：匿名特征，就是未告知数据列所属的性质的特征列。训练数据中数字全都脱敏处理，都为label encoding形式，即数字形式。

3. 预测指标

   - 评价指标为MAE (Mean Absolute Error)：
     $$
     MAE=\frac{\sum_{i=1}^{n}\left|y_{i}-\hat{y}_{i}\right|}{n}
     $$
     其中yi代表第i个样本的真实值，其中yi代表第i个样本的预测值。

4. 结果提交格式：提交前请确保预测结果的格式与sample_submit.csv中的格式一致，以及提交文件后缀名为csv。形式如下:

   ```
   SaleID,price
   150000,687
   150001,1250
   150002,2580
   150003,1178
   ```

   