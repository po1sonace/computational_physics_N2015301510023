# Exercise 06 Problem 2.21
## 解题思路
<div align=center><a href="http://www.codecogs.com/eqnedit.php?latex=F_{M}=S_{0}\omega&space;v_{x}" target="_blank"><img src="http://latex.codecogs.com/gif.latex?F_{M}=S_{0}\omega&space;v_{x}" title="F_{M}=S_{0}\omega v_{x}" /></a>
<div align=left>
<div align=center><a href="http://www.codecogs.com/eqnedit.php?latex=x_{i&plus;1}=x_{i}&plus;v_{x,i}\Delta&space;t" target="_blank"><img src="http://latex.codecogs.com/gif.latex?x_{i&plus;1}=x_{i}&plus;v_{x,i}\Delta&space;t" title="x_{i+1}=x_{i}+v_{x,i}\Delta t" /></a>

<a href="http://www.codecogs.com/eqnedit.php?latex=y_{i&plus;1}=y_{i}&plus;v_{y,i}\Delta&space;t" target="_blank"><img src="http://latex.codecogs.com/gif.latex?y_{i&plus;1}=y_{i}&plus;v_{y,i}\Delta&space;t" title="y_{i+1}=y_{i}+v_{y,i}\Delta t" /></a>

<a href="http://www.codecogs.com/eqnedit.php?latex=z_{i&plus;1}=z_{i}&plus;v_{z,i}\Delta&space;t" target="_blank"><img src="http://latex.codecogs.com/gif.latex?z_{i&plus;1}=z_{i}&plus;v_{z,i}\Delta&space;t" title="z_{i+1}=z_{i}+v_{z,i}\Delta t" /></a>

<a href="http://www.codecogs.com/eqnedit.php?latex=v_{x,i&plus;1}=v_{x,i}-\frac{B_{2}vv_{x,i}}{m}\Delta&space;t" target="_blank"><img src="http://latex.codecogs.com/gif.latex?v_{x,i&plus;1}=v_{x,i}-\frac{B_{2}vv_{x,i}}{m}\Delta&space;t" title="v_{x,i+1}=v_{x,i}-\frac{B_{2}vv_{x,i}}{m}\Delta t" /></a>

<a href="http://www.codecogs.com/eqnedit.php?latex=v_{y,i&plus;1}=v_{y,i}-g\Delta&space;t" target="_blank"><img src="http://latex.codecogs.com/gif.latex?v_{y,i&plus;1}=v_{y,i}-g\Delta&space;t" title="v_{y,i+1}=v_{y,i}-g\Delta t" /></a>

<a href="http://www.codecogs.com/eqnedit.php?latex=v_{z,i&plus;1}=v_{z,i}-\frac{S_{0}v_{x}\omega&space;}{m}\Delta&space;t" target="_blank"><img src="http://latex.codecogs.com/gif.latex?v_{z,i&plus;1}=v_{z,i}-\frac{S_{0}v_{x}\omega&space;}{m}\Delta&space;t" title="v_{z,i+1}=v_{z,i}-\frac{S_{0}v_{x}\omega }{m}\Delta t" /></a>

<div align=left>
<div align=center><a href="http://www.codecogs.com/eqnedit.php?latex=v=\sqrt{v_{x,i}^{2}&plus;v_{y,i}^{2}&plus;v_{z,i}^{2}}" target="_blank"><img src="http://latex.codecogs.com/gif.latex?v=\sqrt{v_{x,i}^{2}&plus;v_{y,i}^{2}&plus;v_{z,i}^{2}}" title="v=\sqrt{v_{x,i}^{2}+v_{y,i}^{2}+v_{z,i}^{2}}" /></a>
<div align=left>
一般情况下，设<a href="http://www.codecogs.com/eqnedit.php?latex=\frac{S_{0}}{m}=4.1\times&space;10^{-4}" target="_blank"><img src="http://latex.codecogs.com/gif.latex?\frac{S_{0}}{m}=4.1\times&space;10^{-4}" title="\frac{S_{0}}{m}=4.1\times 10^{-4}" /></a>
  <div align=center><a href="http://www.codecogs.com/eqnedit.php?latex=\frac{B_{2}}{m}=0.0039&plus;\frac{0.0058}{1&plus;exp[(v-v_{d})/\Delta&space;]}" target="_blank"><img src="http://latex.codecogs.com/gif.latex?\frac{B_{2}}{m}=0.0039&plus;\frac{0.0058}{1&plus;exp[(v-v_{d})/\Delta&space;]}" title="\frac{B_{2}}{m}=0.0039+\frac{0.0058}{1+exp[(v-v_{d})/\Delta ]}" /></a>

<div align=left>

## 代码
```python
import math
import numpy as np
import matplotlib.pyplot as plt
H=float(input("please input the height of the pitcher:"))
V0=float(input("please input the initial speed of baseballs:"))
An=float(input("please input the initial angle of the baseball:"))
An=(An/180)*np.pi
Vx=(V0)*math.cos(An)
Vy=(V0)*math.sin(An)
w=float(input("please input the vertical rotation speed:"))
Vz=0
x=0
y=H
z=0
X_list=[x]
Y_list=[y]
Z_list=[z]
dt=float(0.01)
x_end=200
n=0
while y>=0 and x<x_end :
    V=np.sqrt(Vx**2+Vy**2+Vz**2)
    x=x+Vx*dt
    y=y+Vy*dt
    z=z+Vz*dt
    Vz=Vz+0.00041*Vx*w*dt
    Vx=Vx-(0.0039+0.0058/(1+np.exp((V-35)/5)))*V*Vx*dt
    Vy=Vy-9.8*dt
    X_list.append(x)
    Y_list.append(y)
    Z_list.append(z)
    n=n+1
if y<0:
    r=Y_list[n-1]/(Y_list[n-1]-Y_list[n])
    X_list[n]=X_list[n-1]+(X_list[n]-X_list[n-1])*r
    Y_list[n]=0
    Z_list[n]=Z_list[n-1]+(Z_list[n]-Z_list[n-1])*r
if x>=x_end:
    r=(x_end-X_list[n-1])/(X_list[n-1]-X_list[n])
    Y_list[n]=Y_list[n-1]-(Y_list[n-1]-Y_list[n])*r
    Z_list[n]=Z_list[n-1]+(Z_list[n]-Z_list[n-1])*r
    X_list[n]=x_end
figure=plt.figure()
ax=figure.add_subplot(111,projection='3d')
ax.plot(X_list,Z_list,Y_list)
plt.show()    
plt.plot(X_list,Y_list,label="vertical deflection")
plt.xlabel("X/m")
plt.ylabel("Y or Z/m")
plt.title("Curve Ball Trajectory")
plt.plot(X_list,Z_list,label="horizontal deflection")
plt.legend(loc="upper left")
plt.show()
print(Z_list[n])
```

最后，绘出x-y-z三维轨迹曲线
   
## 结果

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


