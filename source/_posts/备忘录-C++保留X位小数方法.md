title: 备忘录-C++保留X位小数方法
categories: C++
tags: [电脑,C++]
date: 2022-02-01 20:44:00
---
实用备忘录-C++保留X位小数方法。

<!-- more -->

### 1.引入`iomanip`库

```cpp
#include <iomanip>
```

### 2.使用`fixed`和`setprecision(x)`实现保留

```cpp
cout << fixed << setprecision(2) << 141 << endl; // 14
```

> 解释：先`cout`一下`fixed`,再`cout`一下`setprecision(x)`，x是你要保留的小数位数，最后只要`cout`你要的小数就好了！
