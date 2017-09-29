# 报告
题目：1.1

python code
```python
import numpy as np
import matplotlib.pyplot as plt

a = 10
b = 1
initial_v = int(input("Enter the initial velovity:"))
t = 0
delt_t = 1
process_v = initial_v

list_v=[process_v,] 
list_t=[t,]

for t in range(0,6000):
    process_v = process_v + (a-b*process_v)*delt_t/1000
    t=t+delt_t
    list_v.append(process_v)
    list_t.append(t)
   
c=a-b*initial_v
ture_t=np.linspace(0,5,1000)/1000
ture_v=(a-c*np.exp(-b*ture_t))/b

plt.figure(figsize=(40,21))
plt.plot(list_t,list_v,label="$v(t)$",marker='.')
plt.plot(ture_t,ture_v,linewidth=2,color="red")
plt.xlabel("Time(ms)")
plt.ylabel("velocity(m/s)")
plt.title("velocity variation")
plt.ylim(0,11)
plt.legend()
plt.show()
```
