## AlexNet
**Training**
Resize(256)+CenterCrop(256)+RandomCrop(224)
Augmentation:RandomHorizontalFlip()
Normalize: SubMean()
**Infering**
Resize(256)+CenterCrop(256)+SubMean()+5 patch Crop(224)

## VGG
**Training**
- Resize(S) ($S\in {224,384}$) + RandomCrop(224)
- Resize(S) ($S\in [256,512]$) + RandomCrop(224)
- Augmentation: random horizontal flipping and random RGB color shift
**Infering**
multi-crop: 即对图像进行多样本的随机裁剪，然后通过网络预测每一个样本的结构，最终对所有结果平均

## Inception
RandomResizedCrop

# Resnet
Resize(S) ($S\in [256,480]$) + RandomCrop(224) + RandomHorizontalFlip() + SubMean()
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjc2NDI2NDAzXX0=
-->