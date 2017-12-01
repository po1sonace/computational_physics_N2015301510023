# Exercise 10
## 问题
![](https://github.com/lopo70/Computational_Physics_N2015301020170/blob/master/Exercise%2010/e.png)
## 思路
本题目的主体算法依然采用Euler—Cromer方法.对地球，太阳，木星分别建立坐标，速度的数组。根据万有引力定律计算不同位置时的加速度。根据加速度计算速度的改变，再计算由此速度带来坐标的改变。
<div align=center>
<a href="http://www.codecogs.com/eqnedit.php?latex=\frac{dv_{x,e}}{t}=-\frac{GM_{s}x_{e}}{r^{3}}-\frac{GM_{J}(x_{e}-x_{J})}{r_{EJ}^{3}}" target="_blank"><img src="http://latex.codecogs.com/gif.latex?\frac{dv_{x,e}}{t}=-\frac{GM_{s}x_{e}}{r^{3}}-\frac{GM_{J}(x_{e}-x_{J})}{r_{EJ}^{3}}" title="\frac{dv_{x,e}}{t}=-\frac{GM_{s}x_{e}}{r^{3}}-\frac{GM_{J}(x_{e}-x_{J})}{r_{EJ}^{3}}" /></a>

<div align=left>
同理可得到地球运动y方向的运动方程，以及木星x，y方向上的运动方程。 
本文计算使用欧拉-克拉默方法。 由于该系统涉及的变量较多，使用控制变量法进行研究。之后依次改变了木星质量，太阳的初始坐标。在模拟过程中保持初始条件下木星，太阳，地球始终在一条直线上。改变这条线和水平方向的夹角。

## 结果
### 标准情况
三者质量为标准状态时，设初始角度为0，太阳的初始坐标为(0,0)， 木星质量为其真实的质量。得到如下曲线：
<div align=center>

![](https://github.com/po1sonace/computational_physics_N2015301510023/blob/master/T1.png)
<div align=left>
可见此时太阳保持不动，木星与地球绕太阳做圆周运动，三者保持稳定运动状态。

### 木星质量增大十倍
仅仅改变木星的质量，可以看到地球的运动开始受到影响，太阳也不再固定不动，但三者仍能稳定运动。
<div align=center>
 
![](https://github.com/po1sonace/computational_physics_N2015301510023/blob/master/T2.png)
<div align=left>

### 木星质量增大一百倍
此时地球运动变得复杂，太阳开始做圆周运动。
<div align=center>
 
![](https://github.com/po1sonace/computational_physics_N2015301510023/blob/master/T3.png)
<div align=left>
可见这时地球受到太阳与木星的引力在一定区域内运动，轨迹变化较大。缩短运行时间 

## 木星质量增大一千倍
由于此时木星质量与太阳质量已经相当，引力无法束缚住太阳和木星，它们相互远离。可见，初始位置的细微改变会对轨迹产生极大的影响。这也是三体问题的一大特点：对初始条件极为敏感。
<div align=center>
 
![](https://github.com/po1sonace/computational_physics_N2015301510023/blob/master/T4.png)

