# AutoAssign: Differentiable Label Assignment for Dense Object Detection 

# ![Screen Shot 2020-12-02 at 3.31.55 PM](/Users/poodarchu/Library/Application Support/typora-user-images/Screen Shot 2020-12-02 at 3.31.55 PM.png)

This is a PyTorch implementation of the [AutoAssign paper](https://arxiv.org/abs/2007.03496):

```
@article{zhu2020autoassign,
  title={AutoAssign: Differentiable Label Assignment for Dense Object Detection},
  author={Zhu, Benjin and Wang, Jianfeng and Jiang, Zhengkai and Zong, Fuhang and Liu, Songtao and Li, Zeming and Sun, Jian},
  journal={arXiv preprint arXiv:2007.03496},
  year={2020}
}
```



## Get Started

1. install cvpods following the instructions

```shell
# Install cvpods
git clone --recursive https://github.com/poodarchu/cvpods
cd cvpods 
## build cvpods (requires GPU)
pip install -r requirements.txt
python setup.py build develop
## preprare data path
mkdir datasets
ln -s /path/to/your/coco/dataset datasets/coco
```

2. run the project

```shell
cd auto_assign.res50.fpn.coco.800size.1x

# train
pods_train --num-gpus 8

# test
pods_test --num-gpus 8
# test with provided weights
pods_test --num-gpus 8 MODEL.WEIGHTS /path/to/your/model.pth
```



## Results

| Model | Multi-scale training | Multi-scale testing | Testing time / im | AP (minival) | Link |
|:--- |:--------------------:|:--------------------:|:-----------------:|:-------:|:---:|
| [AutoAssign_Res50_FPN_1x](https://github.com/poodarchu/AutoAssign/auto_assign.res50.fpn.coco.800size.1x/config.py) | No | No | 53ms | 40.5 | [download](https://drive.google.com/file/d/11mV53SJUIpCdWj-Wbfi_fdmDz96ekb-Z/view?usp=sharing)

