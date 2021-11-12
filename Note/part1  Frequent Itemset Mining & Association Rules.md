# part1  Frequent Itemset Mining & Association Rules

## 关联规则挖掘

Goal ： 挖掘频繁被消费者同时购买的商品集合

<img src="https://cdn.jsdelivr.net/gh/copyrosicky/Images/image-20211112162801011.png" alt="image-20211112162801011" style="zoom: 50%;" />

## Frequent Itemsets

Goal : 发现商品basket中的frequent items

定义 Support of itme I (支持度)：几个关联的数据在数据集中出现的次数占总数据集的比重

我们将support超过了阈值s的itemsete称之为frequent itemsets

<img src="https://cdn.jsdelivr.net/gh/copyrosicky/Images/image-20211112163521674.png" alt="image-20211112163521674" style="zoom:67%;" />

eg :

<img src="C:\Users\罗西基\AppData\Roaming\Typora\typora-user-images\image-20211112163555722.png" alt="image-20211112163555722" style="zoom: 50%;" />

## Association Rules

$\{i_1,i_2,...,i_k\} \rightarrow j$ 表示如果某个basket中已经包括了所有的$i_1$到$i_k$个item，那么这个basket很有可能包括$i_j$

$Confidence\ of\ association\ rules$表示给出basket $I = \{i_1,...,i_k\}$时，含有j的概率

​                                                                 $$conf(I \rightarrow j) = \frac{support(I \bigcup j)}{support(I)}$$


我们并不是关注所有的高概率关联规则，比如$X \rightarrow milk$可能发生的概率很高，但是这仅仅是因为milk会被经常购买，即milk和X是独立的。因此我们需要定义$Interest \ of \ an \ association \ rule I \rightarrow j $ 来平衡item本身被购买的概率和他成为某个basket的frequent item的概率,即找到那些“高价值的Association Rules”。

​                                                         $$Interest(I \rightarrow j) = |conf(I \rightarrow j) - Pr[j]|$$

<img src="C:\Users\罗西基\AppData\Roaming\Typora\typora-user-images\image-20211112165230485.png" alt="image-20211112165230485" style="zoom:50%;" />

## Association Rule Mining

我们现在的目标为找到$support >= s$且$confidence >= c$的关联规则

<img src="C:\Users\罗西基\AppData\Roaming\Typora\typora-user-images\image-20211112165544238.png" alt="image-20211112165544238" style="zoom: 67%;" />

