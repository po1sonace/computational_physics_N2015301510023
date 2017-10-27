# 题目
![](https://github.com/po1sonace/computational_physics_N2015301510023/blob/master/QQ%E5%9B%BE%E7%89%8720171027225859.png)
# 思路
本题仍然可以采用欧勒法的基本思路，即使用迭代法数，摆的运动方程写出来，模拟得到曲线，绘图并改变参数。
![](https://github.com/po1sonace/computational_physics_N2015301510023/blob/master/121.png)

![](https://github.com/po1sonace/computational_physics_N2015301510023/blob/master/12123.png)
## 代码
```python
import math
import matplotlib.pyplot as plt

def func(F):  
    theta=[0 for i in range(0,60000)]
    w=[0 for i in range(0,60000)]
    t=[0 for i in range(0,60000)]
    dt=0.001
    q=0.5
    o=0.6667
    theta[0]=0.2
    w[0]=0
    p=1
    t<10000:
    ω=ω-(math.sin(math.radians(θ))+q*ω-FD*math.sin(ΩD*t))*Δt
    θ=θ+ω*Δt
    while p:
        if p<60000:
            w[p]=w[p-1]-math.sin(theta[p-1])*dt-0.5*w[p-1]*dt+F*math.sin(o*(p-1)*dt)*dt
            theta[p]=theta[p-1]+w[p]*dt
            if theta[p]>=math.pi:
                theta[p]=theta[p]-2*math.pi
            if theta[p]<=-math.pi:
                theta[p]=theta[p]+2*math.pi
            else: 
                theta[p]=theta[p]
            t[p]=t[p-1]+dt
            p=p+1
        if p>=60000:
            break
    plt.title("theta versus t")
    plt.plot(theta,w,"r",label='F=0.500')
    plt.legend()
```
## 结果分析
将摆从0，2rad的位置释放，下为模拟的结果

![](https://github.com/po1sonace/computational_physics_N2015301510023/blob/master/%E5%9B%BE1.png)

![](https://github.com/lopo70/Computational_Physics_N2015301020170/blob/master/Exercise%2007/4.png)
