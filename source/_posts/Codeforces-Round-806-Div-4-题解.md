---
title: Codeforces Round#806(Div.4) 题解
date: 2022-07-15 11:16:00
categories: 题解
tags: [CF,题解]
---
哈哈哈又写题解了！[CF链接](https://codeforces.com/contest/1703)

<!-- more -->

## A YES or YES?

### 英文题面

[看这里](https://codeforces.com/contest/1703/problem/A)

### 解释

输入N个字符串，不管大小写，判断是否为“yes”

### 思路

挨个字母判断是否大写，如果大写就转换成小写，最后判断是否为“yes”。

那怎么判断是否为“yes”呢？直接`==`可以吗？似乎不行（我用的`char x[4]`），所以我们用最原始的方法：`x[0] == 'y' && x[1] == 'e' && x[2] == 's'`，过了！

### 代码

```
#include<iostream>
using namespace std;
int main() {
	int n, v;
	char x[4];
	cin >> n;
	while (n--) {
		cin >> x;
		for (v = 0; v < 3; v++) {
			if (x[v] >= 65 && x[v] <= 90) {
				x[v] = char((int)x[v] - ('Z' - 'z'));
			}
		}
		if (x[0] == 'y' && x[1] == 'e' && x[2] == 's') {
			cout << "YES\n";
		} else {
			cout << "NO\n";
		}
	}
	return 0;
}
```

## B ICPC Balloons

### 英文题面

[Here](https://codeforces.com/contest/1703/problem/B)

### 解释

有26道题目，分别叫A,B,C...Z，每个题目第一个解出来的队伍得2个气球，其他解出来的给1个气球。输入如`ABA`这样的解出顺序，求一共给出多少气球。

### 思路

开个打勾用的BOOL数组，A题索引为1，B题索引为2...在TestCase里依次`For`，如果题目在BOOL数组中为True（解出过），Count+1；如果题目在BOOL数组中为False（没解出过），Count+2并在BOOL数组中设为True。

注意一个TestCase完了之后，要把BOOL数组全设为False！（代码中`memset(xx, 0, 50 * sizeof(bool));`，50是BOOL数组的长度。

### 代码

```
#include<iostream>
#include<string.h>
using namespace std;
int main(){
	bool xx[50];
	string x;
	int n,nn,now,c;
	cin >> n;
	while(n--){
		cin >> nn >> x;
		memset(xx, 0, 50 * sizeof(bool));
		c=0;
		for (int i=0;i<nn;i++){
			now = x[i]-('A'-1);
			if (xx[now]){
				c++;
			}else{
				c+=2;
				xx[now]=true;
			}
		}
		cout << c << endl;
	}
	return 0;
}
```

## C Cypher

这个题目名是加密的意思。

### 英文题面

[点我](https://codeforces.com/contest/1703/problem/C)

### 解释

有个密码锁，有N位，告诉你现在的样子和操作（U表示+1，D表示-1），求出原来的样子。比如样例的第一个：

```
3
9 3 1
3 DDD
4 UDUU
2 DU
```

你要把第一位（9）执行DDD，也就是反过来，UUU，那是2（（9+1+1+1）%10）；
第二位（3）执行UDUU,也就是DUDD，是1（（3-1+1-1-1）%10）
第三位（1）执行DU，也就是UD，是1（（1+1-1）%10）
输出（2 1 1）。

### 代码

```
#include<iostream>
using namespace std;
int main() {
	string moves;
	int n, x, wheels[100], m;
	cin >> n;
	while (n--) {
		cin >> x;
		for (int i = 0; i < x; i++) cin >> wheels[i];
		for (int z = 0; z < x; z++) {
			cin >> m >> moves;
			for (int i = 0; i < m; i++) {
				if (moves[i] == 'U') {
					if (wheels[z] == 0) {
						wheels[z] = 9;
					} else {
						wheels[z]--;
					}
				} else {
					if (wheels[z] == 9) {
						wheels[z] = 0;
					} else {
						wheels[z]++;
					}
				}
			}
		}
		for (int i = 0; i < x; i++) cout << wheels[i] << " ";
		cout << endl;
	}
	return 0;
}
```

## D Double Strings

### 英文题面

[哈哈](https://codeforces.com/contest/1703/problem/D)

### 解释

就是给N个字符串，检查每个字符串，如果可以被其他两个（不一定不同）的字符串拼接，输出1，否则0.

### 思路

emm...只要看每个字符串的（0~1）位、（2~末尾）位或（0~2）位、（3~末尾）位...（0~末尾-2）位、（末尾-1~末尾）位是否在输入中就可以了。那怎么判断？打擂台肯定超时（要10的25次方次***吗？***【我也不确定】），可以开一个`map<string,bool> mp`来解决，只要判断`mp["aaa"]`就好了，存的话只要`mp["aaa"]=true`,很方便！

### 代码

```
#include<iostream>
#include<map>
using namespace std;
void slove() {
	int x;
	bool ok;
	map<string, bool> mp;
	cin >> x;
	string z[x], n, a, b;
	for (int i = 0; i < x; i++) {
		cin >> z[i];
		mp[z[i]] = true;
	}
	for (int i = 0; i < x; i++) {
		n = z[i];
		ok = false;
		for (int q = 1; q < n.length(); q++) {
			a = n.substr(0, q);
			b = n.substr(q, n.length() - q);
			if (mp[a] && mp[b]) {
				ok = true;
				break;
			}
		}
		cout << ok;
	}
	cout << endl;
}
int main() {
	ios::sync_with_stdio(false);
	cin.tie(nullptr);
	int n;
	cin >> n;
	while (n--) {
		slove();
	}
	return 0;
}
```
（这是这篇文章里第一次、也是唯一一次使用`slove`函数）

## E Mirror Grid

从这里开始，我就没解出来。

### 英文题面

[嘻嘻](https://codeforces.com/contest/1703/problem/E)

### 解释

emm...不会做、也是唯一一次使用`slove`函数