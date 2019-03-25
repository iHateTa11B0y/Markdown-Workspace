# cvtransform Functions

## CenterCrop
**Input:** 输入图像维度$H\times W\times C$，输入可以是int或者tuple。
**Func:** 在原图中心截取输入大小的图片。

## RandomCrop
**Input:** 输入图像维度$H\times W\times C$，输入可以是int或者tuple。
**Func:** 在原图随机截取输入大小的图片。

## RandomResizedCrop
**Input:** 输入图像维度$H\times W\times C$, 输入是输出图像短边长和插值方式
**Func:** 在原图随机截取一部分大小随机生成的图片。
Step-1. （均匀分布）随机生成目标面积是原图的$[0.8, 1.0]$. 
Step-2. （均匀分布）随机生成宽高比在$[\frac{3}{4}, \frac{4}{3}]$.
Step-3.  求出W, H 并在原图随机截取。
Step-4.  resize到输入尺寸。
- 注：插值默认cv2.INTER_LINEAR。这个方法训练Inception会用到

## Resize
**Input:** 输出图像的短边长度(int)和插值方式
**Func:** 把图像的短边resize到输入值，不改变长宽比

## FixResize
**Input:** 输出图像的size(int or tuple)和插值方式
**Func:**  把输出图像resize到输入尺寸，可以改变长宽比

## RandomHorizontalFlip
**Input:** 图
**Func:**  0.5的机率横向翻转

## RandomVerticalFlip
**Input:** 图
**Func:**  0.5的机率纵向翻转

## Padding
**Input:** Padding的method: [none, patch, translateMask]
**Func:** 
**none:** do nothing
**patch:** add a ellipse or rectangle
[rectangle]: 对应区域置零
imgSize = x,y,c
rect Size = (x1,y1,w,h)
x1 = randint(0,x-20)
y1 = randint(0,y-20)
w = randint(30,200)
h = randint(30,200)
[ellipse]
ellipse (x1,y1,aixs1,axis2,angle)
x1 = randint(30,x-30)
y1 = randint(30,y-30)
aixs1,axis2 = random.randint(30,90)
angle = randint(0,90)
**translateMask:** add the items' own mask as a pad
随机生成$x,y\in[-180, -28]\union[28,180]$的$(x,y)$平移offset
把平移后的mask加到原图上上去
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTI0MDYxMTE4NV19
-->