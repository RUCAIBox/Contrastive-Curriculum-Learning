# Contrastive-Curriculum-Learning

This is the official PyTorch implementation for the [paper](https://dl.acm.org/doi/abs/10.1145/3459637.3481905):
> Shuqing Bian, Wayne Xin Zhao, Kun Zhou, Jing Cai, Yancheng He, Cunxiang Yin, Ji-Rong Wen. Contrastive Curriculum Learning for Sequential User Behavior Modeling via Data Augmentation. CIKM 2021.

---

## Overview

Within online platforms, it is critical to capture the semantics of sequential user behaviors for accurately modeling user interests. However, dynamic characteristics and sparse behaviors make it difficult to train effective user representations for sequential user behavior modeling.

Inspired by the recent progress in contrastive learning, we propose a novel Contrastive Curriculum Learning framework for producing effective representations for modeling sequential user behaviors. We make important technical contributions in two aspects, namely data quality and sample ordering. Firstly, we design a model-based data generator by generating high-quality samples confirming to users' attribute information. Given a target user, it can leverage the fused attribute semantics for generating more close-to-real sequences. Secondly, we propose a curriculum learning strategy to conduct contrastive learning via an easy-to-difficult learning process. The core component is a learnable difficulty evaluator, which can score augmented sequences, and schedule them in curriculums. Extensive results on both public and industry datasets demonstrate the effectiveness of our approach on downstream tasks.


## Requirements

```
recbole==1.0.1
python==3.6.0
pytorch==1.11.0
```


### Train and evaluate on downstream datasets

```
python run_pretrain_cl.py 
```

Fine-tune the pre-trained model in curriculum learning setting.

```
python run_finetune_cl.py 
```


### Acknowledgement

The implementation is based on the open-source recommendation library [RecBole](https://github.com/RUCAIBox/RecBole).

Please cite the following papers as the references if you use our codes or the processed datasets.

```bibtex
@inproceedings{bian2021contrastive,
  title={Contrastive curriculum learning for sequential user behavior modeling via data augmentation},
  author={Bian, Shuqing and Zhao, Wayne Xin and Zhou, Kun and Cai, Jing and He, Yancheng and Yin, Cunxiang and Wen, Ji-Rong},
  booktitle={Proceedings of the 30th ACM International Conference on Information \& Knowledge Management},
  pages={3737--3746},
  year={2021}
}

@inproceedings{zhao2021recbole,
  title={Recbole: Towards a unified, comprehensive and efficient framework for recommendation algorithms},
  author={Wayne Xin Zhao and Shanlei Mu and Yupeng Hou and Zihan Lin and Kaiyuan Li and Yushuo Chen and Yujie Lu and Hui Wang and Changxin Tian and Xingyu Pan and Yingqian Min and Zhichao Feng and Xinyan Fan and Xu Chen and Pengfei Wang and Wendi Ji and Yaliang Li and Xiaoling Wang and Ji-Rong Wen},
  booktitle={{CIKM}},
  year={2021}
}
```
