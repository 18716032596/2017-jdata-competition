# 2017 JData Competition
高潜用户购买意向预测-rank12
 
# 赛题网址

https://www.datafountain.cn/competitions/247/details/data-evaluation

# 赛题任务
本次大赛以京东商城真实的用户、商品和行为数据（脱敏后）为基础，参赛队伍需要通过数据挖掘的技术和机器学习的算法，构建用户购买商品的预测模型，
输出高潜用户和目标商品的匹配结果，为精准营销提供高质量的目标群体。同时，希望参赛队伍能通过本次比赛，挖掘数据背后潜在的意义，为电商用户提供
更简单、快捷、省心的购物体验。
参赛者需要使用京东多个品类下商品的历史销售数据，构建算法模型，预测用户在未来5天内，对某个目标品类下商品的购买意向。对于训练集中出现的每一
个用户，参赛者的模型需要预测该用户在未来5天内是否购买目标品类下的商品以及所购买商品的SKU_ID。评测算法将针对参赛者提交的预测结果，计算加权得分。

# 评分公式
参赛者提交的结果文件中包含对所有用户购买意向的预测结果。对每一个用户的预测结果包括两方面：

1、该用户2016-04-16到2016-04-20是否下单P中的商品，提交的结果文件中仅包含预测为下单的用户，预测为未下单的用户，无须在结果中出现。若预测正确，则评测算法中置label=1，不正确label=0；

2、如果下单，下单的sku_id （只需提交一个sku_id），若sku_id预测正确，则评测算法中置pred=1，不正确pred=0。

对于参赛者提交的结果文件，按如下公式计算得分：

<a href="https://www.codecogs.com/eqnedit.php?latex=$Score=0.4F_{11}&space;&plus;&space;0.6F_{12}$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$Score=0.4F_{11}&space;&plus;&space;0.6F_{12}$" title="$Score=0.4F_{11} + 0.6F_{12}$" /></a>

此处的F1值定义为：

<a href="https://www.codecogs.com/eqnedit.php?latex=F_{11}=&space;\frac{6Recall&space;\cdot&space;Precise}{5Recall&plus;Precise}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?F_{11}=&space;\frac{6Recall&space;\cdot&space;Precise}{5Recall&plus;Precise}" title="F_{11}= \frac{6Recall \cdot Precise}{5Recall+Precise}" /></a>

<a href="https://www.codecogs.com/eqnedit.php?latex=F_{12}=&space;\frac{5Recall&space;\cdot&space;Precise}{2Recall&plus;3&space;\cdot&space;Precise}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?F_{12}=&space;\frac{5Recall&space;\cdot&space;Precise}{2Recall&plus;3&space;\cdot&space;Precise}" title="F_{12}= \frac{5Recall \cdot Precise}{2Recall+3 \cdot Precise}" /></a>

其中，Precise为准确率，Recall为召回率.<a href="https://www.codecogs.com/eqnedit.php?latex=F_{11}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?F_{11}" title="F_{11}" /></a>是label=1或0的F1值，<a href="https://www.codecogs.com/eqnedit.php?latex=F_{12}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?F_{12}" title="F_{12}" /></a>是pred=1或0的F1值.
