论文:"Video-Text As Game Players: Hierarchical Banzhaf Interaction for Cross-Modal Representation Learning"

期刊/会议：CVPR2023


开源代码：https://github.com/jpthu17/HBI


动机:过去的多Level对齐不好，找一个更好的多粒度对齐方法。


模型图：
![alt text](./images/HBI.png)



模型总结:
1. 首先指出相似度计算是通过双向细粒度(非全局Token)语义对齐的方式(Cap4Video)， 然后计算出不同Level(视频-帧-token/事件-行为-实体)的相似度然后整个形成最后的相似度。
2. 这篇论文设计一个Level特征提取器，对于Clip视觉编码器产生的帧(cls) 特征和Patch特征 进行 使用一个聚类模块产生更具有代表性的特征表示(事件-行为-实体 类型)。
3. 本文的"Banzhaf Interaction"一词是非常新颖和具有亮点，查看内部本质，作者通过蒙特卡洛随机掩码暴力计算出的“词-帧最优相关性权重矩阵”，作为教师模型。(理解细粒度直之间的关系)，在训练过程中逼底层的骨干网络学会这种博弈论级别的特征对齐方式。(模块蒸馏指导)




总结和思考:
1. 本篇论文在模型性能方面取得优秀的表现，同时在多Level对齐方面也是非常具有亮点和创新性，同时论文设计的聚类方式非常好。
2. 这篇基于Clip模型取得优秀的性能，代价或许就是计算量的提升和训练花费。(本人观点:一切性能的提升都需要代价的付出，能量是守恒的。)

