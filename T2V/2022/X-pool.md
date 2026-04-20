论文："X-Pool: Cross-Modal Language-Video Attention for Text-Video Retrieval"


期刊/会议:CVPR2022


动机：文本-视频检索中，视频信息远多于文本，文本仅对应视频局部关键帧，现有方法采用不依赖文本的视频帧聚合策略，会引入无关视觉干扰，在内容多样、场景切换多的视频上检索效果不佳，亟需文本驱动的视频帧聚焦聚合机制。

贡献：引入Cross Attention，将文本作为Q，视频帧作为K,V，计算出基于文本查询的视频总体特征。这种基于查询的查询提取的全局视频特征，可以去除和查询无关的噪音。


项目代码开源：https://github.com/layer6ai-labs/xpool


![model picture](./images/X-pool.png)




项目代码开源：https://github.com/layer6ai-labs/xpool



实验结果:![alt text](./images/X-pool_exper.png)



总结：X-pool通过cross attention 基于文本查询提取视频特征，然后计算查询和基于该查询提取视频的相似度，相比于过去的mean-pooling 性能得到了较高的提升，但是对于视频文本检索任务训练阶段从过去计算复杂度O(N)-->O(N^2)。



思考:
这篇论文让我们认识到Cross Attention在视频领域的应用，同样取得了性能显著的进步。

但是这种方式的代价是显著的，对于训练和推理阶段，每个视频都要基于查询计算提炼的特征，然后进行相似度计算。比如:MSRVTT推理阶段1000个文本视频对，我们需要基于每个查询去计算视频的特征，需要通过1000000次计算产生视频特征，然后进行后续交互计算。







