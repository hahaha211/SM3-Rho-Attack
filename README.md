# Rho-Attack原理与实现
我们从某一个数据出发，计算SM3值，并不断将上一次的结果作为下一次的输入，这样计算下去，最终结果会进入死循环同一结果周期性出现。

SM3算法采用生日攻击的版本。

Rho-Attack实现上比较简单。起初随机选择一个数作为初始值，之后迭代循环，在hash值不等时，刷新输入值，具体实现见代码。
# 运行结果
碰撞前8bit

![Q9UEN`YFO0CW9 E}{)2@TW8](https://user-images.githubusercontent.com/71619888/181810459-23e9fad6-35ca-4dc4-a68b-d2575cb2c339.png)

碰撞前12bit

![@%{ D((@HQW5ZNC0~FV@_LK](https://user-images.githubusercontent.com/71619888/181810487-f1583158-7d66-41e3-8011-5d89f8f11775.png)

碰撞前16bit

![CXAYBRA84BIYSGB(TI1ID 8](https://user-images.githubusercontent.com/71619888/181810511-178529ee-5534-4c94-9330-b600eb99dbd5.png)

# 简单分析
1. 碰撞前8bit耗时比碰撞前12bit耗时长的原因，可能是前者初始随机数的选取不佳，导致进入循环圈较晚。
2. 后面依然是随着碰撞bit的提升，碰撞耗时增加的很快。
