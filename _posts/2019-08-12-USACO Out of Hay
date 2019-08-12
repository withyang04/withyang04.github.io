---
layout: post
title: "USACO Out of Hay"
date: 2019-08-12
excerpt: "Kruskal"
tags: [USACO]
comments: true
---

### 日常刷水题orz

### 裸模板题

## 题目描述
### Bessie 计划调查N (2 <= N <= 2,000)个农场的干草情况，它从1号农场出发。农场之间总共有M (1 <= M <= 10,000)条双向道路，所有道路的总长度不超过1,000,000,000。有些农场之间存在着多条道路，所有的农场之间都是连通的。
### Bessie希望计算出该图中最小生成树中的最长边的长度。

----------
代码
```cpp
#include <bits/stdc++.h>
#define maxn 100001
using namespace std;
int n,m,fa[maxn];
struct node{
	int u,v,c;
}e[maxn];
inline int find(int x){
	if(fa[x] == x)return x;
	else return fa[x] = find(fa[x]);
}
bool cmp(node a,node b){
	return a.c < b.c;
}
int ans;
int main(){
	cin >> n >> m;
	for (int i = 1;i <= m;++i){
		int u,v,c;
		cin >> u >> v >> c;
		e[i].u = u;e[i].v = v;e[i].c = c;
	}
	for (int i = 1;i <= n;++i)fa[i] = i;
	sort (e+1,e+m+1,cmp);
	for (int i = 1;i <= m;++i){
		int fax = find(e[i].u),fay = find(e[i].v);
		if (fax == fay)continue;
		fa[fax] = fay;
		ans = max (ans,e[i].c);
	}
	cout << ans;
}
```
