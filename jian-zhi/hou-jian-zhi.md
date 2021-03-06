# 后剪枝

后剪枝先从训练集生成一棵完整决策树,例如基于表4.2的数据我们得到 如图4.5所示的决策树.易知，该决策树的验证集精度为42.9%. 

![&#x56FE;4.5](../.gitbook/assets/image%20%286%29.png)

后剪枝首先考察图4.5中的结点⑥.若将其领衔的分支剪除，则相当于 把⑥替换为叶结点.替换后的叶结点包含编号为{7, 15}的训练样本,于是,该 叶结点的类别标记为“好瓜”,此时决策树的验证集精度提高至57.1%.于是, 后剪枝策略决定剪枝,如图4.7所示. 

![&#x56FE;4.7](../.gitbook/assets/image%20%2813%29.png)

然后考察结点⑤，若将其领衔的子树替换为叶结点，则替换后的叶结点包 含编号为{6,7,15}的训练样例，叶结点类别标记为“好瓜”，此时决策树验证 集精度仍为57.1%. 于是,可以不进行剪枝. 

对结点②,若将其领衔的子树替换为叶结点，则替换后的叶结点包含编号 为{1,2,3,14}的训练样例，叶结点标记为“好瓜”。此时决策树的验证集精度 提高至71.4%. 于是,后剪枝策略决定剪枝. 

对结点③和①,若将其领衔的子树替换为叶结点，则所得决策树的验证集 精度分别为71.4%与42.9%,均未得到提高.于是它们被保留.

最终,基于后剪枝策略从表4.2数据所生成的决策树如图4.7所示，其验证 集精度为71.4%. 

对比图4.7和图4.6可看出,后剪枝决策树通常比预剪枝决策树保留了更多的分支，一般情形下，后剪枝决策树的欠拟合风险很小，泛化性能往往优于预 剪枝决策树.但后剪枝过程是在生成完全决策树之后进行的，并且要自底向上 地对树中的所有非叶结点进行逐一考察,因此其训练时间开销比未剪枝决策树和预剪枝决策树都要大得多.

