# 模型库

## 1. 图像分类

数据集：ImageNet1000类

### 1.1 量化

| 模型 | 压缩方法 | Top-1/Top-5 Acc | 模型体积（MB） | TensorRT时延(V100, ms) | 下载 |
|:--:|:---:|:--:|:--:|:--:|:--:|
|MobileNetV1|-|70.99%/89.68%| 17 | -| [下载链接](http://paddle-imagenet-models-name.bj.bcebos.com/MobileNetV1_pretrained.tar) |
|MobileNetV1|quant_post|70.18%/89.25% (-0.81%/-0.43%)| 4.4 | - | [下载链接](https://paddlemodels.bj.bcebos.com/PaddleSlim/MobileNetV1_quant_post.tar) |
|MobileNetV1|quant_aware|70.60%/89.57% (-0.39%/-0.11%)| 4.4 | -| [下载链接](https://paddlemodels.bj.bcebos.com/PaddleSlim/MobileNetV1_quant_aware.tar) |
| MobileNetV2 | - |72.15%/90.65%| 15 | - | [下载链接](https://paddle-imagenet-models-name.bj.bcebos.com/MobileNetV2_pretrained.tar) |
| MobileNetV2 | quant_post | 71.15%/90.11% (-1%/-0.54%)| 4.0   | - | [下载链接](https://paddlemodels.bj.bcebos.com/PaddleSlim/MobileNetV2_quant_post.tar) |
| MobileNetV2 | quant_aware |72.05%/90.63% (-0.1%/-0.02%)| 4.0 | - | [下载链接](https://paddlemodels.bj.bcebos.com/PaddleSlim/MobileNetV2_quant_aware.tar) |
|ResNet50|-|76.50%/93.00%| 99 | 2.71 | [下载链接](http://paddle-imagenet-models-name.bj.bcebos.com/ResNet50_pretrained.tar) |
|ResNet50|quant_post|76.33%/93.02% (-0.17%/+0.02%)| 25.1| 1.19 | [下载链接](https://paddlemodels.bj.bcebos.com/PaddleSlim/ResNet50_quant_post.tar) |
|ResNet50|quant_aware|    76.48%/93.11% (-0.02%/+0.11%)| 25.1 | 1.17 | [下载链接](https://paddlemodels.bj.bcebos.com/PaddleSlim/ResNet50_quant_awre.tar) |

分类模型Lite时延(ms)

| 设备    | 模型类型    | 压缩策略      | armv7 Thread 1 | armv7 Thread 2 | armv7 Thread 4 | armv8 Thread 1 | armv8 Thread 2 | armv8 Thread 4 |
| ------- | ----------- | ------------- | -------------- | -------------- | -------------- | -------------- | -------------- | -------------- |
| 高通835 | MobileNetV1 | FP32 baseline | 96.1942        | 53.2058        | 32.4468        | 88.4955        | 47.95          | 27.5189        |
| 高通835 | MobileNetV1 | quant_aware   | 60.8186        | 32.1931        | 16.4275        | 56.4311        | 29.5446        | 15.1053        |
| 高通835 | MobileNetV1 | quant_post    | 60.5615        | 32.4016        | 16.6596        | 56.5266        | 29.7178        | 15.1459        |
| 高通835 | MobileNetV2 | FP32 baseline | 65.715         | 38.1346        | 25.155         | 61.3593        | 36.2038        | 22.849         |
| 高通835 | MobileNetV2 | quant_aware   | 48.3655        | 30.2021        | 21.9303        | 46.1487        | 27.3146        | 18.3053        |
| 高通835 | MobileNetV2 | quant_post    | 48.3495        | 30.3069        | 22.1506        | 45.8715        | 27.4105        | 18.2223        |
| 高通835 | ResNet50    | FP32 baseline | 526.811        | 319.6486       | 205.8345       | 506.1138       | 335.1584       | 214.8936       |
| 高通835 | ResNet50    | quant_aware   | 475.4538       | 256.8672       | 139.699        | 461.7344       | 247.9506       | 145.9847       |
| 高通835 | ResNet50    | quant_post    | 476.0507       | 256.5963       | 139.7266       | 461.9176       | 248.3795       | 149.353        |
| 高通855 | MobileNetV1 | FP32 baseline | 33.5086        | 19.5773        | 11.7534        | 31.3474        | 18.5382        | 10.0811        |
| 高通855 | MobileNetV1 | quant_aware   | 36.7067        | 21.628         | 11.0372        | 14.0238        | 8.199          | 4.2588         |
| 高通855 | MobileNetV1 | quant_post    | 37.0498        | 21.7081        | 11.0779        | 14.0947        | 8.1926         | 4.2934         |
| 高通855 | MobileNetV2 | FP32 baseline | 25.0396        | 15.2862        | 9.6609         | 22.909         | 14.1797        | 8.8325         |
| 高通855 | MobileNetV2 | quant_aware   | 28.1583        | 18.3317        | 11.8103        | 16.9158        | 11.1606        | 7.4148         |
| 高通855 | MobileNetV2 | quant_post    | 28.1631        | 18.3917        | 11.8333        | 16.9399        | 11.1772        | 7.4176         |
| 高通855 | ResNet50    | FP32 baseline | 185.3705       | 113.0825       | 87.0741        | 177.7367       | 110.0433       | 74.4114        |
| 高通855 | ResNet50    | quant_aware   | 327.6883       | 202.4536       | 106.243        | 243.5621       | 150.0542       | 78.4205        |
| 高通855 | ResNet50    | quant_post    | 328.2683       | 201.9937       | 106.744        | 242.6397       | 150.0338       | 79.8659        |
| 麒麟970 | MobileNetV1 | FP32 baseline | 101.2455       | 56.4053        | 35.6484        | 94.8985        | 51.7251        | 31.9511        |
| 麒麟970 | MobileNetV1 | quant_aware   | 62.5012        | 32.1863        | 16.6018        | 57.7477        | 29.2116        | 15.0703        |
| 麒麟970 | MobileNetV1 | quant_post    | 62.4412        | 32.2585        | 16.6215        | 57.825         | 29.2573        | 15.1206        |
| 麒麟970 | MobileNetV2 | FP32 baseline | 70.4176        | 42.0795        | 25.1939        | 68.9597        | 39.2145        | 22.6617        |
| 麒麟970 | MobileNetV2 | quant_aware   | 52.9961        | 31.5323        | 22.1447        | 49.4858        | 28.0856        | 18.7287        |
| 麒麟970 | MobileNetV2 | quant_post    | 53.0961        | 31.7987        | 21.8334        | 49.383         | 28.2358        | 18.3642        |
| 麒麟970 | ResNet50    | FP32 baseline | 586.8943       | 344.0858       | 228.2293       | 573.3344       | 351.4332       | 225.8006       |
| 麒麟970 | ResNet50    | quant_aware   | 488.361        | 260.1697       | 142.416        | 479.5668       | 249.8485       | 138.1742       |
| 麒麟970 | ResNet50    | quant_post    | 489.6188       | 258.3279       | 142.6063       | 480.0064       | 249.5339       | 138.5284       |





### 1.2 剪裁


PaddleLite推理耗时说明：

环境：Qualcomm SnapDragon 845 + armv8

速度指标：Thread1/Thread2/Thread4耗时

PaddleLite版本： v2.3


| 模型 | 压缩方法 | Top-1/Top-5 Acc | 模型体积（MB） | GFLOPs |PaddleLite推理耗时|TensorRT推理速度(FPS)| 下载 |
|:--:|:---:|:--:|:--:|:--:|:--:|:--:|:--:|
| MobileNetV1 |    Baseline    |         70.99%/89.68%         |       17       |  1.11  |66.052\35.8014\19.5762|-| [下载链接](http://paddle-imagenet-models-name.bj.bcebos.com/MobileNetV1_pretrained.tar) |
| MobileNetV1 |  uniform -50%  | 69.4%/88.66% (-1.59%/-1.02%)  |       9        |  0.56  | 33.5636\18.6834\10.5076|-|[下载链接](https://paddlemodels.bj.bcebos.com/PaddleSlim/MobileNetV1_uniform-50.tar) |
| MobileNetV1 | sensitive -30% |  70.4%/89.3% (-0.59%/-0.38%)  |       12       |  0.74  | 46.5958\25.3098\13.6982|-|[下载链接](https://paddlemodels.bj.bcebos.com/PaddleSlim/MobileNetV1_sensitive-30.tar) |
| MobileNetV1 | sensitive -50% | 69.8% / 88.9% (-1.19%/-0.78%) |       9        |  0.56  |37.9892\20.7882\11.3144|-| [下载链接](https://paddlemodels.bj.bcebos.com/PaddleSlim/MobileNetV1_sensitive-50.tar) |
| MobileNetV2 |       -        |         72.15%/90.65%         |       15       |  0.59  |41.7874\23.375\13.3998|-| [下载链接](https://paddle-imagenet-models-name.bj.bcebos.com/MobileNetV2_pretrained.tar) |
| MobileNetV2 |  uniform -50%  | 65.79%/86.11% (-6.35%/-4.47%) |       11       | 0.296  |23.8842\13.8698\8.5572|-| [下载链接](https://paddlemodels.bj.bcebos.com/PaddleSlim/MobileNetV2_uniform-50.tar) |
|  ResNet34   |       -        |         74.57%/92.14%         |       84       |  7.36  |217.808\139.943\96.7504|342.32| [下载链接](https://paddle-imagenet-models-name.bj.bcebos.com/ResNet34_pretrained.tar) |
|  ResNet34   |  uniform -50%  | 70.99%/89.95% (-3.58%/-2.19%) |       41       |  3.67  |114.787\75.0332\51.8438|452.41| [下载链接](https://paddlemodels.bj.bcebos.com/PaddleSlim/ResNet34_uniform-50.tar) |
|  ResNet34   |  auto -55.05%  | 70.24%/89.63% (-4.33%/-2.51%) |       33       |  3.31  |105.924\69.3222\48.0246|457.25| [下载链接](https://paddlemodels.bj.bcebos.com/PaddleSlim/ResNet34_auto-55.tar) |


### 1.3 蒸馏

| 模型 | 压缩方法 | Top-1/Top-5 Acc | 模型体积（MB） | 下载 |
|:--:|:---:|:--:|:--:|:--:|
| MobileNetV1 |                     student                     |  70.99%/89.68%  |       17       | [下载链接](http://paddle-imagenet-models-name.bj.bcebos.com/MobileNetV1_pretrained.tar) |
|ResNet50_vd|teacher|79.12%/94.44%| 99 | [下载链接](https://paddle-imagenet-models-name.bj.bcebos.com/ResNet50_vd_pretrained.tar) |
|MobileNetV1|ResNet50_vd<sup>[1](#trans1)</sup> distill|72.77%/90.68% (+1.78%/+1.00%)| 17 | [下载链接](https://paddlemodels.bj.bcebos.com/PaddleSlim/MobileNetV1_distilled.tar) |
| MobileNetV2 |                     student                     |  72.15%/90.65%  |       15       | [下载链接](https://paddle-imagenet-models-name.bj.bcebos.com/MobileNetV2_pretrained.tar) |
| MobileNetV2 |            ResNet50_vd distill             |  74.28%/91.53% (+2.13%/+0.88%)  |       15       | [下载链接](https://paddlemodels.bj.bcebos.com/PaddleSlim/MobileNetV2_distilled.tar) |
|  ResNet50   |                     student                     |  76.50%/93.00%  |       99       | [下载链接](http://paddle-imagenet-models-name.bj.bcebos.com/ResNet50_pretrained.tar) |
|ResNet101|teacher|77.56%/93.64%| 173 | [下载链接](http://paddle-imagenet-models-name.bj.bcebos.com/ResNet101_pretrained.tar) |
|  ResNet50   |             ResNet101 distill              |  77.29%/93.65% (+0.79%/+0.65%)  |       99       | [下载链接](https://paddlemodels.bj.bcebos.com/PaddleSlim/ResNet50_distilled.tar) |

注意：带"_vd"后缀代表该预训练模型使用了Mixup，Mixup相关介绍参考[mixup: Beyond Empirical Risk Minimization](https://arxiv.org/abs/1710.09412)

### 1.4 搜索

数据集: ImageNet1000

| 模型 | 压缩方法 | Top-1/Top-5 Acc | 模型体积（MB） | GFLOPs | 下载 |
|:--:|:---:|:--:|:--:|:--:|:--:|
| MobileNetV2 |       -        |            72.15%/90.65%           |     15      |  0.59  | [下载链接](https://paddle-imagenet-models-name.bj.bcebos.com/MobileNetV2_pretrained.tar) |
| MobileNetV2 |     SANAS      |  71.518%/90.208% (-0.632%/-0.442%) |     14      | 0.295  | [下载链接](https://paddlemodels.cdn.bcebos.com/PaddleSlim/MobileNetV2_sanas.tar) |

数据集: Cifar10
| 模型 |压缩方法 |  Acc  | 模型参数（MB） | 下载 |
|:---:|:--:|:--:|:--:|:--:|
|          Darts               |    -    |     97.135%        |        3.767        |  -  |
| Darts_SA(基于Darts搜索空间)  |  SANAS  | 97.276%(+0.141%)   |    3.344(-11.2%)    |  -  |

Note: MobileNetV2_NAS 的token是：[4, 4, 5, 1, 1, 2, 1, 1, 0, 2, 6, 2, 0, 3, 4, 5, 0, 4, 5, 5, 1, 4, 8, 0, 0]. Darts_SA的token是：[5, 5, 0, 5, 5, 10, 7, 7, 5, 7, 7, 11, 10, 12, 10, 0, 5, 3, 10, 8].



## 2. 目标检测

### 2.1 量化

数据集： COCO 2017

|              模型              |  压缩方法   | 数据集 | Image/GPU | 输入608 Box AP | 输入416 Box AP | 输入320 Box AP | 模型体积（MB） |   TensorRT时延(V100, ms) |  下载     |
| :----------------------------: | :---------: | :----: | :-------: | :------------: | :------------: | :------------: | :------------: | :----------: |:----------: |
|      MobileNet-V1-YOLOv3       |      -      |  COCO  |     8     |      29.3      |      29.3      |      27.1      |       95       |  - | [下载链接](https://paddlemodels.bj.bcebos.com/object_detection/yolov3_mobilenet_v1.tar) |
|      MobileNet-V1-YOLOv3       | quant_post  |  COCO  |     8     |     27.9 (-1.4)|    28.0 (-1.3)      |    26.0 (-1.0) |       25       | -  | [下载链接](https://paddlemodels.bj.bcebos.com/PaddleSlim/yolov3_mobilenetv1_coco_quant_post.tar) |
|      MobileNet-V1-YOLOv3       | quant_aware |  COCO  |     8     |     28.1 (-1.2)|  28.2 (-1.1)      |    25.8 (-1.2) |       26.3     | -  | [下载链接](https://paddlemodels.bj.bcebos.com/PaddleSlim/yolov3_mobilenet_coco_quant_aware.tar) |
|      R34-YOLOv3                |      -      |  COCO  |     8     |      36.2      |      34.3      |      31.4      |       162       |  - | [下载链接](https://paddlemodels.bj.bcebos.com/object_detection/yolov3_r34.tar) |
|      R34-YOLOv3                | quant_post  |  COCO  |     8     | 35.7 (-0.5)    |      -         |      -         |       42.7      |  - | [下载链接](https://paddlemodels.bj.bcebos.com/PaddleSlim/yolov3_r34_coco_quant_post.tar) |
|      R34-YOLOv3                | quant_aware |  COCO  |     8     |  35.2 (-1.0)   | 33.3 (-1.0)    |     30.3 (-1.1)|       44       |  - | [下载链接](https://paddlemodels.bj.bcebos.com/PaddleSlim/yolov3_r34_coco_quant_aware.tar) |
| R50-dcn-YOLOv3 obj365_pretrain |      -      |  COCO  |     8     |      41.4      |       -      |       -       |       177       | 18.56  |[下载链接](https://paddlemodels.bj.bcebos.com/object_detection/yolov3_r50vd_dcn_obj365_pretrained_coco.tar) |
| R50-dcn-YOLOv3 obj365_pretrain | quant_aware |  COCO  |     8     |   40.6 (-0.8)  |       37.5   |       34.1    |       66       |  14.64 | [下载链接](https://paddlemodels.bj.bcebos.com/PaddleSlim/yolov3_r50vd_dcn_obj365_pretrained_coco_quant_aware.tar) |



数据集：WIDER-FACE



|      模型      |  压缩方法   | Image/GPU | 输入尺寸 |        Easy/Medium/Hard         | 模型体积（MB） |                             下载                             |
| :------------: | :---------: | :-------: | :------: | :-----------------------------: | :------------: | :----------------------------------------------------------: |
|   BlazeFace    |      -      |     8     |   640    |         91.5/89.2/79.7          |      815       | [下载链接](https://paddlemodels.bj.bcebos.com/object_detection/blazeface_original.tar) |
|   BlazeFace    | quant_post  |     8     |   640    | 87.8/85.1/74.9 (-3.7/-4.1/-4.8) |      228       | [下载链接](https://paddlemodels.bj.bcebos.com/PaddleSlim/blazeface_origin_quant_post.tar) |
|   BlazeFace    | quant_aware |     8     |   640    | 90.5/87.9/77.6 (-1.0/-1.3/-2.1) |      228       | [下载链接](https://paddlemodels.bj.bcebos.com/PaddleSlim/blazeface_origin_quant_aware.tar) |
| BlazeFace-Lite |      -      |     8     |   640    |         90.9/88.5/78.1          |      711       | [下载链接](https://paddlemodels.bj.bcebos.com/object_detection/blazeface_lite.tar) |
| BlazeFace-Lite | quant_post  |     8     |   640    | 89.4/86.7/75.7 (-1.5/-1.8/-2.4) |      211       | [下载链接](https://paddlemodels.bj.bcebos.com/PaddleSlim/blazeface_lite_quant_post.tar) |
| BlazeFace-Lite | quant_aware |     8     |   640    | 89.7/87.3/77.0 (-1.2/-1.2/-1.1) |      211       | [下载链接](https://paddlemodels.bj.bcebos.com/PaddleSlim/blazeface_lite_quant_aware.tar) |
| BlazeFace-NAS  |      -      |     8     |   640    |         83.7/80.7/65.8          |      244       | [下载链接](https://paddlemodels.bj.bcebos.com/object_detection/blazeface_nas.tar) |
| BlazeFace-NAS  | quant_post  |     8     |   640    | 81.6/78.3/63.6 (-2.1/-2.4/-2.2) |       71       | [下载链接](https://paddlemodels.bj.bcebos.com/PaddleSlim/blazeface_nas_quant_post.tar) |
| BlazeFace-NAS  | quant_aware |     8     |   640    | 83.1/79.7/64.2 (-0.6/-1.0/-1.6) |       71       | [下载链接](https://paddlemodels.bj.bcebos.com/PaddleSlim/blazeface_nas_quant_aware.tar) |

### 2.2 剪裁


数据集：Pasacl VOC & COCO 2017

PaddleLite推理耗时说明：

环境：Qualcomm SnapDragon 845 + armv8

速度指标：Thread1/Thread2/Thread4耗时

PaddleLite版本： v2.3

|              模型              |     压缩方法      |   数据集   | Image/GPU | 输入608 Box AP | 输入416 Box AP | 输入320 Box AP | 模型体积(MB) | GFLOPs (608*608) | PaddleLite推理耗时(ms)(608*608) | TensorRT推理速度(FPS)(608*608) | 下载 |
| :----------------------------: | :---------------: | :--------: | :-------: | :------------: | :------------: | :------------: | :----------: | :--------------: | :--------------: | :--------------: | :-----------------------------------: |
|      MobileNet-V1-YOLOv3       |     Baseline      | Pascal VOC |     8     |      76.2      |      76.7      |      75.3      |      94      |      40.49       | 1238\796.943\520.101|60.04| [下载链接](https://paddlemodels.bj.bcebos.com/object_detection/yolov3_mobilenet_v1_voc.tar) |
|      MobileNet-V1-YOLOv3       | sensitive -52.88% | Pascal VOC |     8     |  77.6 (+1.4)   |   77.7 (1.0)   |  75.5 (+0.2)   |      31      |      19.08       | 602.497\353.759\222.427 |99.36| [下载链接](https://paddlemodels.bj.bcebos.com/PaddleSlim/yolov3_mobilenet_v1_voc_prune.tar) |
|      MobileNet-V1-YOLOv3       |         -         |    COCO    |     8     |      29.3      |      29.3      |      27.0      |      95      |      41.35       |-|-| [下载链接](https://paddlemodels.bj.bcebos.com/object_detection/yolov3_mobilenet_v1.tar) |
|      MobileNet-V1-YOLOv3       | sensitive -51.77% |    COCO    |     8     |  26.0 (-3.3)   |  25.1 (-4.2)   |  22.6 (-4.4)   |      32      |      19.94       |-|73.93| [下载链接](https://paddlemodels.bj.bcebos.com/PaddleSlim/yolov3_mobilenet_v1_prune.tar) |
|         R50-dcn-YOLOv3         |         -         |    COCO    |     8     |      39.1      |       -        |       -        |     177      |      89.60       |-|27.68| [下载链接](https://paddlemodels.bj.bcebos.com/object_detection/yolov3_r50vd_dcn.tar) |
|         R50-dcn-YOLOv3         | sensitive -9.37%  |    COCO    |     8     |  39.3 (+0.2)   |       -        |       -        |     150      |      81.20       |-|30.08| [下载链接](https://paddlemodels.bj.bcebos.com/PaddleSlim/yolov3_r50vd_dcn_prune.tar) |
|         R50-dcn-YOLOv3         | sensitive -24.68% |    COCO    |     8     |  37.3 (-1.8)   |       -        |       -        |     113      |      67.48       |-|34.32| [下载链接](https://paddlemodels.bj.bcebos.com/PaddleSlim/yolov3_r50vd_dcn_prune578.tar) |
| R50-dcn-YOLOv3 obj365_pretrain |         -         |    COCO    |     8     |      41.4      |       -        |       -        |     177      |      89.60       |-|-| [下载链接](https://paddlemodels.bj.bcebos.com/object_detection/yolov3_r50vd_dcn_obj365_pretrained_coco.tar) |
| R50-dcn-YOLOv3 obj365_pretrain | sensitive -9.37%  |    COCO    |     8     |  40.5 (-0.9)   |       -        |       -        |     150      |      81.20       |-|-| [下载链接](https://paddlemodels.bj.bcebos.com/PaddleSlim/yolov3_r50vd_dcn_obj365_pretrained_coco_prune.tar) |
| R50-dcn-YOLOv3 obj365_pretrain | sensitive -24.68% |    COCO    |     8     |  37.8 (-3.3)   |       -        |       -        |     113      |      67.48       |-|-| [下载链接](https://paddlemodels.bj.bcebos.com/PaddleSlim/yolov3_r50vd_dcn_obj365_pretrained_coco_prune578.tar) |

### 2.3 蒸馏

数据集：Pasacl VOC & COCO 2017


|        模型         |        压缩方法         |   数据集   | Image/GPU | 输入608 Box AP | 输入416 Box AP | 输入320 Box AP | 模型体积（MB） |                             下载                             |
| :-----------------: | :---------------------: | :--------: | :-------: | :------------: | :------------: | :------------: | :------------: | :----------------------------------------------------------: |
| MobileNet-V1-YOLOv3 |            -            | Pascal VOC |     8     |      76.2      |      76.7      |      75.3      |       94       | [下载链接](https://paddlemodels.bj.bcebos.com/object_detection/yolov3_mobilenet_v1_voc.tar) |
|   ResNet34-YOLOv3   |            -            | Pascal VOC |     8     |      82.6      |      81.9      |      80.1      |      162       | [下载链接](https://paddlemodels.bj.bcebos.com/object_detection/yolov3_r34_voc.tar) |
| MobileNet-V1-YOLOv3 | ResNet34-YOLOv3 distill | Pascal VOC |     8     |  79.0 (+2.8)   |  78.2 (+1.5)   |  75.5 (+0.2)   |       94       | [下载链接](https://paddlemodels.bj.bcebos.com/PaddleSlim/yolov3_mobilenetv1_voc_distilled.tar) |
| MobileNet-V1-YOLOv3 |            -            |    COCO    |     8     |      29.3      |      29.3      |      27.0      |       95       | [下载链接](https://paddlemodels.bj.bcebos.com/object_detection/yolov3_mobilenet_v1.tar) |
|   ResNet34-YOLOv3   |            -            |    COCO    |     8     |      36.2      |      34.3      |      31.4      |      163       | [下载链接](https://paddlemodels.bj.bcebos.com/object_detection/yolov3_r34.tar) |
| MobileNet-V1-YOLOv3 | ResNet34-YOLOv3 distill |    COCO    |     8     |  31.4 (+2.1)   |  30.0 (+0.7)   |  27.1 (+0.1)   |       95       | [下载链接](https://paddlemodels.bj.bcebos.com/PaddleSlim/yolov3_mobilenetv1_coco_distilled.tar) |


### 2.4 搜索

数据集：WIDER-FACE

|      模型      |  压缩方法   | Image/GPU | 输入尺寸 |        Easy/Medium/Hard         | 模型体积（KB） |    硬件延时（ms）|                         下载                             |
| :------------: | :---------: | :-------: | :------: | :-----------------------------: | :------------: | :------------: | :----------------------------------------------------------: |
|   BlazeFace    |      -      |     8     |   640    |         91.5/89.2/79.7          |      815       |       71.862     | [下载链接](https://paddlemodels.bj.bcebos.com/object_detection/blazeface_original.tar) |
| BlazeFace-NAS  |      -      |     8     |   640    |         83.7/80.7/65.8          |      244       |       21.117     |[下载链接](https://paddlemodels.bj.bcebos.com/object_detection/blazeface_nas.tar) |
| BlazeFace-NASV2 |    SANAS    |     8     |   640    |         87.0/83.7/68.5          |      389       |       22.558     | [下载链接](https://paddlemodels.bj.bcebos.com/object_detection/blazeface_nas2.tar) |

Note: 硬件延时时间是利用提供的硬件延时表得到的，硬件延时表是在855芯片上基于PaddleLite测试的结果。BlazeFace-NASV2的详细配置在[这里](https://github.com/PaddlePaddle/PaddleDetection/blob/master/configs/face_detection/blazeface_nas_v2.yml).

## 3. 图像分割

数据集：Cityscapes

### 3.1 量化

|          模型          |  压缩方法   |     mIoU      | 模型体积（MB） |                             下载                             |
| :--------------------: | :---------: | :-----------: | :------------: | :----------------------------------------------------------: |
| DeepLabv3+/MobileNetv1 |      -      |     63.26     |      6.6       | [下载链接](https://paddlemodels.bj.bcebos.com/PaddleSlim/deeplabv3_mobilenetv1.tar )                         |
| DeepLabv3+/MobileNetv1 | quant_post  | 58.63 (-4.63) |      1.8       | [下载链接](https://paddlemodels.bj.bcebos.com/PaddleSlim/deeplabv3_mobilenetv1_2049x1025_quant_post.tar) |
| DeepLabv3+/MobileNetv1 | quant_aware | 62.03 (-1.23) |      1.8       | [下载链接](https://paddlemodels.bj.bcebos.com/PaddleSlim/deeplabv3_mobilenetv1_2049x1025_quant_aware.tar) |
| DeepLabv3+/MobileNetv2 |      -      |     69.81     |      7.4       | [下载链接](https://paddleseg.bj.bcebos.com/models/mobilenet_cityscapes.tgz) |
| DeepLabv3+/MobileNetv2 | quant_post  | 67.59 (-2.22) |      2.1       | [下载链接](https://paddlemodels.bj.bcebos.com/PaddleSlim/deeplabv3_mobilenetv2_2049x1025_quant_post.tar) |
| DeepLabv3+/MobileNetv2 | quant_aware | 68.33 (-1.48) |      2.1       | [下载链接](https://paddlemodels.bj.bcebos.com/PaddleSlim/deeplabv3_mobilenetv2_2049x1025_quant_aware.tar) |

图像分割模型Lite时延(ms), 输入尺寸769x769

| 设备    | 模型类型               | 压缩策略      | armv7 Thread 1 | armv7 Thread 2 | armv7 Thread 4 | armv8 Thread 1 | armv8 Thread 2 | armv8 Thread 4 |
| ------- | ---------------------- | ------------- | -------------- | -------------- | -------------- | -------------- | -------------- | -------------- |
| 高通835 | Deeplabv3- MobileNetV1 | FP32 baseline | 1227.9894      | 734.1922       | 527.9592       | 1109.96        | 699.3818       | 479.0818       |
| 高通835 | Deeplabv3- MobileNetV1 | quant_aware   | 848.6544       | 512.785        | 382.9915       | 752.3573       | 455.0901       | 307.8808       |
| 高通835 | Deeplabv3- MobileNetV1 | quant_post    | 840.2323       | 510.103        | 371.9315       | 748.9401       | 452.1745       | 309.2084       |
| 高通835 | Deeplabv3-MobileNetV2  | FP32 baseline | 1282.8126      | 793.2064       | 653.6538       | 1193.9908      | 737.1827       | 593.4522       |
| 高通835 | Deeplabv3-MobileNetV2  | quant_aware   | 976.0495       | 659.0541       | 513.4279       | 892.1468       | 582.9847       | 484.7512       |
| 高通835 | Deeplabv3-MobileNetV2  | quant_post    | 981.44         | 658.4969       | 538.6166       | 885.3273       | 586.1284       | 484.0018       |
| 高通855 | Deeplabv3- MobileNetV1 | FP32 baseline | 568.8748       | 339.8578       | 278.6316       | 420.6031       | 281.3197       | 217.5222       |
| 高通855 | Deeplabv3- MobileNetV1 | quant_aware   | 608.7578       | 347.2087       | 260.653        | 241.2394       | 177.3456       | 143.9178       |
| 高通855 | Deeplabv3- MobileNetV1 | quant_post    | 609.0142       | 347.3784       | 259.9825       | 239.4103       | 180.1894       | 139.9178       |
| 高通855 | Deeplabv3-MobileNetV2  | FP32 baseline | 639.4425       | 390.1851       | 322.7014       | 477.7667       | 339.7411       | 262.2847       |
| 高通855 | Deeplabv3-MobileNetV2  | quant_aware   | 703.7275       | 497.689        | 417.1296       | 394.3586       | 300.2503       | 239.9204       |
| 高通855 | Deeplabv3-MobileNetV2  | quant_post    | 705.7589       | 474.4076       | 427.2951       | 394.8352       | 297.4035       | 264.6724       |
| 麒麟970 | Deeplabv3- MobileNetV1 | FP32 baseline | 1682.1792      | 1437.9774      | 1181.0246      | 1261.6739      | 1068.6537      | 690.8225       |
| 麒麟970 | Deeplabv3- MobileNetV1 | quant_aware   | 1062.3394      | 1248.1014      | 878.3157       | 774.6356       | 710.6277       | 528.5376       |
| 麒麟970 | Deeplabv3- MobileNetV1 | quant_post    | 1109.1917      | 1339.6218      | 866.3587       | 771.5164       | 716.5255       | 500.6497       |
| 麒麟970 | Deeplabv3-MobileNetV2  | FP32 baseline | 1771.1301      | 1746.0569      | 1222.4805      | 1448.9739      | 1192.4491      | 760.606        |
| 麒麟970 | Deeplabv3-MobileNetV2  | quant_aware   | 1320.2905      | 921.4522       | 676.0732       | 1145.8801      | 821.5685       | 590.1713       |
| 麒麟970 | Deeplabv3-MobileNetV2  | quant_post    | 1320.386       | 918.5328       | 672.2481       | 1020.753       | 820.094        | 591.4114       |





### 3.2 剪裁

PaddleLite推理耗时说明：

环境：Qualcomm SnapDragon 845 + armv8

速度指标：Thread1/Thread2/Thread4耗时

PaddleLite版本： v2.3

|   模型    |     压缩方法      |     mIoU      | 模型体积（MB） | GFLOPs | PaddleLite推理耗时 | TensorRT推理速度(FPS) |                             下载                             |
| :-------: | :---------------: | :-----------: | :------------: | :----: | :------------: | :----: | :--------------------------------------: |
| fast-scnn |     baseline      |     69.64     |       11       | 14.41  | 1226.36\682.96\415.664 |39.53| [下载链接](https://paddlemodels.bj.bcebos.com/PaddleSlim/fast_scnn_cityscape.tar) |
| fast-scnn | uniform  -17.07%  | 69.58 (-0.06) |      8.5       | 11.95  | 1140.37\656.612\415.888 |42.01| [下载链接](https://paddlemodels.bj.bcebos.com/PaddleSlim/fast_scnn_cityscape_uniform-17.tar) |
| fast-scnn | sensitive -47.60% | 66.68 (-2.96) |      5.7       |  7.55  | 866.693\494.467\291.748 |51.48| [下载链接](https://paddlemodels.bj.bcebos.com/PaddleSlim/fast_scnn_cityscape_sensitive-47.tar) |
