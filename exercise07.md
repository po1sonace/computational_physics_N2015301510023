# Exercise 08 Problem 3.20
## 问题
![](https://github.com/lopo70/Computational_Physics_N2015301020170/blob/master/Exercise%2008/%E6%8D%95%E8%8E%B7.PNG)
## 思路
<div align=center><a href="http://www.codecogs.com/eqnedit.php?latex=\omega&space;_{i&plus;1}=\omega&space;_{i}-\left&space;[&space;\frac{g}{l}sin(\theta&space;)&plus;q\cdot&space;\omega&space;_{i}-F_{D}sin(\Omega_{D}t_{i}&space;)\right&space;]\Delta&space;t" target="_blank"><img src="http://latex.codecogs.com/gif.latex?\omega&space;_{i&plus;1}=\omega&space;_{i}-\left&space;[&space;\frac{g}{l}sin(\theta&space;)&plus;q\cdot&space;\omega&space;_{i}-F_{D}sin(\Omega_{D}t_{i}&space;)\right&space;]\Delta&space;t" title="\omega _{i+1}=\omega _{i}-\left [ \frac{g}{l}sin(\theta )+q\cdot \omega _{i}-F_{D}sin(\Omega_{D}t_{i} )\right ]\Delta t" /></a>

<a href="http://www.codecogs.com/eqnedit.php?latex=\theta&space;_{i&plus;1}=\theta&space;_{i}&plus;\omega&space;_{i&plus;1}\Delta&space;t" target="_blank"><img src="http://latex.codecogs.com/gif.latex?\theta&space;_{i&plus;1}=\theta&space;_{i}&plus;\omega&space;_{i&plus;1}\Delta&space;t" title="\theta _{i+1}=\theta _{i}+\omega _{i+1}\Delta t" /></a>

<a href="http://www.codecogs.com/eqnedit.php?latex=t&space;_{i&plus;1}=t&space;_{i}&plus;\Delta&space;t" target="_blank"><img src="http://latex.codecogs.com/gif.latex?t&space;_{i&plus;1}=t&space;_{i}&plus;\Delta&space;t" title="t _{i+1}=t _{i}+\Delta t" /></a>

<a href="http://www.codecogs.com/eqnedit.php?latex=t\approx&space;\frac{2\pi&space;n}{\Omega&space;_{D}}" target="_blank"><img src="http://latex.codecogs.com/gif.latex?t\approx&space;\frac{2\pi&space;n}{\Omega&space;_{D}}" title="t\approx \frac{2\pi n}{\Omega _{D}}" /></a>，
<div align=center>
<a href="http://www.codecogs.com/eqnedit.php?latex=\left&space;|&space;t-\frac{2n\pi&space;}{\Omega&space;_{D}}&space;\right&space;|<&space;\frac{\Delta&space;t}{2}" target="_blank"><img src="http://latex.codecogs.com/gif.latex?\left&space;|&space;t-\frac{2n\pi&space;}{\Omega&space;_{D}}&space;\right&space;|<&space;\frac{\Delta&space;t}{2}" title="\left | t-\frac{2n\pi }{\Omega _{D}} \right |< \frac{\Delta t}{2}" /></a>
<div align=left>
## 代码
