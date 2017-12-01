# Exercise 10
## 问题
![](https://github.com/lopo70/Computational_Physics_N2015301020170/blob/master/Exercise%2010/e.png)
## 解题思路
本题目的主体算法依然采用Euler—Cromer方法.对地球，太阳，木星分别建立坐标，速度的数组。根据万有引力定律计算不同位置时的加速度。根据加速度计算速度的改变，再计算由此速度带来坐标的改变。
<div align=center>
<a href="http://www.codecogs.com/eqnedit.php?latex=\frac{dv_{x,e}}{t}=-\frac{GM_{s}x_{e}}{r^{3}}-\frac{GM_{J}(x_{e}-x_{J})}{r_{EJ}^{3}}" target="_blank"><img src="http://latex.codecogs.com/gif.latex?\frac{dv_{x,e}}{t}=-\frac{GM_{s}x_{e}}{r^{3}}-\frac{GM_{J}(x_{e}-x_{J})}{r_{EJ}^{3}}" title="\frac{dv_{x,e}}{t}=-\frac{GM_{s}x_{e}}{r^{3}}-\frac{GM_{J}(x_{e}-x_{J})}{r_{EJ}^{3}}" /></a>

<div align=left>
同理可得到地球运动y方向的运动方程，以及木星x，y方向上的运动方程。 
本文计算使用欧拉-克拉默方法。 由于该系统涉及的变量较多，使用控制变量法进行研究。之后依次改变了木星质量，太阳的初始坐标。在模拟过程中保持初始条件下木星，太阳，地球始终在一条直线上。改变这条线和水平方向的夹角。

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
