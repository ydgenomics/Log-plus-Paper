# Log
This repository is remembering my logs.

---
## 20250523
基因名不对应的问题一直困扰着我们，当我们在处理基因的时候常常无法很好对应，总是需要在相应的分析流程中考虑到这个问题，显然是低效率的，所以要做到一开始就要考虑到这个问题，基因组的gtf文件和蛋白质fasta序列中的注释要一致，那么那些下游分析就可以很好杜绝这种问题！！！

**Gold Standard** of file upstream-preparation
```shell
# 1. .fasta and .gtf files of genome
# 2. .fasta file of protein
# transcription_id = gene_id ？ whether exist difference between transcription_id and gene_id
```

提出peanut单细胞矩阵中基因名和蛋白质基因名不对应的问题。发现gtf里面有关基因名是两列，transcription_id和gene_id。transcription_id和蛋白质序列是对应的，有.1后缀，说明建好的index和scRNA-seq流程倾向于使用gene_id，为了解决这个问题，后面的分析最好把期望的基因id放在gene_id里面。对于gtf文件的处理，使用GRN-SCENIC-database环境！

## 20250522
pySCENIC运行比较复杂！
1. 非模式物种要建cistarget_databases
2. pySCENIC环境的搭建与运行，之前用的别人的环境，生成的AUCell数据格式有问题，后面用biomamba的代码搭建的环境运行速度太慢，应该是worker没有配置好，与其如此直接用作者的pySCENIC的docker来跑；
3. 可视化部分要用到R版本的SCENIC，所以就有了环境GRN-SCENIC-R

**Gold Standard** of Scripts
```
# Title: deal_genome.R
# Date: 20250522
# Coder: ydgenomics
# Description:
# Input: gtf file and fasta file
# Output:
# Image: 
# Reference: https://mp.weixin.qq.com/s/7-vKrLiFS4Tlkt-rHxEGeQ; https://github.com/aertslab/create_cisTarget_databases
```

## 20250521
解决tomato的可视化和结果解读；学习自建cistarget拿到feather和tbl文件做peanut的pySCENIC分析；总结知识，从内容上，gold standard逻辑，建立通用性分析流程

## 2025-05--20
1.做GRN分析的软件有那些？已知的就是pySCENIC，但是pySCENIC依赖于motif和TF信息，我在plantTFDB里面没有发现peanut的数据，所以现在很难办；2.是否存在不依赖于库的做GRN分析，即非监督的unsupervise的分析；3.如果没有unsupervise的方法，那我们可能需要做prediction和同源转换。
GRN分析一直没有解决，内容总结，通用性测试，流程搭建和结果解读。
遗留问题：pySCENIC结果可视化需要的R环境没装好；拿到peanut的三个文件，即.feather and .tbl

**同源基因和直系同源基因的区别**：同源基因包括直系同源基因和旁系同源基因，直系同源基因是进化分化产生的，来自共同祖先基因，在进化分化过程中趋于稳定；而旁系同源基因多由于基因复制和环境适应而产生的，故基因间差别更大。
**基于DNA序列和基于蛋白质序列找同源基因的区别**：DNA序列多样性高，而蛋白质序列较保守，在氨基酸的简并性，核酸有变化，但是蛋白质可能无变化；蛋白质序列偏向功能，做功能性同源的话用蛋白质序列更好。故eggnog-mapper的注释用的是protein序列。


## 2025-04--21
本周工作内容：
  - 跑水稻叶鞘项目的数据，其中包括整合、注释(基于scPlantLLM，注意基因名的对应和rice参数的对应)、GeneNMF拿到MP即meta program，元程序；
  - 跑tomato和peanut的GRN，基因调控网络，pySCENIC应该是要提供潜在的库，而hdWGCNA是基于共表达预测的；

## 2025-04--12
基于泛化的大模型通过fine-tuning拿到适配专一的模型，这也是节省资源，快速运用的方法之一。同时带着这个思路是不是可以训练一个GO和KEGG富集结果解读的神器呢？
