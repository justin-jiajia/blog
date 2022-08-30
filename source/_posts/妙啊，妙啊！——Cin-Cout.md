title: 妙啊，妙啊！——Cin/Cout
categories: C++
tags: [C++,小技巧]
date: 2022-07-15 11:53:29
---
有时，Cin/Cout会出现超时的现象，其实可以在程序中加入这两句解决…

<!-- more -->

```
ios::sync_with_stdio(false);
cin.tie(nullptr);
```