# Exercise 06 Problem 2.21
## 问题
![](https://github.com/lopo70/Computational_Physics_N2015301020170/blob/master/Exercise%2006/%E6%8D%95%E8%8E%B7.PNG)
## 解题思路
题目要求计算一个击打出的产生绕竖直轴自旋的棒球的轨迹，以及在自旋角速度为2000rpm的情况下，棒球轨迹曲线水平偏转的距离。首先在空间建立三维直角坐标系，在地面选取一个原点，棒球高度为y轴，击打方向为x轴。设棒球绕y轴逆时针旋转，可知，会产生一个-z方向的力。
<div align=center><a href="http://www.codecogs.com/eqnedit.php?latex=F_{M}=S_{0}\omega&space;v_{x}" target="_blank"><img src="http://latex.codecogs.com/gif.latex?F_{M}=S_{0}\omega&space;v_{x}" title="F_{M}=S_{0}\omega v_{x}" /></a>
<div align=left>
由于空气阻力对棒球y及z方向上的作用较小，故忽略不计。对这个问题再次使用欧勒法，则棒球实时坐标与速度为
<div align=center><a href="http://www.codecogs.com/eqnedit.php?latex=x_{i&plus;1}=x_{i}&plus;v_{x,i}\Delta&space;t" target="_blank"><img src="http://latex.codecogs.com/gif.latex?x_{i&plus;1}=x_{i}&plus;v_{x,i}\Delta&space;t" title="x_{i+1}=x_{i}+v_{x,i}\Delta t" /></a>

<a href="http://www.codecogs.com/eqnedit.php?latex=y_{i&plus;1}=y_{i}&plus;v_{y,i}\Delta&space;t" target="_blank"><img src="http://latex.codecogs.com/gif.latex?y_{i&plus;1}=y_{i}&plus;v_{y,i}\Delta&space;t" title="y_{i+1}=y_{i}+v_{y,i}\Delta t" /></a>

<a href="http://www.codecogs.com/eqnedit.php?latex=z_{i&plus;1}=z_{i}&plus;v_{z,i}\Delta&space;t" target="_blank"><img src="http://latex.codecogs.com/gif.latex?z_{i&plus;1}=z_{i}&plus;v_{z,i}\Delta&space;t" title="z_{i+1}=z_{i}+v_{z,i}\Delta t" /></a>

<a href="http://www.codecogs.com/eqnedit.php?latex=v_{x,i&plus;1}=v_{x,i}-\frac{B_{2}vv_{x,i}}{m}\Delta&space;t" target="_blank"><img src="http://latex.codecogs.com/gif.latex?v_{x,i&plus;1}=v_{x,i}-\frac{B_{2}vv_{x,i}}{m}\Delta&space;t" title="v_{x,i+1}=v_{x,i}-\frac{B_{2}vv_{x,i}}{m}\Delta t" /></a>

<a href="http://www.codecogs.com/eqnedit.php?latex=v_{y,i&plus;1}=v_{y,i}-g\Delta&space;t" target="_blank"><img src="http://latex.codecogs.com/gif.latex?v_{y,i&plus;1}=v_{y,i}-g\Delta&space;t" title="v_{y,i+1}=v_{y,i}-g\Delta t" /></a>

<a href="http://www.codecogs.com/eqnedit.php?latex=v_{z,i&plus;1}=v_{z,i}-\frac{S_{0}v_{x}\omega&space;}{m}\Delta&space;t" target="_blank"><img src="http://latex.codecogs.com/gif.latex?v_{z,i&plus;1}=v_{z,i}-\frac{S_{0}v_{x}\omega&space;}{m}\Delta&space;t" title="v_{z,i+1}=v_{z,i}-\frac{S_{0}v_{x}\omega }{m}\Delta t" /></a>

<div align=left>其中
<div align=center><a href="http://www.codecogs.com/eqnedit.php?latex=v=\sqrt{v_{x,i}^{2}&plus;v_{y,i}^{2}&plus;v_{z,i}^{2}}" target="_blank"><img src="http://latex.codecogs.com/gif.latex?v=\sqrt{v_{x,i}^{2}&plus;v_{y,i}^{2}&plus;v_{z,i}^{2}}" title="v=\sqrt{v_{x,i}^{2}+v_{y,i}^{2}+v_{z,i}^{2}}" /></a>
<div align=left>
一般情况下，设<a href="http://www.codecogs.com/eqnedit.php?latex=\frac{S_{0}}{m}=4.1\times&space;10^{-4}" target="_blank"><img src="http://latex.codecogs.com/gif.latex?\frac{S_{0}}{m}=4.1\times&space;10^{-4}" title="\frac{S_{0}}{m}=4.1\times 10^{-4}" /></a>棒球出射角度以及速度，自旋角速度为方便起见在程序中设定。另外棒球drag coefficient由下式给出
  
<div align=center><a href="http://www.codecogs.com/eqnedit.php?latex=\frac{B_{2}}{m}=0.0039&plus;\frac{0.0058}{1&plus;exp[(v-v_{d})/\Delta&space;]}" target="_blank"><img src="http://latex.codecogs.com/gif.latex?\frac{B_{2}}{m}=0.0039&plus;\frac{0.0058}{1&plus;exp[(v-v_{d})/\Delta&space;]}" title="\frac{B_{2}}{m}=0.0039+\frac{0.0058}{1+exp[(v-v_{d})/\Delta ]}" /></a>

<div align=left>
其中vd=35m/s，\Delta=5

## 代码实现
输入任意初速，角度，自旋角速度，出射高度
```python
y=float(input("请输入初始高度："))
angel=float(input("请输入初射角度："))
w=float(input("请输入自旋角速度："))
v=float(input("请输入初始速度："))
```
程序主循环为
```python
  while y>=0:
    v=py.sqrt(vx**2+vy**2+vz**2)
    vz=vz+S*vx*w*t
    vx=vx-(0.0039+0.0058/(1+py.exp(v-35/5)))*v*vx*t
    vy=vy-9.8*t
    x=x+vx*t
    y=y+vy*t
    z=z+vz*t
    xlist.append(x)
    ylist.append(y)
    zlist.append(z)
    n=n+1
```
  为了得出棒球在y=0临界点的z方向偏转量，由上一节讨论炮弹落点时的代码，感谢刘肇宁同学的帮助
  ```python
  if y<0:
    r=ylist[n-1]/(ylist[n-1]-ylist[n])
    xlist[n]=xlist[n-1]+(xlist[n]-xlist[n-1])*r
    ylist[n]=0
    zlist[n]=zlist[n-1]+(zlist[n]-zlist[n-1])*r
```
  
  或者,在x=60feet（18.288m）home plate临界点的z方向偏转量
  ```python
  if x>=xend:
    r=(xend-xlist[n-1])/(xlist[n-1]-xlist[n])
    ylist[n]=ylist[n-1]-(ylist[n-1]-ylist[n])*r
    zlist[n]=zlist[n-1]+(zlist[n]-zlist[n-1])*r
    xlist[n]=xend
```

最后，绘出棒球轨迹在x-y平面上的投影以及z方向偏转与x的关系图，也可以绘制x-y-z三维轨迹曲线
   
## 结果分析

### 若考虑棒球落地（y=0）
棒球初速30m/s，初始角度5°，自转角速度2000rpm，初始高度1m
棒球轨迹在x-y平面上的投影以及z方向偏转与x的关系图
![](https://github.com/lopo70/Computational_Physics_N2015301020170/blob/master/Exercise%2006/a.png)
三维曲线图
![](https://github.com/lopo70/Computational_Physics_N2015301020170/blob/master/Exercise%2006/b.png)
水平方向偏转z=0.779000465391m
### 若考虑棒球到达home plate（x=18.288）
棒球初速30m/s，初始角度5°，自转角速度2000rpm，初始高度1m
棒球轨迹在x-y平面上的投影以及z方向偏转与x的关系图
![](https://github.com/lopo70/Computational_Physics_N2015301020170/blob/master/Exercise%2006/c.png)
三维曲线图
![](https://github.com/lopo70/Computational_Physics_N2015301020170/blob/master/Exercise%2006/d.png)
水平方向偏转z=0.501240103989m

增大出射角度到20°
棒球轨迹在x-y平面上的投影以及z方向偏转与x的关系图

![](https://github.com/lopo70/Computational_Physics_N2015301020170/blob/master/Exercise%2006/e.png)
水平方向偏转z=0.717086468175m

### 结论
可见，若击球手打出一个curve ball则在home plate的接球手较难接到球。因为curve ball会产生较大偏转，且其偏转程度会随着击球角度，速度，自转速度的增加而增大。![源代码](https://raw.githubusercontent.com/lopo70/Computational_Physics_N2015301020170/master/Exercise%2006/Exercise%20602.py)


