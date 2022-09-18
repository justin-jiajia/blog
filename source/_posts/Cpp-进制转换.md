---
title: 洛谷P1143
date: 2022-08-24 19:08:10
categories: 题解
tags: [题解,洛谷]
---
如何在C++中进行进制转换？本文将在不使用现成函数的情况下完成这个（并不艰巨）的任务。

先抛洛谷链接:[P1143](https://www.luogu.com.cn/problem/P1143)

<!-- more -->

# 进入正题

做到N进制转X进制，肯定是把N进制数转到10进制再转到X进制，相当于是吧10进制当了一个桥梁的~

## N进制转换10进制

按权展开：

只需要将N进制的每一个数字（字母）乘N的位权次方就可以了，位权是这个数后面有几个数~

## 10进制转X进制

我们只需用简单的短除法就可以完成这个（简单？）的任务：
![短除法](/images/断除.png)

这个图展示了用短除法求10的2进制的方法。

只需用C++做个简单的虚拟即可。需要注意的是短除法是倒着取，所以要把余数一个个`push`到`stack`里面，再一个个`top`再`pop`出来！这个问题我查了半天！！！

## 代码

需要注意的是，C++`cmath`头里的`pow`（求的是次方）（似乎）**不支持**0次方，所以我们要自己判断一下。

```
#include<iostream>
#include<cmath>
#include<stack>
using namespace std;
int toto(char i) {
	if (i >= 'A') return i - 'A' + 10;

	if (i >= '0') return i - '0';
}
char outout(int i) {
	if (i > 9) return i - 10 + 'A';

	return i + '0';
}
int main() {
	ios::sync_with_stdio(false);
	cin.tie(nullptr);
	stack <char>sk;
	int to, as;
	string st;
	long long a = 0;
	double from;
	cin >> from >> st;
	as = st.size();

	for (int i = 0; i < as; i++) a += (as - i - 1 ? pow(from, as - i - 1) : 1) * toto(st[i]);

	cin >> to;

	while (a) {
		sk.push(outout(a % to));
		a /= to;
	}

	while (!sk.empty()) {
		cout << sk.top();
		sk.pop();
	}

	return 0;
}
```

写了两个简单的辅助函数`toto`和`outout`来格式化输入/输出。