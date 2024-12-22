# Pytorch-Transformers

实现了一个基于PyTorch的Transformer模型

Transformer结构

```
===============================================================================================
Layer (type:depth-idx)                        Output Shape              Param #
===============================================================================================
Transformer                                   [1600, 1000]              --
├─Encoder: 1-1                                [32, 50, 512]             --
│    └─Embedding: 2-1                         [32, 50, 512]             512,000
│    └─PositionalEncoding: 2-2                [32, 50, 512]             --
│    │    └─Dropout: 3-1                      [32, 50, 512]             --
│    └─ModuleList: 2-3                        --                        --
│    │    └─Encoderlayer: 3-2                 [32, 50, 512]             --
│    │    │    └─MultiHeadAttention: 4-1      [32, 50, 512]             --
│    │    │    │    └─Linear: 5-1             [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-2             [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-3             [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-4             [32, 50, 512]             262,144
│    │    │    │    └─LayerNorm: 5-5          [32, 50, 512]             1,024
│    │    │    └─FeedForwardNetwork: 4-2      [32, 50, 512]             --
│    │    │    │    └─Linear: 5-6             [32, 50, 2048]            1,050,624
│    │    │    │    └─ReLU: 5-7               [32, 50, 2048]            --
│    │    │    │    └─Linear: 5-8             [32, 50, 512]             1,049,088
│    │    │    │    └─Dropout: 5-9            [32, 50, 512]             --
│    │    │    │    └─LayerNorm: 5-10         [32, 50, 512]             1,024
│    │    └─Encoderlayer: 3-3                 [32, 50, 512]             --
│    │    │    └─MultiHeadAttention: 4-3      [32, 50, 512]             --
│    │    │    │    └─Linear: 5-11            [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-12            [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-13            [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-14            [32, 50, 512]             262,144
│    │    │    │    └─LayerNorm: 5-15         [32, 50, 512]             1,024
│    │    │    └─FeedForwardNetwork: 4-4      [32, 50, 512]             --
│    │    │    │    └─Linear: 5-16            [32, 50, 2048]            1,050,624
│    │    │    │    └─ReLU: 5-17              [32, 50, 2048]            --
│    │    │    │    └─Linear: 5-18            [32, 50, 512]             1,049,088
│    │    │    │    └─Dropout: 5-19           [32, 50, 512]             --
│    │    │    │    └─LayerNorm: 5-20         [32, 50, 512]             1,024
│    │    └─Encoderlayer: 3-4                 [32, 50, 512]             --
│    │    │    └─MultiHeadAttention: 4-5      [32, 50, 512]             --
│    │    │    │    └─Linear: 5-21            [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-22            [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-23            [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-24            [32, 50, 512]             262,144
│    │    │    │    └─LayerNorm: 5-25         [32, 50, 512]             1,024
│    │    │    └─FeedForwardNetwork: 4-6      [32, 50, 512]             --
│    │    │    │    └─Linear: 5-26            [32, 50, 2048]            1,050,624
│    │    │    │    └─ReLU: 5-27              [32, 50, 2048]            --
│    │    │    │    └─Linear: 5-28            [32, 50, 512]             1,049,088
│    │    │    │    └─Dropout: 5-29           [32, 50, 512]             --
│    │    │    │    └─LayerNorm: 5-30         [32, 50, 512]             1,024
│    │    └─Encoderlayer: 3-5                 [32, 50, 512]             --
│    │    │    └─MultiHeadAttention: 4-7      [32, 50, 512]             --
│    │    │    │    └─Linear: 5-31            [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-32            [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-33            [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-34            [32, 50, 512]             262,144
│    │    │    │    └─LayerNorm: 5-35         [32, 50, 512]             1,024
│    │    │    └─FeedForwardNetwork: 4-8      [32, 50, 512]             --
│    │    │    │    └─Linear: 5-36            [32, 50, 2048]            1,050,624
│    │    │    │    └─ReLU: 5-37              [32, 50, 2048]            --
│    │    │    │    └─Linear: 5-38            [32, 50, 512]             1,049,088
│    │    │    │    └─Dropout: 5-39           [32, 50, 512]             --
│    │    │    │    └─LayerNorm: 5-40         [32, 50, 512]             1,024
│    │    └─Encoderlayer: 3-6                 [32, 50, 512]             --
│    │    │    └─MultiHeadAttention: 4-9      [32, 50, 512]             --
│    │    │    │    └─Linear: 5-41            [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-42            [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-43            [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-44            [32, 50, 512]             262,144
│    │    │    │    └─LayerNorm: 5-45         [32, 50, 512]             1,024
│    │    │    └─FeedForwardNetwork: 4-10     [32, 50, 512]             --
│    │    │    │    └─Linear: 5-46            [32, 50, 2048]            1,050,624
│    │    │    │    └─ReLU: 5-47              [32, 50, 2048]            --
│    │    │    │    └─Linear: 5-48            [32, 50, 512]             1,049,088
│    │    │    │    └─Dropout: 5-49           [32, 50, 512]             --
│    │    │    │    └─LayerNorm: 5-50         [32, 50, 512]             1,024
│    │    └─Encoderlayer: 3-7                 [32, 50, 512]             --
│    │    │    └─MultiHeadAttention: 4-11     [32, 50, 512]             --
│    │    │    │    └─Linear: 5-51            [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-52            [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-53            [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-54            [32, 50, 512]             262,144
│    │    │    │    └─LayerNorm: 5-55         [32, 50, 512]             1,024
│    │    │    └─FeedForwardNetwork: 4-12     [32, 50, 512]             --
│    │    │    │    └─Linear: 5-56            [32, 50, 2048]            1,050,624
│    │    │    │    └─ReLU: 5-57              [32, 50, 2048]            --
│    │    │    │    └─Linear: 5-58            [32, 50, 512]             1,049,088
│    │    │    │    └─Dropout: 5-59           [32, 50, 512]             --
│    │    │    │    └─LayerNorm: 5-60         [32, 50, 512]             1,024
├─Decoder: 1-2                                [32, 50, 512]             --
│    └─Embedding: 2-4                         [32, 50, 512]             512,000
│    └─PositionalEncoding: 2-5                [32, 50, 512]             --
│    │    └─Dropout: 3-8                      [32, 50, 512]             --
│    └─ModuleList: 2-6                        --                        --
│    │    └─Decoderlayer: 3-9                 [32, 50, 512]             --
│    │    │    └─MultiHeadAttention: 4-13     [32, 50, 512]             --
│    │    │    │    └─Linear: 5-61            [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-62            [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-63            [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-64            [32, 50, 512]             262,144
│    │    │    │    └─LayerNorm: 5-65         [32, 50, 512]             1,024
│    │    │    └─MultiHeadAttention: 4-14     [32, 50, 512]             --
│    │    │    │    └─Linear: 5-66            [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-67            [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-68            [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-69            [32, 50, 512]             262,144
│    │    │    │    └─LayerNorm: 5-70         [32, 50, 512]             1,024
│    │    │    └─FeedForwardNetwork: 4-15     [32, 50, 512]             --
│    │    │    │    └─Linear: 5-71            [32, 50, 2048]            1,050,624
│    │    │    │    └─ReLU: 5-72              [32, 50, 2048]            --
│    │    │    │    └─Linear: 5-73            [32, 50, 512]             1,049,088
│    │    │    │    └─Dropout: 5-74           [32, 50, 512]             --
│    │    │    │    └─LayerNorm: 5-75         [32, 50, 512]             1,024
│    │    └─Decoderlayer: 3-10                [32, 50, 512]             --
│    │    │    └─MultiHeadAttention: 4-16     [32, 50, 512]             --
│    │    │    │    └─Linear: 5-76            [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-77            [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-78            [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-79            [32, 50, 512]             262,144
│    │    │    │    └─LayerNorm: 5-80         [32, 50, 512]             1,024
│    │    │    └─MultiHeadAttention: 4-17     [32, 50, 512]             --
│    │    │    │    └─Linear: 5-81            [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-82            [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-83            [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-84            [32, 50, 512]             262,144
│    │    │    │    └─LayerNorm: 5-85         [32, 50, 512]             1,024
│    │    │    └─FeedForwardNetwork: 4-18     [32, 50, 512]             --
│    │    │    │    └─Linear: 5-86            [32, 50, 2048]            1,050,624
│    │    │    │    └─ReLU: 5-87              [32, 50, 2048]            --
│    │    │    │    └─Linear: 5-88            [32, 50, 512]             1,049,088
│    │    │    │    └─Dropout: 5-89           [32, 50, 512]             --
│    │    │    │    └─LayerNorm: 5-90         [32, 50, 512]             1,024
│    │    └─Decoderlayer: 3-11                [32, 50, 512]             --
│    │    │    └─MultiHeadAttention: 4-19     [32, 50, 512]             --
│    │    │    │    └─Linear: 5-91            [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-92            [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-93            [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-94            [32, 50, 512]             262,144
│    │    │    │    └─LayerNorm: 5-95         [32, 50, 512]             1,024
│    │    │    └─MultiHeadAttention: 4-20     [32, 50, 512]             --
│    │    │    │    └─Linear: 5-96            [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-97            [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-98            [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-99            [32, 50, 512]             262,144
│    │    │    │    └─LayerNorm: 5-100        [32, 50, 512]             1,024
│    │    │    └─FeedForwardNetwork: 4-21     [32, 50, 512]             --
│    │    │    │    └─Linear: 5-101           [32, 50, 2048]            1,050,624
│    │    │    │    └─ReLU: 5-102             [32, 50, 2048]            --
│    │    │    │    └─Linear: 5-103           [32, 50, 512]             1,049,088
│    │    │    │    └─Dropout: 5-104          [32, 50, 512]             --
│    │    │    │    └─LayerNorm: 5-105        [32, 50, 512]             1,024
│    │    └─Decoderlayer: 3-12                [32, 50, 512]             --
│    │    │    └─MultiHeadAttention: 4-22     [32, 50, 512]             --
│    │    │    │    └─Linear: 5-106           [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-107           [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-108           [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-109           [32, 50, 512]             262,144
│    │    │    │    └─LayerNorm: 5-110        [32, 50, 512]             1,024
│    │    │    └─MultiHeadAttention: 4-23     [32, 50, 512]             --
│    │    │    │    └─Linear: 5-111           [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-112           [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-113           [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-114           [32, 50, 512]             262,144
│    │    │    │    └─LayerNorm: 5-115        [32, 50, 512]             1,024
│    │    │    └─FeedForwardNetwork: 4-24     [32, 50, 512]             --
│    │    │    │    └─Linear: 5-116           [32, 50, 2048]            1,050,624
│    │    │    │    └─ReLU: 5-117             [32, 50, 2048]            --
│    │    │    │    └─Linear: 5-118           [32, 50, 512]             1,049,088
│    │    │    │    └─Dropout: 5-119          [32, 50, 512]             --
│    │    │    │    └─LayerNorm: 5-120        [32, 50, 512]             1,024
│    │    └─Decoderlayer: 3-13                [32, 50, 512]             --
│    │    │    └─MultiHeadAttention: 4-25     [32, 50, 512]             --
│    │    │    │    └─Linear: 5-121           [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-122           [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-123           [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-124           [32, 50, 512]             262,144
│    │    │    │    └─LayerNorm: 5-125        [32, 50, 512]             1,024
│    │    │    └─MultiHeadAttention: 4-26     [32, 50, 512]             --
│    │    │    │    └─Linear: 5-126           [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-127           [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-128           [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-129           [32, 50, 512]             262,144
│    │    │    │    └─LayerNorm: 5-130        [32, 50, 512]             1,024
│    │    │    └─FeedForwardNetwork: 4-27     [32, 50, 512]             --
│    │    │    │    └─Linear: 5-131           [32, 50, 2048]            1,050,624
│    │    │    │    └─ReLU: 5-132             [32, 50, 2048]            --
│    │    │    │    └─Linear: 5-133           [32, 50, 512]             1,049,088
│    │    │    │    └─Dropout: 5-134          [32, 50, 512]             --
│    │    │    │    └─LayerNorm: 5-135        [32, 50, 512]             1,024
│    │    └─Decoderlayer: 3-14                [32, 50, 512]             --
│    │    │    └─MultiHeadAttention: 4-28     [32, 50, 512]             --
│    │    │    │    └─Linear: 5-136           [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-137           [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-138           [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-139           [32, 50, 512]             262,144
│    │    │    │    └─LayerNorm: 5-140        [32, 50, 512]             1,024
│    │    │    └─MultiHeadAttention: 4-29     [32, 50, 512]             --
│    │    │    │    └─Linear: 5-141           [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-142           [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-143           [32, 50, 512]             262,144
│    │    │    │    └─Linear: 5-144           [32, 50, 512]             262,144
│    │    │    │    └─LayerNorm: 5-145        [32, 50, 512]             1,024
│    │    │    └─FeedForwardNetwork: 4-30     [32, 50, 512]             --
│    │    │    │    └─Linear: 5-146           [32, 50, 2048]            1,050,624
│    │    │    │    └─ReLU: 5-147             [32, 50, 2048]            --
│    │    │    │    └─Linear: 5-148           [32, 50, 512]             1,049,088
│    │    │    │    └─Dropout: 5-149          [32, 50, 512]             --
│    │    │    │    └─LayerNorm: 5-150        [32, 50, 512]             1,024
├─Linear: 1-3                                 [32, 50, 1000]            512,000
===============================================================================================
Total params: 45,637,632
Trainable params: 45,637,632
Non-trainable params: 0
Total mult-adds (G): 1.46
===============================================================================================
Input size (MB): 0.03
Forward/backward pass size (MB): 1087.59
Params size (MB): 182.55
Estimated Total Size (MB): 1270.17
===============================================================================================
```

