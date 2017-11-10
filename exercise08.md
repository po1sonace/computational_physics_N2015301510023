# Exercise 09
# 问题
![](https://github.com/lopo70/Computational_Physics_N2015301020170/blob/master/Exercise%2009/%E6%8D%95%E8%8E%B7.PNG)
## 解题思路
用Euler法计算绘制台球在不同平面下的轨迹并观察混沌现象
当碰撞发生时,<br>
![](http://latex.codecogs.com/gif.latex?%5C%5C%20%5Cvec%7Bv%7D_%7Bi%2C%5Cperp%20%7D%3D%28%5Cvec%7Bv%7D_%7Bi%7D%5Ccdot%20%5Chat%7Bn%7D%29%5Chat%7Bn%7D%20%5C%5C%20%5Cvec%7Bv%7D_%7Bi%2C%5Cparallel%20%7D%3D%5Cvec%7Bv%7D_%7Bi%7D-%5Cvec%7Bv%7D_%7Bi%2C%5Cperp%20%7D)<br>
所以碰撞后的速度为<br>
![](http://latex.codecogs.com/gif.latex?%5C%5C%20%5Cvec%7Bv%7D_%7Bf%2C%5Cperp%20%7D%3D-%5Cvec%7Bv%7D_%7Bi%2C%5Cperp%20%7D%20%5C%5C%20%5Cvec%7Bv%7D_%7Bf%2C%5Cparallel%20%7D%3D%5Cvec%7Bv%7D_%7Bi%2C%5Cparallel%20%7D)
坐标方程为
![](https://github.com/lopo70/Computational_Physics_N2015301020170/blob/master/Exercise%2009/捕获1.PNG)
## 结果分析
* Circular stadium<br>
![](http://latex.codecogs.com/gif.latex?x_0%3D0.2%2Cy_0%3D0%2Cv_0%3D1%2C%5Ctheta_0%3D%5Cpi/6)<br>
![](https://github.com/lopo70/Computational_Physics_N2015301020170/blob/master/Exercise%2009/1.png)

* Stadium billiard<br>

1. ![](http://latex.codecogs.com/gif.latex?x_0%3D0.2%2Cy_0%3D0%2Cv_0%3D1%2C%5Ctheta_0%3D%5Cpi/6%2C%5Calpha%20%3D0.001)<br>
![](https://github.com/lopo70/Computational_Physics_N2015301020170/blob/master/Exercise%2009/2.png)

2. ![](http://latex.codecogs.com/gif.latex?x_0%3D0.2%2Cy_0%3D0%2Cv_0%3D1%2C%5Ctheta_0%3D%5Cpi/6%2C%5Calpha%20%3D0.01)<br>
![](https://github.com/lopo70/Computational_Physics_N2015301020170/blob/master/Exercise%2009/3.png)



* Elliptical table<br>

1. ![](http://latex.codecogs.com/gif.latex?%5Cfrac%7Bx%5E2%7D%7B25%7D&plus;%5Cfrac%7By%5E2%7D%7B16%7D%3D1)<br>

 1. ![](http://latex.codecogs.com/gif.latex?x_0%3D0.2%2Cy_0%3D0%2Cv_0%3D1%2C%5Ctheta_0%3D%5Cpi/6)<br>
 ![](https://github.com/lopo70/Computational_Physics_N2015301020170/blob/master/Exercise%2009/5.png)
 
 2. ![](http://latex.codecogs.com/gif.latex?x_0%3D1.5%2Cy_0%3D0%2Cv_0%3D1%2C%5Ctheta_0%3D%5Cpi/6)<br>
 ![](https://github.com/lopo70/Computational_Physics_N2015301020170/blob/master/Exercise%2009/6.png)
 
 3. ![](http://latex.codecogs.com/gif.latex?x_0%3D3%2Cy_0%3D0%2Cv_0%3D1%2C%5Ctheta_0%3D%5Cpi/6)<br>
 ![](https://github.com/lopo70/Computational_Physics_N2015301020170/blob/master/Exercise%2009/7.png)

* A square table with a circulai interior wall located in the center<br>
![](http://latex.codecogs.com/gif.latex?x_0%3D0.7%2Cy_0%3D0%2Cv_0%3D1%2C%5Ctheta_0%3D%5Cpi/6)<br>
![](https://github.com/lopo70/Computational_Physics_N2015301020170/blob/master/Exercise%2009/15.png)

