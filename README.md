# Log
This repository is remembering my logs.

---
## 2025-05--20
1.做GRN分析的软件有那些？已知的就是pySCENIC，但是pySCENIC依赖于motif和TF信息，我在plantTFDB里面没有发现peanut的数据，所以现在很难办；2.是否存在不依赖于库的做GRN分析，即非监督的unsupervise的分析；3.如果没有unsupervise的方法，那我们可能需要做prediction和同源转换。
GRN分析一直没有解决，内容总结，通用性测试，流程搭建和结果解读

## 2025-04--21
本周工作内容：
  - 跑水稻叶鞘项目的数据，其中包括整合、注释(基于scPlantLLM，注意基因名的对应和rice参数的对应)、GeneNMF拿到MP即meta program，元程序；
  - 跑tomato和peanut的GRN，基因调控网络，pySCENIC应该是要提供潜在的库，而hdWGCNA是基于共表达预测的；

## 2025-04--12
基于泛化的大模型通过fine-tuning拿到适配专一的模型，这也是节省资源，快速运用的方法之一。同时带着这个思路是不是可以训练一个GO和KEGG富集结果解读的神器呢？
