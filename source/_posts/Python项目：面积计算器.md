title: Python项目：面积计算器
categories: Python
tags: [Python,电脑]
date: 2021-06-29 10:56:00
---
这个就不多说了，开箱即用。没有函数。

<!-- more -->

```
print("欢迎使用面积计算器！")
print("（1）正方形 （2）长方形 （3）三角形 （4）平行四边形 （5）梯形")
lx = input("请输入类型：")
# 正方形
if lx == "1":
    print("正方形面积：边长*边长")
    bc = input("请输入边长：")
    bc = float(bc)
    mj = bc * bc
    print("面积：", mj)

# 长方形
if lx == "2":
    print("长方形面积：长*宽")
    c = input("请输入长：")
    c = float(c)
    k = input("请输入宽：")
    k = float(k)
    mj = c * k
    print("面积：", mj)

# 三角形
if lx == "3":
    print("三角形面积：底*高/2")
    d = input("请输入底：")
    d = float(d)
    g = input("请输入高：")
    g = float(g)
    mj = d * g / 2
    print("面积：", mj)

# 平行四边形
if lx == "4":
    print("平行四边形面积：底*高")
    d = input("请输入底：")
    d = float(d)
    g = input("请输入高：")
    g = float(g)
    mj = d * g
    print("面积：", mj)

# 梯形
if lx == "5":
    print("梯形面积：（上底+下底）*高")
    sd = input("请输入上底：")
    sd = float(sd)
    xd = input("请输入下底：")
    xd = float(xd)
    g = input("请输入高：")
    g = float(g)
    d = sd + xd
    mj = d * g
    print("面积：", mj)
```

![运行效果](/images/image-4.png)
