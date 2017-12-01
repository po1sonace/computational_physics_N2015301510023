# Exercise 10
## 问题
![](https://github.com/lopo70/Computational_Physics_N2015301020170/blob/master/Exercise%2010/e.png)
## 解题思路
相比较太阳与地球的两体运动，对于三体运动我们需要考虑木星对地球及太阳的影响。假设三者处在同一平面x-y平面，我们利用牛顿第二定律以及万有引力公式可以得到地球x方向上的运动方程
<div align=center>
<a href="http://www.codecogs.com/eqnedit.php?latex=\frac{dv_{x,e}}{t}=-\frac{GM_{s}x_{e}}{r^{3}}-\frac{GM_{J}(x_{e}-x_{J})}{r_{EJ}^{3}}" target="_blank"><img src="http://latex.codecogs.com/gif.latex?\frac{dv_{x,e}}{t}=-\frac{GM_{s}x_{e}}{r^{3}}-\frac{GM_{J}(x_{e}-x_{J})}{r_{EJ}^{3}}" title="\frac{dv_{x,e}}{t}=-\frac{GM_{s}x_{e}}{r^{3}}-\frac{GM_{J}(x_{e}-x_{J})}{r_{EJ}^{3}}" /></a>

<div align=left>
同理可得到地球运动y方向的运动方程，以及木星x，y方向上的运动方程。 
本文计算使用欧拉-克拉默方法。 
由相关资料，已知太阳质量，地球质量和木星质量分别为： 

<div align=center>
<a href="http://www.codecogs.com/eqnedit.php?latex=M_{S}=1.989\times&space;10^{30}kg,&space;M_{e}=6.0\times&space;10^{26}kg,&space;M_{J}=1.9\times&space;10^{27}kg" target="_blank"><img src="http://latex.codecogs.com/gif.latex?M_{S}=1.989\times&space;10^{30}kg,&space;M_{e}=6.0\times&space;10^{26}kg,&space;M_{J}=1.9\times&space;10^{27}kg" title="M_{S}=1.989\times 10^{30}kg, M_{e}=6.0\times 10^{26}kg, M_{J}=1.9\times 10^{27}kg" /></a>
<div align=left>

## 结果
### 标准情况
三者质量为标准状态时，可以得到如下运动轨迹
<div align=center>

![](https://github.com/lopo70/Computational_Physics_N2015301020170/blob/master/Exercise%2010/1.png)
<div align=left>
可见此时太阳保持不动，木星与地球绕太阳做圆周运动，三者保持稳定运动状态。这是由于太阳的质量相对其余二者而言相当大，木星对地球的影响可以忽略。

### 木星质量增大十倍
可以看到地球的运动开始受到影响，太阳也不再固定不动，但三者仍能稳定运动。
<div align=center>
 
![](https://github.com/lopo70/Computational_Physics_N2015301020170/blob/master/Exercise%2010/2.png)
<div align=left>

### 木星质量增大一百倍
此时地球运动变得复杂，太阳开始做圆周运动。
<div align=center>
 
![](https://github.com/lopo70/Computational_Physics_N2015301020170/blob/master/Exercise%2010/3.png)
<div align=left>

## 木星质量增大一千倍
由于此时木星质量与太阳质量已经相当，引力无法束缚住太阳和木星，它们相互远离。由于地球一开始与太阳距离更近，在之后地球跟随着太阳运动。
<div align=center>
 
![](https://github.com/lopo70/Computational_Physics_N2015301020170/blob/master/Exercise%2010/4.png)

