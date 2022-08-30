title: 新Python项目：替换式密码
categories: Python
tags: [Python,电脑]
date: 2021-06-29 10:34:00
---
2022 Update：**警示后人：不查自带函数的后果很严重！ **额...发现可以把文字转码后+1/-1来实现

最近我才学定义函数，写了一个替换式密码小程序。

<!-- more -->

# 1.替换式密码.py

> 这个程序是可以被调用的，一共有两个函数，分别是jiami"(加密）jiemi（解密）。jiami调用时传入两个参数，第一个是明文，第二个是移位值，传回密文。jiemi调用时也传入两个参数，第一个是密文，第二个是移位值，传回明文。

```
# 文件名：替换式密码.py
# 包括两个函数

def jiami(ming, yi):
    mi = ""
    ming_old_list = list(ming)
    ming = ""
    for y in range(0, yi):
        for i in ming_old_list:
            if i == "a":
                mi += "b"
            elif i == "A":
                mi += "B"

            elif i == "b":
                mi += "c"
            elif i == "B":
                mi += "C"

            elif i == "c":
                mi += "d"
            elif i == "C":
                mi += "D"

            elif i == "d":
                mi += "e"
            elif i == "D":
                mi += "E"

            elif i == "e":
                mi += "f"
            elif i == "E":
                mi += "F"

            elif i == "f":
                mi += "g"
            elif i == "F":
                mi += "G"

            elif i == "g":
                mi += "h"
            elif i == "G":
                mi += "H"

            elif i == "h":
                mi += "i"
            elif i == "H":
                mi += "I"

            elif i == "i":
                mi += "j"
            elif i == "I":
                mi += "J"

            elif i == "j":
                mi += "k"
            elif i == "J":
                mi += "K"

            elif i == "k":
                mi += "l"
            elif i == "K":
                mi += "L"

            elif i == "l":
                mi += "m"
            elif i == "L":
                mi += "M"

            elif i == "m":
                mi += "n"
            elif i == "M":
                mi += "N"

            elif i == "n":
                mi += "o"
            elif i == "N":
                mi += "O"

            elif i == "o":
                mi += "p"
            elif i == "O":
                mi += "P"

            elif i == "p":
                mi += "q"
            elif i == "P":
                mi += "Q"

            elif i == "q":
                mi += "r"
            elif i == "Q":
                mi += "R"

            elif i == "r":
                mi += "s"
            elif i == "R":
                mi += "S"

            elif i == "s":
                mi += "t"
            elif i == "S":
                mi += "T"

            elif i == "t":
                mi += "u"
            elif i == "T":
                mi += "U"

            elif i == "u":
                mi += "v"
            elif i == "U":
                mi += "V"

            elif i == "v":
                mi += "w"
            elif i == "V":
                mi += "W"

            elif i == "w":
                mi += "x"
            elif i == "W":
                mi += "X"

            elif i == "x":
                mi += "y"
            elif i == "X":
                mi += "Y"

            elif i == "y":
                mi += "z"
            elif i == "Y":
                mi += "Z"

            elif i == "z":
                mi += "a"
            elif i == "Z":
                mi += "A"

            else:
                mi += i
        ming_old_list = list(mi)
        mi_str = mi
        mi = ""
    return mi_str


def jiemi(mi, yi):
    ming = ""
    mi_old_list = list(mi)
    mi = ""
    for y in range(0, yi):
        for i in mi_old_list:
            if i == "a":
                ming += "z"
            elif i == "A":
                ming += "Z"

            elif i == "b":
                ming += "a"
            elif i == "B":
                ming += "A"

            elif i == "c":
                ming += "b"
            elif i == "C":
                ming += "B"

            elif i == "d":
                ming += "c"
            elif i == "D":
                ming += "C"

            elif i == "e":
                ming += "d"
            elif i == "E":
                ming += "D"

            elif i == "f":
                ming += "e"
            elif i == "F":
                ming += "E"

            elif i == "g":
                ming += "f"
            elif i == "G":
                ming += "F"

            elif i == "h":
                ming += "g"
            elif i == "H":
                ming += "G"

            elif i == "i":
                ming += "h"
            elif i == "I":
                ming += "H"

            elif i == "j":
                ming += "i"
            elif i == "J":
                ming += "I"

            elif i == "k":
                ming += "j"
            elif i == "K":
                ming += "J"

            elif i == "l":
                ming += "k"
            elif i == "L":
                ming += "K"

            elif i == "m":
                ming += "l"
            elif i == "M":
                ming += "L"

            elif i == "n":
                ming += "m"
            elif i == "N":
                ming += "M"

            elif i == "o":
                ming += "n"
            elif i == "O":
                ming += "N"

            elif i == "p":
                ming += "o"
            elif i == "P":
                ming += "O"

            elif i == "q":
                ming += "p"
            elif i == "Q":
                ming += "P"

            elif i == "r":
                ming += "q"
            elif i == "R":
                ming += "Q"

            elif i == "s":
                ming += "r"
            elif i == "S":
                ming += "R"

            elif i == "t":
                ming += "s"
            elif i == "T":
                ming += "S"

            elif i == "u":
                ming += "t"
            elif i == "U":
                ming += "T"

            elif i == "v":
                ming += "u"
            elif i == "V":
                ming += "U"

            elif i == "w":
                ming += "v"
            elif i == "W":
                ming += "V"

            elif i == "x":
                ming += "w"
            elif i == "X":
                ming += "W"

            elif i == "y":
                ming += "x"
            elif i == "Y":
                ming += "X"

            elif i == "z":
                ming += "y"
            elif i == "Z":
                ming += "Y"

            else:
                ming += i
        mi_old_list = list(ming)
        ming_str = ming
        ming = ""
    return ming_str
```

# 2.文本替换式加解密.py

> 这个Python程序可以引导你加/解密

![运行效果](/images/QQ截图20210629103336-1.png)

> 代码来喽！

```
# 依赖替换式密码
# 文件名：文本替换式加解密.py

import 替换式密码

while True:
    print("欢迎使用文本加解密APP！")
    print("(1)加密 （2）解密  输入其他内容退出")
    m = input("请输入：")
    if m == "1":
        ming = input("请输入明文：")
        while True:
            try:
                yi = int(input("请输入移位值："))
            except ValueError:
                print("请输入数字！")
            else:
                break
        print("密文为：%s\\n" % (替换式密码.jiami(ming, yi)))

    elif m == "2":
        mi = input("请输入密文：")
        while True:
            try:
                yi = int(input("请输入移位值："))
            except ValueError:
                print("请输入数字！")
            else:
                break
        print("明文为：%s\\n" % (替换式密码.jiemi(mi, yi)))

    else:
        break
```