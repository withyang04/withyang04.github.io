---
layout: post
title: "UVA1329 Corporative Network"
date: 2019-8-11
excerpt: "UVA"
tags: [UVA]
comments: true
---

### 被并差集吓傻的Linea 

### ~~不会并查集~~

### 我太难了

### 题意翻译
###　有NN个结点，初始时每个结点的父结点都不存在。你的任务是执行一次II操作和EE操作，
### 格式如下：　I\ u\ vI u v：把结点uu的父结点设为vv，距离为|u-v| \mod 1000∣u−v∣mod1000。输入保证执行指令前uu没有父结点。E\ uE u：询问uu到根节点的距离。

### 乍一看是挺像并查集，反手一波并查集炸锅，~~被小李嘲讽了qaq~~

上代码了
```cpp
#include <bits/stdc++.h>
#define maxn 20001

using namespace std;
int t,n,fa[maxn];
int sum = 0;
int main(){
	cin >> t;
	while(t--){
		char a; int u,v;
		cin >> n;
		memset (fa,0,sizeof(fa));
		while (scanf("%c",&a)){
			if (a == 'O')break;
			if (a == 'I'){
				cin >> u >> v;
				fa[u] = v;
			}
			else if(a == 'E'){
				cin >> u;
				sum = 0;
				while (fa[u]){
					sum += abs(u -fa[u]) %1000;
					u = fa[u];
				}
				cout << sum << endl;
			}
		}
	}
}
```
