a## 作业2.6
### 利用Euler method计算本题极为有效,运用迭代的方法对vt进行计算

### 代码
```python
import numpy as np
import matplotlib.pyplot as plt    

v=0.0
t=0.0

for i in range (1,1001):
    v=v-9.8*0.01
    t=t+0.01                     
    plt.plot(t,v,"^c")            


t = np.linspace(0,10)
v=-9.8*t
plt.plot(t,v,"k")                  
plt.xlabel("time")             
plt.ylabel("velocity")      
plt.title("Velocity-time Figure")
```

### 运行结果
![](https://github.com/po1sonace/computational_physics_N2015301510023/blob/master/QQ%E5%9B%BE%E7%89%8720171013222049.png)
